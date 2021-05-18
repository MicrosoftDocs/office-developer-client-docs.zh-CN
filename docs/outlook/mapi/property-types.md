---
title: 属性类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 71967150-1005-4c85-90f1-76fc7876c0d0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 43b0090192a2f9b02acee4edf471c5ae6c6de7e8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407051"
---
# <a name="property-types"></a>属性类型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 支持单值和多值属性。 对于单值属性，该属性有一个基类型的值。 对于多值属性，基类型有多个值。 
  
下表介绍了 MAPI 支持的单值和多值属性类型。 对于具有相应多值类型的每个单值类型，多值类型显示在单值类型后的括号中。
  
|**属性类型**|**十六进制值**|**说明**|
|:-----|:-----|:-----|
|PT_UNSPECIFIED  <br/> |0000  <br/> |指示属性类型未知。 保留此属性类型以用于接口方法。  <br/> |
|PT_NULL  <br/> |0001  <br/> |指示没有属性值。 此属性类型保留用于接口方法，并且与 OLE 类型属性VT_NULL。  <br/> |
|PT_I2 (PT_MV_I2)   <br/> |0002  <br/> |有符号 16 位 (2 字节) 整数。 此属性类型与属性类型PT_SHORT (PT_MV_SHORT) OLE 类型VT_I2。  <br/> |
|PT_I4 (PT_MV_I4)   <br/> |0003  <br/> |有符号或无符号的 32 位 (4 字节) 整数。 此属性类型与属性类型PT_LONG (PT_MV_LONG) OLE 类型VT_I4。  <br/> |
|PT_FLOAT (PT_MV_FLOAT)   <br/> |0004  <br/> |32 位 (8 字节) 浮点值。 此属性类型与属性类型PT_R4 (PT_MV_R4) OLE 类型VT_R4。  <br/> |
|PT_DOUBLE (PT_MV_DOUBLE)   <br/> |0005  <br/> |64 位 (8 字节) 浮点值。 此属性类型与属性类型PT_R8 OLE 类型VT_R8和 VT_DOUBLE。  <br/> |
|PT_CURRENCY (PT_MV_CURRENCY )   <br/> |0006  <br/> |64 位 (8 字节) 解释为十进制的整数。 此属性类型与 Microsoft Visual Basic CURRENCY 类型兼容，并且与 OLE 类型类型VT_CY。  <br/> |
|PT_APPTIME (PT_MV_APPTIME)   <br/> |0007  <br/> |解释为日期和时间的双精度值。 整数部分为日期，小数部分为时间。 此属性类型与 OLE 类型类型VT_DATE，并且与 Microsoft Visual Basic表示形式兼容。  <br/> |
|PT_ERROR  <br/> |000A  <br/> |SCODE 值;32 位 (4 字节) 无符号整数。 此属性类型与 OLE 类型的值VT_ERROR。  <br/> |
|PT_BOOLEAN (PT_MV_12)   <br/> |000B  <br/> |16 位 (2 字节) 布尔值，其中零等于 **false，** 非零等于 **true**。 此属性类型与 OLE 类型值相同VT_BOOL。  <br/> |
|PT_OBJECT  <br/> |000D  <br/> |指向实现 **IUnknown 接口的对象的** 指针。 此属性类型类似于多个 OLE 类型，如 VT_UNKNOWN。  <br/> |
|PT_I8 (PT_MV_I8)   <br/> |0014  <br/> |有符号或无符号的 64 位 (8 字节) ，该整数使用 LARGE_INTEGER **结构。** 此属性类型与属性类型PT_I8 OLE 类型VT_I8。  <br/> |
|PT_STRING8 (PT_MV_STRING8)   <br/> |001E  <br/> |以 Null 结尾的 8 位 (2 字节) 字符串。 此属性类型与 OLE 类型属性VT_LPSTR。  <br/> |
|PT_TSTRING (PT_MV_TSTRING)   <br/> |001F  <br/> |以 Null 结尾的 16 位 (2 字节) 字符串。 使用 UNICODE 符号编译时，此类型的属性PT_UNICODE属性类型重置为PT_STRING8 UNICODE 符号编译时属性类型重置为属性类型。 此属性类型与生成的属性的 OLE VT_LPSTR相同，PT_STRING8属性VT_LPWSTR OLE PT_UNICODE属性  <br/> |
|PT_SYSTIME (PT_MV_SYSTIME)   <br/> |0040  <br/> |64 位 (8 字节) FILETIME 结构形式的整数 **数据和时间** 值。 此属性类型与 OLE 类型属性VT_FILETIME。  <br/> |
|PT_CLSID (PT_MV_CLSID)   <br/> |0048  <br/> |**CLSID** 结构值。 此属性类型与 OLE 类型属性VT_CLSID。  <br/> |
|PT_SVREID  <br/> |00FB  <br/> |可变大小，一个 16 位 (2 字节) **COUNT** 后跟一个结构。  <br/> |
|PT_SRESTRICT  <br/> |00FD  <br/> |可变大小，表示一个或多个 Restriction 结构的字节数组。  <br/> |
|PT_ACTIONS  <br/> |00FE  <br/> |可变大小，16 位 (2 字节) **COUNT** 操作， (字节) 后跟许多规则操作结构。  <br/> |
|PT_BINARY (PT_MV_BINARY)   <br/> |0102  <br/> |**SBinary** 结构值，计数型字节数组。  <br/> |
   
> [!NOTE]
> 若要确定多值属性类型的 Hex 值，或将 PT_MV标志 (0x00001000) 属性类型的 Hex 值。 例如，PT_MV_UNICODE的 Hex 0x101F，而 PT_MV_BINARY 的 Hex 0x1102。 
  

