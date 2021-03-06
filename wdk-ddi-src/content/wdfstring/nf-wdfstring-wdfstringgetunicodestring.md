---
UID: NF:wdfstring.WdfStringGetUnicodeString
title: WdfStringGetUnicodeString function
author: windows-driver-content
description: The WdfStringGetUnicodeString method retrieves the Unicode string that is assigned to a specified framework string object.
old-location: wdf\wdfstringgetunicodestring.htm
old-project: wdf
ms.assetid: 39041953-11ef-4f31-9b7e-09ce40b6b930
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfStringGetUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfstring.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfStringGetUnicodeString
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfStringGetUnicodeString function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfStringGetUnicodeString</b> method retrieves the Unicode string that is assigned to a specified framework string object.



## -syntax

````
VOID WdfStringGetUnicodeString(
  _In_  WDFSTRING       String,
  _Out_ PUNICODE_STRING UnicodeString
);
````


## -parameters

### -param String [in]

A handle to a framework string object.


### -param UnicodeString [out]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that receives a pointer to the Unicode string that is currently assigned to the string object that <i>String</i> specifies.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
After <b>WdfStringGetUnicodeString</b> returns, the UNICODE_STRING structure that <i>UnicodeString</i> points to contains a pointer to the specified string object's Unicode string, along with the string's length. The Unicode string is allocated in paged pool.

 The framework does not make a copy of the string for the driver.

For more information about framework string objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-string-objects">Using String Objects</a>.

The following code example obtains the Unicode string that is assigned to a specified framework string object.


## -see-also
<dl>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="..\wdfstring\nf-wdfstring-wdfstringcreate.md">WdfStringCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfStringGetUnicodeString method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

