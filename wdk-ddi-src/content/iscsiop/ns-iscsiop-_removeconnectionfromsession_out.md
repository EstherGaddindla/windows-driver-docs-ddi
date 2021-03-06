---
UID: NS:iscsiop._RemoveConnectionFromSession_OUT
title: _RemoveConnectionFromSession_OUT
author: windows-driver-content
description: The RemoveConnectionFromSession_OUT structure holds the output data for the RemoveConnectionFromSession method, which is used to remove a connection from a session.
old-location: storage\removeconnectionfromsession_out.htm
old-project: storage
ms.assetid: 00c6c94e-06a8-40ec-8ddd-4a4191fa1ec6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _RemoveConnectionFromSession_OUT, RemoveConnectionFromSession_OUT, *PRemoveConnectionFromSession_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RemoveConnectionFromSession_OUT
req.alt-loc: iscsiop.h
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
req.typenames: RemoveConnectionFromSession_OUT, *PRemoveConnectionFromSession_OUT
---

# _RemoveConnectionFromSession_OUT structure



## -description
The RemoveConnectionFromSession_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563973">RemoveConnectionFromSession</a> method, which is used to remove a connection from a session.



## -syntax

````
typedef struct _RemoveConnectionFromSession_OUT {
  ULONG Status;
} RemoveConnectionFromSession_OUT, *PRemoveConnectionFromSession_OUT;
````


## -struct-fields

### -field Status

This specifies the status of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563973">RemoveConnectionFromSession</a> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks
You must implement this class.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563973">RemoveConnectionFromSession</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveConnectionFromSession_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

