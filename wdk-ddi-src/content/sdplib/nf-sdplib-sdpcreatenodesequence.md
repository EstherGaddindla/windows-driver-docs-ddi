---
UID: NF:sdplib.SdpCreateNodeSequence
title: SdpCreateNodeSequence function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeSequence function is used to create an empty sequence SDP node.
old-location: bltooth\sdpcreatenodesequence.htm
old-project: bltooth
ms.assetid: 9e02f32b-cd39-4953-9698-a1800bedf0e2
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: SdpCreateNodeSequence
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sdplib.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SdpCreateNodeSequence
req.alt-loc: sdplib.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.typenames: *PSDCMD_DESCRIPTOR, SDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpCreateNodeSequence function



## -description
The Bluetooth 
  <b>SdpCreateNodeSequence</b> function is used to create an empty sequence SDP node.



## -syntax

````
PSDP_NODE SdpCreateNodeSequence(
  _In_ ULONG tag
);
````


## -parameters

### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns
If successful, this function returns a pointer to the newly allocated 
     <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure. If not successful, this
     function returns <b>NULL</b>.


## -remarks
After a sequence node is created by calling the 
    <b>SdpCreateNodeSequence</b> function, Bluetooth drivers can call the 
    <a href="..\sdplib\nf-sdplib-sdpappendnodetocontainernode.md">
    SdpAppendNodeToContainerNode</a> function to insert other nodes into the sequence node or to add the
    new sequence node to another sequence node.

A sequence node can be added as a top-level attribute of an SDP record by calling the 
    <a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a> function.


## -see-also
<dl>
<dt>
<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpappendnodetocontainernode.md">SdpAppendNodeToContainerNode</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpCreateNodeSequence function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

