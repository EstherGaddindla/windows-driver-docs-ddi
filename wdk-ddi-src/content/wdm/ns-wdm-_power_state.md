---
UID: NS:wdm._POWER_STATE
title: _POWER_STATE
author: windows-driver-content
description: The POWER_STATE union specifies a system power state value or a device power state value.
old-location: kernel\power_state.htm
old-project: kernel
ms.assetid: c3730035-74fc-421a-89dc-7411e53950f5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _POWER_STATE, *PPOWER_STATE, POWER_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: POWER_STATE
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: *PPOWER_STATE, POWER_STATE
req.product: Windows 10 or later.
---

# _POWER_STATE structure



## -description
The <b>POWER_STATE</b> union specifies a <a href="https://msdn.microsoft.com/bb30bc89-d1f2-4cb3-bcfb-fb76c69dba27">system power state</a> value or a device power state value.



## -syntax

````
typedef union _POWER_STATE {
  SYSTEM_POWER_STATE SystemState;
  DEVICE_POWER_STATE DeviceState;
} POWER_STATE, *PPOWER_STATE;
````


## -struct-fields

### -field SystemState

A system power state value of type <a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a>. 


### -field DeviceState

A device power state value of type <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>. 


## -remarks
The <b>POWER_STATE</b> union is used in conjunction with the <a href="..\wdm\ne-wdm-_power_state_type.md">POWER_STATE_TYPE</a> enumeration type to specify a system power state value or a device power state value. This union is also used in cases where the power state type is implicitly determined by the context in which it is used. For example, see <a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a> and <a href="..\ntifs\nf-ntifs-posetpowerstate.md">PoSetPowerState</a>.

For more information about power management, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548108">Introduction to Power Management</a>.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-posetpowerstate.md">PoSetPowerState</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_power_state_type.md">POWER_STATE_TYPE</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POWER_STATE union%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

