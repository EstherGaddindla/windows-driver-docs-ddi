---
UID: NS:rilapitypes.RILDELETEMSGPARAMS
title: RILDELETEMSGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeletemsgparams_2.htm
old-project: netvista
ms.assetid: 793e9724-fff0-4bdc-a8ed-1e62fa54b4df
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILDELETEMSGPARAMS, *LPRILDELETEMSGPARAMS, RILDELETEMSGPARAMS
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
req.alt-api: RILDELETEMSGPARAMS
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
req.typenames: *LPRILDELETEMSGPARAMS, RILDELETEMSGPARAMS
req.product: Windows 10 or later.
---

# RILDELETEMSGPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILDELETEMSGPARAMS {
  HUICCAPP  hUiccApp;
  DWORD     dwIndex;
} RILDELETEMSGPARAMS, RILDELETEMSGPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field dwIndex


## -remarks
