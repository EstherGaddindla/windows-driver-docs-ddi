---
UID: NI:ntddvol.IOCTL_VOLUME_PHYSICAL_TO_LOGICAL
title: IOCTL_VOLUME_PHYSICAL_TO_LOGICAL
author: windows-driver-content
description: Returns the logical offset corresponding to a physical disk number and a physical offset.
old-location: storage\ioctl_volume_physical_to_logical.htm
old-project: storage
ms.assetid: 3e127456-6387-4340-84c1-d613d8094f33
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _VIDEO_WIN32K_CALLBACKS_PARAMS, VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_VOLUME_PHYSICAL_TO_LOGICAL
req.alt-loc: Ntddvol.h
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
req.typenames: VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
---

# IOCTL_VOLUME_PHYSICAL_TO_LOGICAL IOCTL



## -description

Returns the logical offset corresponding to a physical disk number and a physical offset. 



Returns the logical offset corresponding to a physical disk number and a physical offset. 

The volume manager supports this IOCTL as described for all types of basic and dynamic volumes.



## -ioctlparameters

### -input-buffer
Caller inserts the <a href="..\ntddvol\ns-ntddvol-_volume_physical_offset.md">VOLUME_PHYSICAL_OFFSET</a> structure, containing the physical offset and physical disk number, at the beginning of the buffer, at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -input-buffer-length
<b>
       Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to the value of <b>sizeof</b>(VOLUME_PHYSICAL_OFFSET).


### -output-buffer
The volume manager returns the logical offset in the <a href="..\ntddvol\ns-ntddvol-_volume_logical_offset.md">VOLUME_LOGICAL_OFFSET</a> structure at the beginning of the buffer, at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length
<b>
       Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be greater than or equal to the value of <b>sizeof</b>(VOLUME_LOGICAL_OFFSET).


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the operation is successful, the <b>Status</b> member is set to STATUS_SUCCESS.

If either the input or output buffer is too small, the volume manager sets the <b>Status</b> member to STATUS_BUFFER_TOO_SMALL. If data is returned in the output buffer but the buffer is too small to receive all of it, the volume manager sets the <b>Status</b> member to STATUS_BUFFER_OVERFLOW. The <b>Information</b> member is set to the size of the output buffer provided by the caller. 

If the given physical disk number and physical offset do not belong to the volume or if they are taken from RAID parity data, this call will fail with STATUS_INVALID_PARAMETER.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>
</dt>
<dt>
<a href="..\ntddvol\ns-ntddvol-_volume_logical_offset.md">VOLUME_LOGICAL_OFFSET</a>
</dt>
<dt>
<a href="..\ntddvol\ns-ntddvol-_volume_physical_offsets.md">VOLUME_PHYSICAL_OFFSETS</a>
</dt>
<dt>
<a href="..\ntddvol\ns-ntddvol-_volume_physical_offset.md">VOLUME_PHYSICAL_OFFSET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_VOLUME_PHYSICAL_TO_LOGICAL control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

