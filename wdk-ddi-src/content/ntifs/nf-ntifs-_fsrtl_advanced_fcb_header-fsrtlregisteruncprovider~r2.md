---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlRegisterUncProvider~r2
title: FsRtlRegisterUncProvider function
author: windows-driver-content
description: The FsRtlRegisterUncProvider routine registers a network redirector as a universal naming convention (UNC) provider with the system multiple UNC provider (MUP).
old-location: ifsk\fsrtlregisteruncprovider.htm
old-project: ifsk
ms.assetid: 25bd13de-cbac-408f-b985-e131499f05f0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlRegisterUncProvider
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlRegisterUncProvider
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
req.typenames: TOKEN_TYPE
---

# FsRtlRegisterUncProvider function



## -description
The <b>FsRtlRegisterUncProvider</b> routine registers a network redirector as a universal naming convention (UNC) provider with the system multiple UNC provider (MUP).



## -syntax

````
NTSTATUS FsRtlRegisterUncProvider(
  _Out_ PHANDLE         MupHandle,
  _In_  PUNICODE_STRING RedirDevName,
  _In_  BOOLEAN         MailslotsSupported
);
````


## -parameters

### -param MupHandle [out]

A pointer to a location in which to return a MUP handle to be used when calling <b>FsRtlRegisterUncProvider</b> to deregister the network redirector. The returned handle is valid only if <b>FsRtlRegisterUncProvider</b> returns STATUS_SUCCESS.


### -param RedirDevName [in]

A pointer to a Unicode string that contains the device name of the network redirector. 


### -param MailslotsSupported [in]

Set to <b>TRUE</b> if the network redirector supports mailslots. This option is normally reserved for use by the Microsoft SMB redirector.


## -returns
<b>FsRtlRegisterUncProvider</b> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The execution mode of the original requester for  the IRP operation sent to MUP was not from kernel mode. 
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>An access violation occurred when attempting access to the MUP device. 
<dl>
<dt><b>STATUS_DATATYPE_MISALIGNMENT</b></dt>
</dl>There was a misalignment of data.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There were insufficient resources available to allocate memory for buffers.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>An invalid parameter was passed to MUP in the IRP.
<dl>
<dt><b>STATUS_INVALID_USER_BUFFER</b></dt>
</dl>An invalid parameter was passed in the <i>RedirDevName</i> parameter or an abnormal termination occurred. 

 


## -remarks
A network redirector must register with the MUP to handle UNC names. MUP is a kernel-mode component responsible for channeling all remote file system accesses using a Universal Naming Convention (UNC) name to a network redirector (the UNC provider) that is capable of handling the remote file system requests. MUP is involved when a UNC path is used by an application as illustrated by the following example that could be executed from a command line: 

MUP is not involved during an operation that creates a mapped drive letter (the "NET USE" command, for example). This operation is handled by the multiple provider router (MPR) and a user-mode WNet provider DLL for the network redirector. However, a user-mode WNet provider DLL might communicate directly with a kernel-mode network redirector driver during this operation.

On Windows Server 2003, Windows XP, and Windows 2000, remote file operations performed on a mapped drive that does not represent a Distributed File System (DFS) drive don't go through MUP. These operations go directly to the network provider that handled the drive letter mapping.

For network redirectors that conform to the Windows Vistaredirector model, MUP is involved even when a mapped network drive is used. File operations performed on the mapped drive go through MUP to the network redirector. Note that in this case that MUP simply passes the operation to the network redirector that is involved.

Network redirectors that conform to the Windows Vista redirector model should use <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex~r3.md">FsRtlRegisterUncProviderEx</a>, not <b>FsRtlRegisterUncProvider</b>.

<b>FsRtlRegisterUncProvider</b> sends a private file system control (FSCTL) to MUP to perform the registration. 

The ProviderOrder registry value determines the order in which MUP issues prefix resolution requests to individual network redirectors. This registry value is located under the following registry key: 

Changes to the ProviderOrder registry value require a reboot to take effect in MUP on Windows Server 2003, Windows XP, and Windows 2000. 

Only one network provider on a system can support mailslots. So the <i>MailslotsSupported</i> parameter is normally only set to <b>TRUE</b> for the Microsoft SMB redirector.

A driver calling <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> to create a device object for a network redirector that registers as a UNC provider (a driver that calls <b>FsRtlRegisterUncProvider</b>) must pass FILE_REMOTE_DEVICE as one of the options in the <i>DeviceCharacteristics</i> parameter that is passed to <b>IoCreateDevice</b>.

To deregister a UNC provider, use <a href="..\ntifs\nf-ntifs-fsrtlderegisteruncprovider.md">FsRtlDeregisterUncProvider</a> and pass the <i>MupHandle</i> parameter.

If a driver registers as a local disk file system (calls <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> with the <i>DeviceType</i> parameter set to FILE_DEVICE_DISK_FILE_SYSTEM rather than FILE_NETWORK_FILE_SYSTEM, for example), the driver must not call <b>FsRtlRegisterUncProvider</b> to register as a UNC provider with MUP.

For more information, see the following sections in the Design Guide:


<a href="https://msdn.microsoft.com/07c4a498-10c7-41b2-aaeb-73cab946f392">Support for UNC Naming and MUP</a>



<a href="https://msdn.microsoft.com/8ca2f9bc-14f1-45d3-a397-f3e5459cf8ec">MUP Changes in Microsoft Windows Vista</a>



## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlderegisteruncprovider.md">FsRtlDeregisterUncProvider</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex~r3.md">FsRtlRegisterUncProviderEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>
</dt>
<dt>
<a href="..\ntifs\ni-ntifs-ioctl_redir_query_path_ex.md">IOCTL_REDIR_QUERY_PATH_EX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlRegisterUncProvider routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

