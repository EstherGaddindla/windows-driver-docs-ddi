---
UID: NF:bidispl.IBidiSpl.SendRecv
title: IBidiSpl::SendRecv method
author: windows-driver-content
description: The IBidiSpl::SendRecv method sends a bidi request to the printer.
old-location: print\ibidispl_ibidispl__sendrecv.htm
old-project: print
ms.assetid: 0c91abd0-5e49-4e23-a50f-9d1dacf9d868
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IBidiSpl, IBidiSpl::SendRecv, SendRecv
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IBidiSpl.IBidiSpl::SendRecv
req.alt-loc: bidispl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: Bidispl.dll
req.irql: 
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# IBidiSpl::SendRecv method



## -description
The <b>IBidiSpl::SendRecv</b> method sends a bidi request to the printer.



## -syntax

````
HRESULT IBidiSpl::SendRecv(
  [in] const LPCWSTR      pszAction,
  [in]       IBidiRequest *pRequest
);
````


## -parameters

### -param pszAction [in]

A pointer to a NULL-terminated string that specifies the action for this bidi request. It can be one of the following constants.

<table>
<tr>
<th>Constant</th>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>BIDI_ACTION_ENUM_SCHEMA</td>
<td>L"EnumSchema"</td>
<td>Enumerate the schema. The returned data will be a list of schema that the port monitor or print provider supports.</td>
</tr>
<tr>
<td>BIDI_ACTION_GET</td>
<td>L"Get"</td>
<td>Get the value of a specified schema. </td>
</tr>
<tr>
<td>BIDI_ACTION_GET_ALL</td>
<td>L"GetAll"</td>
<td>Get the values of all child nodes of the specified schema.</td>
</tr>
<tr>
<td>BIDI_ACTION_SET</td>
<td>L"Set"</td>
<td>Set a value of the schema.</td>
</tr>
<tr>
<td>BIDI_ACTION_GET_WITH_ARGUMENT</td>
<td>L"GetWithArgument"  </td>
<td>Request the bidi schema value using the data set as input argument.</td>
</tr>
</table>
 


### -param pRequest [in]

A pointer to a single bidi request.


## -returns
The method returns one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation was successfully carried out.
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>The interface handle was invalid.
<dl>
<dt><b>None of the above</b></dt>
</dl>The <b>HRESULT</b> contains an error code corresponding to the last error.

 

Note that the <b>HRESULT</b> may contain a system error code defined in <a href="https://msdn.microsoft.com/e273f5eb-e4f4-4aa7-9ed9-b418eebc6144">Bidi Error Codes</a>.


## -remarks
The BIDI_ACTION_* values are case insensitive strings.


## -see-also
<dl>
<dt>
<a href="..\bidispl\nn-bidispl-ibidispl.md">IBidiSpl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiSpl::IBidiSpl::SendRecv method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

