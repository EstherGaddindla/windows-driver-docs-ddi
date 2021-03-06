---
UID: NS:rilapitypes.RILSETCALLFORWARDINGSTATUSPARAMS
title: RILSETCALLFORWARDINGSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetcallforwardingstatusparams_2.htm
old-project: netvista
ms.assetid: 98996648-7e1a-4ccd-be8f-b31c1d0a3302
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSETCALLFORWARDINGSTATUSPARAMS, RILSETCALLFORWARDINGSTATUSPARAMS, *LPRILSETCALLFORWARDINGSTATUSPARAMS
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
req.alt-api: RILSETCALLFORWARDINGSTATUSPARAMS
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
req.typenames: RILSETCALLFORWARDINGSTATUSPARAMS, *LPRILSETCALLFORWARDINGSTATUSPARAMS
req.product: Windows 10 or later.
---

# RILSETCALLFORWARDINGSTATUSPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSETCALLFORWARDINGSTATUSPARAMS {
  DWORD                            dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON  dwReason;
  BOOL                             fAllClasses;
  DWORD                            dwInfoClasses;
  RILSERVICESETTINGSSTATUS         dwStatus;
} RILSETCALLFORWARDINGSTATUSPARAMS, RILSETCALLFORWARDINGSTATUSPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwReason


### -field fAllClasses


### -field dwInfoClasses


### -field dwStatus


## -remarks
