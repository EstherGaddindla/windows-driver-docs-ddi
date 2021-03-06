---
UID: NF:ntddk.SeSinglePrivilegeCheck
title: SeSinglePrivilegeCheck function
author: windows-driver-content
description: The SeSinglePrivilegeCheck routine checks for the passed privilege value in the context of the current thread.
old-location: kernel\sesingleprivilegecheck.htm
old-project: kernel
ms.assetid: bb83318c-b14f-421a-9cd4-69e270b825c7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: SeSinglePrivilegeCheck
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SeSinglePrivilegeCheck
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# SeSinglePrivilegeCheck function



## -description
The 
   <b>SeSinglePrivilegeCheck</b> routine checks for the passed privilege value in the context of the current thread.



## -syntax

````
BOOLEAN SeSinglePrivilegeCheck(
  _In_ LUID            PrivilegeValue,
  _In_ KPROCESSOR_MODE PreviousMode
);
````


## -parameters

### -param PrivilegeValue [in]

Specifies the <a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a> value of the privilege being checked.


### -param PreviousMode [in]

Specifies the previous execution mode, one of <b>UserMode</b> or <b>KernelMode</b>.


## -returns
<b>SeSinglePrivilegeCheck</b> returns <b>TRUE</b> if the current subject has the required privilege.


## -remarks
If <i>PreviousMode</i> is <b>KernelMode</b>, the privilege check always succeeds. Otherwise, this routine uses the token of the user-mode thread to determine whether the current (user-mode) thread has been granted the given privilege. 


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtlconvertlongtoluid.md">RtlConvertLongToLuid</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlconvertulongtoluid.md">RtlConvertUlongToLuid</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561842">RtlEqualLuid</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-sevalidsecuritydescriptor.md">SeValidSecurityDescriptor</a>
</dt>
<dt>
<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SeSinglePrivilegeCheck routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

