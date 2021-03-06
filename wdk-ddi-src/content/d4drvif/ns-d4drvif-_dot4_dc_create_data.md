---
UID: NS:d4drvif._DOT4_DC_CREATE_DATA
title: _DOT4_DC_CREATE_DATA
author: windows-driver-content
description: Defines the DOT4_DC_CREATE_DATA construct.
old-location: print\dot4_dc_create_data.htm
old-project: print
ms.assetid: 9C21732B-0AB1-4F3E-8F3D-F0B12007920A
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _DOT4_DC_CREATE_DATA, DOT4_DC_CREATE_DATA, *PDOT4_DC_CREATE_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d4drvif.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT4_DC_CREATE_DATA
req.alt-loc: D4drvif.h
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
req.typenames: DOT4_DC_CREATE_DATA, *PDOT4_DC_CREATE_DATA
---

# _DOT4_DC_CREATE_DATA structure



## -description
Defines the <b>DOT4_DC_CREATE_DATA</b> construct.



## -syntax

````
typedef struct _DOT4_DC_CREATE_DATA {
  unsigned char bPsid;
  CHAR          pServiceName[MAX_SERVICE_LENGTH + 1];
  unsigned char bType;
  ULONG         ulBufferSize;
  USHORT        usMaxHtoPPacketSize;
  USHORT        usMaxPtoHPacketSize;
  unsigned char bHsid;
} DOT4_DC_CREATE_DATA, *PDOT4_DC_CREATE_DATA;
````


## -struct-fields

### -field bPsid

Specifies this or the service name sent.


### -field pServiceName

Describes the <b>CHAR</b>  member <b>pServiceName</b>.


### -field bType

Specifies the type, stream or packet, of channels on the socket.


### -field ulBufferSize

Specifies the size of the read buffer for channels on socket.


### -field usMaxHtoPPacketSize

Describes the <b>USHORT</b> member <b>usMaxHtoPPacketSize</b>.


### -field usMaxPtoHPacketSize

Describes the <b>USHORT</b> member <b>usMaxPtoHPacketSize</b>.


### -field bHsid

Specifies the host socket ID returned.


## -remarks
