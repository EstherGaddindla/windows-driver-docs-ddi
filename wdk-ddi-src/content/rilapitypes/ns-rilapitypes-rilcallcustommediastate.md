---
UID: NS:rilapitypes.RILCALLCUSTOMMEDIASTATE
title: RILCALLCUSTOMMEDIASTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallcustommediastate_2.htm
old-project: netvista
ms.assetid: 3c385208-992d-4a74-8382-4312f468300f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLCUSTOMMEDIASTATE, *LPRILCALLCUSTOMMEDIASTATE, RILCALLCUSTOMMEDIASTATE
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
req.alt-api: RILCALLCUSTOMMEDIASTATE
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
req.typenames: *LPRILCALLCUSTOMMEDIASTATE, RILCALLCUSTOMMEDIASTATE
req.product: Windows 10 or later.
---

# RILCALLCUSTOMMEDIASTATE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILCALLCUSTOMMEDIASTATE {
  DWORD [1] dwCustomStateSpecific;
} RILCALLCUSTOMMEDIASTATE, RILCALLCUSTOMMEDIASTATE;
````


## -struct-fields

### -field dwCustomStateSpecific


## -remarks
