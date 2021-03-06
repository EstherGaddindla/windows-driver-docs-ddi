---
UID: NS:rilapitypes.RILPROVISIONSTATUS
title: RILPROVISIONSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilprovisionstatus_2.htm
old-project: netvista
ms.assetid: 59568338-6718-4f3e-bcf6-cd284e68e6af
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILPROVISIONSTATUS, RILPROVISIONSTATUS, *LPRILPROVISIONSTATUS
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
req.alt-api: RILPROVISIONSTATUS
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
req.typenames: RILPROVISIONSTATUS, *LPRILPROVISIONSTATUS
req.product: Windows 10 or later.
---

# RILPROVISIONSTATUS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILPROVISIONSTATUS {
  DWORD                              cbSize;
  DWORD                              dwExecutor;
  RILPROVISIONSTATUSPROVISIONSTATUS  dwProvisionStatus;
} RILPROVISIONSTATUS, RILPROVISIONSTATUS;
````


## -struct-fields

### -field cbSize


### -field dwExecutor


### -field dwProvisionStatus


## -remarks
