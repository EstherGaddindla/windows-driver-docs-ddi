---
UID: NC:wmilib.WMI_SET_DATAITEM_CALLBACK
title: WMI_SET_DATAITEM_CALLBACK
author: windows-driver-content
description: The DpWmiSetDataItem routine changes a single data item in an instance of a data block. This routine is optional.
old-location: kernel\dpwmisetdataitem.htm
old-project: kernel
ms.assetid: 409adf29-7f2b-465b-aa2d-28bbcc31a574
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _WMI_CHANGER_PROBLEM_DEVICE_ERROR, WMI_CHANGER_PROBLEM_DEVICE_ERROR, *PWMI_CHANGER_PROBLEM_DEVICE_ERROR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wmilib.h
req.include-header: Wmilib.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DpWmiSetDataItem
req.alt-loc: Wmilib.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
req.typenames: WMI_CHANGER_PROBLEM_DEVICE_ERROR, *PWMI_CHANGER_PROBLEM_DEVICE_ERROR
req.product: Windows 10 or later.
---

# WMI_SET_DATAITEM_CALLBACK callback



## -description
The <i>DpWmiSetDataItem</i> routine changes a single data item in an instance of a data block. This routine is optional.



## -prototype

````
WMI_SET_DATAITEM_CALLBACK DpWmiSetDataItem;

NTSTATUS DpWmiSetDataItem(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp,
  _In_ ULONG          GuidIndex,
  _In_ ULONG          InstanceIndex,
  _In_ ULONG          DataItemId,
  _In_ ULONG          BufferSize,
  _In_ PUCHAR         Buffer
)
{ ... }
````


## -parameters

### -param DeviceObject [in]

Pointer to the driver's WDM <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.


### -param Irp [in]

Pointer to the IRP.


### -param GuidIndex [in]

Specifies the data block by supplying a zero-based index into the list of GUIDs that the driver provided in the <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure it passed to <a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a>. 


### -param InstanceIndex [in]

If the block specified by <i>GuidIndex</i> has multiple instances, <i>InstanceIndex</i> is a zero-based value that specifies the instance.


### -param DataItemId [in]

Specifies the ID of the data item to set.


### -param BufferSize [in]

Specifies the size in bytes of the buffer at <i>Buffer</i>.


### -param Buffer [in]

Pointer to a buffer that contains the new value for the data item.


## -returns
<i>DpWmiSetDataItem</i> returns STATUS_SUCCESS or an appropriate error code such as the following:
<dl>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
<dt><b>STATUS_WMI_ITEMID_NOT_FOUND</b></dt>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
<dt><b>STATUS_WMI_READ_ONLY</b></dt>
<dt><b>STATUS_WMI_SET_FAILURE</b></dt>
</dl>

## -remarks
WMI calls a driver's <i>DpWmiSetDataItem</i> routine after the driver calls <a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a> in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550836">IRP_MN_CHANGE_SINGLE_ITEM</a> request.

Do not implement <i>DpWmiSetDataItem</i> unless you are sure that a system-supplied user-mode component requires this capability. If you implement a <i>DpWmiSetDataItem</i> routine, the driver must place the routine's address in the <b>SetWmiDataItem</b> member of the <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure that it passes to <a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a>. If you do not implement a <i>DpWmiSetDataItem</i> routine, the driver must set <b>SetWmiDataItem</b> to <b>NULL</b>. In the latter case, WMI returns STATUS_READ_ONLY to the caller.

The driver is responsible for validating all input arguments. Specifically, the driver must do the following:

Verify that the <i>GuidIndex</i> value is between zero and GuidCount-1, based on the <b>GuidCount</b> member of the <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure.

Verify that the driver has not flagged the specified data block for removal. If the driver recently specified the WMIREG_FLAG_REMOVE_GUID flag in a <a href="..\wmilib\ns-wmilib-_wmiguidreginfo.md">WMIGUIDREGINFO</a> structure that is contained in a <b>WMILIB_CONTEXT</b> structure, it is possible for a set request to arrive before the removal occurs.

Verify that the <i>InstanceIndex</i> value is within the range of instance indexes that are supported by the driver for the data block. 

Verify that the <i>DataItemId</i> value is within the range of data item identifiers that are supported by the driver for the data block. 

Verify that <i>Buffer</i> and <i>BufferSize</i> describe a valid-sized data item, and that the contents of the buffer are valid for the data item.

Verify that the specified data item is one for which the driver allows caller-initiated modifications. In other words, the driver should not allow modifications to data items that you intended to be read-only.

Do not assume the thread context is that of the initiating user-mode application—a higher-level driver might have changed it.

This routine can be pageable.

For more information about implementing this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540741">Calling WmiSystemControl to Handle WMI IRPs</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550836">IRP_MN_CHANGE_SINGLE_ITEM</a>
</dt>
<dt>
<a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a>
</dt>
<dt>
<a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WMI_SET_DATAITEM_CALLBACK callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

