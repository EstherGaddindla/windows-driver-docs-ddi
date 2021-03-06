---
UID: NC:ndischimney.NDIS_TCP_OFFLOAD_SEND_COMPLETE
title: NDIS_TCP_OFFLOAD_SEND_COMPLETE
author: windows-driver-content
description: An offload target calls the NdisTcpOffloadSendComplete function to complete one or more send requests that were made to the MiniportTcpOffloadSend function of the offload target.
old-location: netvista\ndistcpoffloadsendcomplete.htm
old-project: netvista
ms.assetid: 1689b6f9-88f3-456f-9a7c-c6b4e76cb336
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _PD_BUFFER_VIRTUAL_SUBNET_INFO, PD_BUFFER_VIRTUAL_SUBNET_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisTcpOffloadSendComplete
req.alt-loc: ndischimney.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NDIS_TCP_OFFLOAD_SEND_COMPLETE callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisTcpOffloadSendComplete</b> function to complete one or more send requests that were made to the 
  <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">MiniportTcpOffloadSend</a> function of
  the offload target.



## -prototype

````
VOID NdisTcpOffloadSendComplete(
  _In_ NDIS_HANDLE      NdisMiniportHandle,
  _In_ PNET_BUFFER_LIST NetBufferList
);
````


## -parameters

### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     The offload target obtained these structures in one or more calls to its 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">
     MiniportTcpOffloadSend</a> function.


## -returns
None


## -remarks
To improve system performance, an offload target can create a linked list that contains 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures from multiple
    calls to the 
    <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">MiniportTcpOffloadSend</a> function.
    The driver can then pass such a linked list in a single call to the 
    <b>NdisTcpOffloadSendComplete</b> function.

Before completing one or more send requests, the offload target must do the following for each
    NET_BUFFER_LIST structure that it passes to the 
    <b>NdisTcpOffloadSendComplete</b> function:

Write a status value to the 
      <b>Status</b> member:

Specify the number of data bytes sent. The offload target does this by calling the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro with an 
      <i>id</i> of 
      <b>TcpOffloadBytesTransferred</b>.

Call the 
      <a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
      NdisAdvanceNetBufferDataStart</a> function for each NET_BUFFER structure that is associated with the
      NET_BUFFER_LIST structure. The 
      <i>NetBuffer</i> parameter passed to the 
      <b>NdisAdvanceNetBufferDataStart</b> function should point to the NET_BUFFER structure. The 
      <i>DataOffsetDelta</i> parameter should specify the number of data bytes from the NET_BUFFER structure
      that were transmitted by the offload target and that were acknowledged by the remote host. The 
      <i>FreeMdl</i> parameter is <b>NULL</b>.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">MiniportSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">MiniportTcpOffloadSend</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
   NdisAdvanceNetBufferDataStart</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_OFFLOAD_SEND_COMPLETE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

