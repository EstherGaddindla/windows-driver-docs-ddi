---
UID: NS:ehstorbandmgmt._BAND_TABLE_ENTRY
title: _BAND_TABLE_ENTRY
author: windows-driver-content
description: Banding information entries in BAND_TABLE are represented as BAND_TABLE_ENTRY structures. These entries contain location and security properties for a band configuration.
old-location: storage\band_table_entry.htm
old-project: storage
ms.assetid: 6956327E-5407-4771-9BB9-F59D752A5410
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _BAND_TABLE_ENTRY, BAND_TABLE_ENTRY, *PBAND_TABLE_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BAND_TABLE_ENTRY
req.alt-loc: EhStorBandMgmt.h
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
req.typenames: BAND_TABLE_ENTRY, *PBAND_TABLE_ENTRY
---

# _BAND_TABLE_ENTRY structure



## -description
Banding information entries in <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table.md">BAND_TABLE</a> are represented as <b>BAND_TABLE_ENTRY</b> structures. These entries contain location and security properties for a band configuration.



## -syntax

````
typedef struct _BAND_TABLE_ENTRY {
  ULONG              BandId;
  BAND_LOCATION_INFO LocationInfo;
  BAND_SECURITY_INFO SecurityInfo;
} BAND_TABLE_ENTRY, *PBAND_TABLE_ENTRY;
````


## -struct-fields

### -field BandId

The band identifier for a configured band on a storage device.


### -field LocationInfo

The band location information.


### -field SecurityInfo

The band security information. This includes encryption algorithm information when selected in <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">ENUMERATE_BANDS_PARAMETERS</a>.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_location_info.md">BAND_LOCATION_INFO</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table.md">BAND_TABLE</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">ENUMERATE_BANDS_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20BAND_TABLE_ENTRY structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

