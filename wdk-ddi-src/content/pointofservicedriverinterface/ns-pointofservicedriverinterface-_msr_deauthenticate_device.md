---
UID: NS:pointofservicedriverinterface._MSR_DEAUTHENTICATE_DEVICE
title: _MSR_DEAUTHENTICATE_DEVICE
author: windows-driver-content
description: This structure provides the information necessary to deauthenticate the device.
old-location: pos\msr_deauthenticate_device.htm
old-project: pos
ms.assetid: 7174a342-de02-4a3c-8bb9-9c86e7f4b5e1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MSR_DEAUTHENTICATE_DEVICE, MSR_DEAUTHENTICATE_DEVICE, *PMSR_DEAUTHENTICATE_DEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MSR_DEAUTHENTICATE_DEVICE
req.alt-loc: PointOfServiceDriverInterface.h
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
req.typenames: MSR_DEAUTHENTICATE_DEVICE, *PMSR_DEAUTHENTICATE_DEVICE
---

# _MSR_DEAUTHENTICATE_DEVICE structure



## -description
This structure provides the information necessary to deauthenticate the device.



## -syntax

````
typedef struct _MSR_DEAUTHENTICATE_DEVICE {
  unsigned char Challenge2[MSR_CHALLENGE_SIZE];
} MSR_DEAUTHENTICATE_DEVICE, *PMSR_DEAUTHENTICATE_DEVICE;
````


## -struct-fields

### -field Challenge2

The challenge token used to deauthenticate the device.


## -remarks
