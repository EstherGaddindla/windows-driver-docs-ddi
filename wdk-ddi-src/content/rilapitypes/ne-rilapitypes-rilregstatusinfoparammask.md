---
UID: NE:rilapitypes.RILREGSTATUSINFOPARAMMASK
title: RILREGSTATUSINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilregstatusinfoparammask_2.htm
old-project: netvista
ms.assetid: 22751b8b-f19c-4480-b8f4-6ee2322419ca
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILREGSTATUSINFOPARAMMASK, RILREGSTATUSINFOPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILREGSTATUSINFOPARAMMASK
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
req.typenames: RILREGSTATUSINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILREGSTATUSINFOPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILREGSTATUSINFOPARAMMASK { 
  RIL_PARAM_REGSI_HUICCAPP,
  RIL_PARAM_REGSI_REGSTATUS,
  RIL_PARAM_REGSI_ACCESSTECHNOLOGY,
  RIL_PARAM_REGSI_SYSTEMCAPS,
  RIL_PARAM_REGSI_REGREJECTREASON,
  RIL_PARAM_REGSI_CURRENTOPERATOR,
  RIL_PARAM_REGSI_VOICEDOMAIN,
  RIL_PARAM_REGSI_NETWORKCODE,
  RIL_PARAM_REGSI_ALL
} RILREGSTATUSINFOPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_REGSI_HUICCAPP


### -field RIL_PARAM_REGSI_REGSTATUS


### -field RIL_PARAM_REGSI_ACCESSTECHNOLOGY


### -field RIL_PARAM_REGSI_SYSTEMCAPS


### -field RIL_PARAM_REGSI_REGREJECTREASON


### -field RIL_PARAM_REGSI_CURRENTOPERATOR


### -field RIL_PARAM_REGSI_VOICEDOMAIN


### -field RIL_PARAM_REGSI_NETWORKCODE


### -field RIL_PARAM_REGSI_ALL


## -remarks