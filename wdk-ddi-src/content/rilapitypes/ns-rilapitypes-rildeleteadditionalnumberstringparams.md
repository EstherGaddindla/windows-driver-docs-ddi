---
UID: NS:rilapitypes.RILDELETEADDITIONALNUMBERSTRINGPARAMS
title: RILDELETEADDITIONALNUMBERSTRINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeleteadditionalnumberstringparams_2.htm
old-project: netvista
ms.assetid: 3acfa3ec-5cee-46f2-9473-bca1bc093555
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILDELETEADDITIONALNUMBERSTRINGPARAMS, *LPRILDELETEADDITIONALNUMBERSTRINGPARAMS, RILDELETEADDITIONALNUMBERSTRINGPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILDELETEADDITIONALNUMBERSTRINGPARAMS
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILDELETEADDITIONALNUMBERSTRINGPARAMS, RILDELETEADDITIONALNUMBERSTRINGPARAMS
req.product: Windows 10 or later.
---

# RILDELETEADDITIONALNUMBERSTRINGPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILDELETEADDITIONALNUMBERSTRINGPARAMS {
  HUICCAPP  hUiccApp;
  DWORD     dwNumId;
} RILDELETEADDITIONALNUMBERSTRINGPARAMS, RILDELETEADDITIONALNUMBERSTRINGPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field dwNumId


## -remarks
