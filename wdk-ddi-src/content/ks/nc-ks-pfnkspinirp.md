---
UID: NC:ks.PFNKSPINIRP
title: PFNKSPINIRP
author: windows-driver-content
description: An AVStream minidriver's routine is called when an activity on the pin is performed and it receives these IRPs:IRP_MJ_CREATEIRP_MJ_CLOSE
old-location: stream\avstrminipincreate.htm
old-project: stream
ms.assetid: 85e91b13-96c8-4422-b9b7-90f6cecbb2a5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVStrMiniPinCreate
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
req.typenames: KEYWORDSELECTOR
---

# PFNKSPINIRP callback



## -description
An AVStream minidriver's routine is called when an activity on the pin is performed and it receives these IRPs:



## -prototype

````
PFNKSPINIRP AVStrMiniPinCreate;

NTSTATUS AVStrMiniPinCreate(
  _In_ PKSPIN Pin,
  _In_ PIRP   Irp
)
{ ... }
````


## -parameters

### -param Pin [in]

Pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> that was just created.


### -param Irp [in]

Pointer to the  IRP for <i>Pin</i>.


## -returns
If the routine succeeds, the operation is guaranteed to succeed. Return STATUS_SUCCESS or STATUS_PENDING. 


## -remarks
The minidriver specifies this routine's address in the <b>Create</b> member of its <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a> structure.

This routine is called when a pin is created. At the point at which this routine is called, the file object has an associated context, and the KS object header has been allocated. Typically, this function will be provided by minidrivers that want to initialize the context and resources associated with the pin. 

The filter control mutex is held while in this function. The function will be called at IRQL = PASSIVE_LEVEL.

This routine is optional.

If the routine succeeds, the create operation is guaranteed to succeed. Return STATUS_SUCCESS or STATUS_PENDING. If a minidriver returns STATUS_PENDING, AVStream will not complete the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> immediately. Before returning STATUS_PENDING, however, the minidriver must call <a href="..\wdm\nf-wdm-iomarkirppending.md">IoMarkIrpPending</a>. Once the processing of the create is complete, the minidriver must set the IRP's status code and then call <a href="..\ks\nf-ks-kscompletependingrequest.md">KsCompletePendingRequest</a>.

The minidriver specifies this routine's address in the <b>Close</b> member of its <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a> structure.

At the point at which the routine is called, any registered events on the pin have been freed, but the object is otherwise intact.

The filter control mutex is held while in this function. For more information about mutexes, please see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iomarkirppending.md">IoMarkIrpPending</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kscompletependingrequest.md">KsCompletePendingRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSPINIRP routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

