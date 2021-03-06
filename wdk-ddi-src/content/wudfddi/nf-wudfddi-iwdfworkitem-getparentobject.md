---
UID: NF:wudfddi.IWDFWorkItem.GetParentObject
title: IWDFWorkItem::GetParentObject method
author: windows-driver-content
description: The GetParentObject method returns the parent framework object of this interface's work item.
old-location: wdf\iwdfworkitem_getparentobject.htm
old-project: wdf
ms.assetid: D965D8D3-B78C-4126-A675-D6D8A85AA158
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFWorkItem, IWDFWorkItem::GetParentObject, GetParentObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IWDFWorkItem.GetParentObject
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFWorkItem::GetParentObject method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetParentObject</b> method returns the parent framework object of this interface's  work item.



## -syntax

````
IWDFObject* GetParentObject();
````


## -parameters


## -returns
A pointer to the parent object interface.

A pointer to the parent object interface.

A pointer to the parent object interface.


## -remarks
For more information, see <a href="https://msdn.microsoft.com/4617A33F-9026-45FF-9CC2-7215423E6D35">Using Work Items</a>.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfworkitem.md">IWDFWorkItem</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFWorkItem::GetParentObject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

