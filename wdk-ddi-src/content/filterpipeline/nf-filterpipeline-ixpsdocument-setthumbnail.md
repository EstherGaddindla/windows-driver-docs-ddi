---
UID: NF:filterpipeline.IXpsDocument.SetThumbnail
title: IXpsDocument::SetThumbnail method
author: windows-driver-content
description: The SetThumbnail method removes the current thumbnail object from the document and inserts a new one.
old-location: print\ixpsdocument_setthumbnail.htm
old-project: print
ms.assetid: 47211c8f-e112-47fd-bd9e-57ff7ec586a5
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IXpsDocument, IXpsDocument::SetThumbnail, SetThumbnail
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IXpsDocument.SetThumbnail
req.alt-loc: filterpipeline.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: EXpsFontRestriction
---

# IXpsDocument::SetThumbnail method



## -description
The <code>SetThumbnail</code> method removes the current thumbnail object from the document and inserts a new one.



## -syntax

````
HRESULT SetThumbnail(
  [in] IPartThumbnail *pThumbnail
);
````


## -parameters

### -param pThumbnail [in]

A pointer to a new thumbnail.


## -returns
<code>SetThumbnail</code> returns an <b>HRESULT</b> value.


## -remarks
