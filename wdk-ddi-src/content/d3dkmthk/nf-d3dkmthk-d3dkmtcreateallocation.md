---
UID: NF:d3dkmthk.D3DKMTCreateAllocation
title: D3DKMTCreateAllocation function
author: windows-driver-content
description: The D3DKMTCreateAllocation function creates allocations of system or video memory.
old-location: display\d3dkmtcreateallocation.htm
old-project: display
ms.assetid: 1374ad6f-3a79-4db1-acc9-28c8bd9aa93d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTCreateAllocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTCreateAllocation
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCreateAllocation function



## -description
The <b>D3DKMTCreateAllocation</b> function creates allocations of system or video memory.



## -syntax

````
NTSTATUS APIENTRY D3DKMTCreateAllocation(
  _Inout_ D3DKMT_CREATEALLOCATION *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createallocation.md">D3DKMT_CREATEALLOCATION</a> structure that contains information for creating allocations.


## -returns
<b>D3DKMTCreateAllocation</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>Allocations were successfully created.
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped or the display device was reset.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreateallocation.md">D3DKMTCreateAllocation</a> could not complete because of insufficient memory.
<dl>
<dt><b>STATUS_NO_VIDEO_MEMORY</b></dt>
</dl>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreateallocation.md">D3DKMTCreateAllocation</a> could not complete because of insufficient video memory. The video memory manager attempts to virtualize video memory; however, if the virtualization fails (such as, when virtual address space runs out), the memory manager might return this error code.

 

This function might also return other NTSTATUS values.


## -remarks
The OpenGL ICD uses the <b>D3DKMTCreateAllocation</b> function to create allocations and resources. An allocation can be associated with a resource, or an allocation can stand alone. The <b>D3DKMTCreateAllocation</b> function can also be used to add additional allocations to a resource at anytime. The only restrictions are that all shared allocations must be associated with a resource and additional allocations cannot be added to an existing shared resource.

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTCreateAllocation</b> to create a stand-alone allocation in video memory that is not associated with a resource.

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTCreateAllocation</b> to create a resource with a single system memory allocation.


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createallocation.md">D3DKMT_CREATEALLOCATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTCreateAllocation function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

