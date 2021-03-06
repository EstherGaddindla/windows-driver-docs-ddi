---
UID: NF:fltkernel.FltFastIoMdlReadComplete
title: FltFastIoMdlReadComplete function
author: windows-driver-content
description: The FltFastIoMdlReadComplete routine completes the read operation that the FltFastIoMdlRead routine initiated.
old-location: ifsk\fltfastiomdlreadcomplete.htm
old-project: ifsk
ms.assetid: 6F5E808C-9E35-4BE8-AE67-FDD354D6FD0E
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltFastIoMdlReadComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlMdlReadCompleteDev
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: EXpsFontRestriction
---

# FltFastIoMdlReadComplete function



## -description
The <b>FltFastIoMdlReadComplete</b> routine completes the read operation that the <a href="..\fltkernel\nf-fltkernel-fltfastiomdlread.md">FltFastIoMdlRead</a> routine initiated.



## -syntax

````
BOOLEAN FsRtlMdlReadCompleteDev(
       PFLT_INSTANCE InitiatingInstance,
  _In_ PFILE_OBJECT  FileObject,
  _In_ PMDL          MdlChain
);
````


## -parameters

### -param InitiatingInstance 

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

A pointer to the file object.


### -param MdlChain [in]

On return, a pointer to a linked list of one or more MDLs that point to the cached file data.


## -returns
None


## -remarks
The <b>FltFastIoMdlReadComplete</b> routine unlocks the pages in cache memory that the <a href="..\fltkernel\nf-fltkernel-fltfastiomdlread.md">FltFastIoMdlRead</a> routine allocated.


## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfastiomdlread.md">FltFastIoMdlRead</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFastIoMdlReadComplete routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

