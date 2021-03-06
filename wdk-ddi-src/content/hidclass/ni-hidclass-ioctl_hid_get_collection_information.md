---
UID: NI:hidclass.IOCTL_HID_GET_COLLECTION_INFORMATION
title: IOCTL_HID_GET_COLLECTION_INFORMATION
author: windows-driver-content
description: The IOCTL_HID_GET_COLLECTION_INFORMATION request obtains a top-level collection's HID_COLLECTION_INFORMATION structure.
old-location: hid\ioctl_hid_get_collection_information.htm
old-project: hid
ms.assetid: 4d080a3d-7277-4bc5-b435-af2c334862ca
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidclass.h
req.include-header: Hidclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_HID_GET_COLLECTION_INFORMATION
req.alt-loc: hidclass.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PHDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT
---

# IOCTL_HID_GET_COLLECTION_INFORMATION IOCTL



## -description
The IOCTL_HID_GET_COLLECTION_INFORMATION request obtains a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="..\hidclass\ns-hidclass-_hid_collection_information.md">HID_COLLECTION_INFORMATION</a> structure. This information includes the size, in bytes, of a collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -ioctlparameters

### -input-buffer
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be &gt;= <b>sizeof</b>(HID_COLLECTION_INFORMATION). 


### -input-buffer-length
Greater than or equal to <b>sizeof</b>(HID_COLLECTION_INFORMATION). 


### -output-buffer
<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a buffer that will receive the collection information. This data will be formatted in the requester-supplied buffer as a HID_COLLECTION_INFORMATION structure.


### -output-buffer-length
The size of a HID_COLLECTION_INFORMATION structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<b>Information</b> is set to <b>sizeof</b>(HID_COLLECTION_INFORMATION) if the data was retrieved successfully. 

<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hidclass\ns-hidclass-_hid_collection_information.md">HID_COLLECTION_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_GET_COLLECTION_INFORMATION control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

