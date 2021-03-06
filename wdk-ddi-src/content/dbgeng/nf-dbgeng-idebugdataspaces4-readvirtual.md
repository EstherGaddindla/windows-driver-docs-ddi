---
UID: NF:dbgeng.IDebugDataSpaces4.ReadVirtual
title: IDebugDataSpaces4::ReadVirtual method
author: windows-driver-content
description: The ReadVirtual method reads memory from the target's virtual address space.
old-location: debugger\readvirtual.htm
old-project: debugger
ms.assetid: 083b0ab5-e2b9-4dcb-b17d-ab2ebde48665
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::ReadVirtual, ReadVirtual
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugDataSpaces.ReadVirtual,IDebugDataSpaces2.ReadVirtual,IDebugDataSpaces3.ReadVirtual,IDebugDataSpaces4.ReadVirtual
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugDataSpaces4::ReadVirtual method



## -description
The <b>ReadVirtual</b> method reads memory from the target's virtual address space.



## -syntax

````
HRESULT ReadVirtual(
  [in]            ULONG64 Offset,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's virtual address space to be read.


### -param Buffer [out]

Specifies the buffer to read the memory into.


### -param BufferSize [in]

Specifies the size in bytes of the buffer.  This is also the number of bytes being requested.


### -param BytesRead [out, optional]

Receives the number of bytes that were read.  If it is set to <b>NULL</b>, this information is not returned.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.  It is possible that <i>BytesRead</i> is less than <i>BufferSize</i>, but at least one byte of data was returned.

 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
This method fills the buffer with the contents of the memory in the target's virtual address space.

This method may reference a cache of memory data when retrieving data.  If the data is volatile, such as memory-mapped hardware state, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff554361">ReadVirtualUncached</a> instead.

When reading memory that contains pointers, these pointers are for the target's virtual address space and not the engine's.  For example, if a data structure contained a string, a second call to this method may be needed to read the contents of the string.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561468">WriteVirtual</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554361">ReadVirtualUncached</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces::ReadVirtual method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

