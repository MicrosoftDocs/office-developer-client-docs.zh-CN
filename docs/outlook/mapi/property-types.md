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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328488"
---
# <a name="property-types"></a>属性类型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 支持单值和多值属性。 使用单值属性时, 属性的一个基本类型值。 对于多值属性, 有多个基类型的值。 
  
下表描述了 MAPI 支持的单值和多值属性类型。 对于每个具有相应的多值类型的单值类型, 多值类型将显示在单值类型后面的圆括号中。
  
|**属性类型**|**十六进制值**|**Description**|
|:-----|:-----|:-----|
|PT_UNSPECIFIED  <br/> |0000  <br/> |指示属性类型未知。 此属性类型保留以与接口方法一起使用。  <br/> |
|PT_NULL  <br/> |0001  <br/> |指示无属性值。 此属性类型将保留用于接口方法, 并且与 OLE 类型 VT_NULL 相同。  <br/> |
|PT_I2 (PT_MV_I2)  <br/> |0002  <br/> |带符号的16位 (2 字节) 整数。 此属性类型与 PT_SHORT (PT_MV_SHORT) 和 OLE 类型 VT_I2 相同。  <br/> |
|PT_I4 (PT_MV_I4)  <br/> |0003  <br/> |已签名或未签署的32位 (4 字节) 整数。 此属性类型与 PT_LONG (PT_MV_LONG) 和 OLE 类型 VT_I4 相同。  <br/> |
|PT_FLOAT (PT_MV_FLOAT)  <br/> |0004  <br/> |32位 (8 字节) 浮点值。 此属性类型与 PT_R4 (PT_MV_R4) 和 OLE 类型 VT_R4 相同。  <br/> |
|PT_DOUBLE (PT_MV_DOUBLE)  <br/> |0005  <br/> |64位 (8 字节) 浮点值。 此属性类型与 PT_R8 和 OLE 类型 VT_R8 和 VT_DOUBLE 相同。  <br/> |
|PT_CURRENCY (PT_MV_CURRENCY)  <br/> |0006  <br/> |64位 (8 字节) 整数, 被解释为 decimal。 此属性类型与 Microsoft Visual Basic 货币类型兼容, 并且与 OLE 类型 VT_CY 相同。  <br/> |
|PT_APPTIME (PT_MV_APPTIME)  <br/> |0007  <br/> |解释为日期和时间的双精度值。 整数部分是日期, 小数部分是时间。 此属性类型与 OLE 类型 VT_DATE 相同, 并且与 Microsoft Visual Basic 时间表示形式兼容。  <br/> |
|PT_ERROR  <br/> |000A  <br/> |SCODE 值;32位 (4 字节) 无符号整数。 此属性类型与 OLE 类型 VT_ERROR 相同。  <br/> |
|PT_BOOLEAN (PT_MV_12)  <br/> |000B  <br/> |16位 (2 字节) 布尔值, 其中零等于**false** , 非零等于**true**。 此属性类型与 OLE 类型 VT_BOOL 相同。  <br/> |
|PT_OBJECT  <br/> |000D  <br/> |指向实现**IUnknown**接口的对象的指针。 此属性类型类似于几种 OLE 类型, 如 VT_UNKNOWN。  <br/> |
|PT_I8 (PT_MV_I8)  <br/> |0014  <br/> |使用**LARGE_INTEGER**结构的已签名或未签署的64位 (8 字节) 整数。 此属性类型与 PT_I8 和 OLE 类型 VT_I8 相同。  <br/> |
|PT_STRING8 (PT_MV_STRING8)  <br/> |001E  <br/> |以空值终止的8位 (2 字节) 字符字符串。 此属性类型与 OLE 类型 VT_LPSTR 相同。  <br/> |
|PT_TSTRING (PT_MV_TSTRING)  <br/> |001F  <br/> |以空值终止的16位 (2 字节) 字符字符串。 使用 unicode 符号和 PT_STRING8 进行编译时, 具有此类型的属性的属性类型重置为 PT_UNICODE, 而不使用 unicode 符号编译。 此属性类型与生成的 PT_STRING8 属性和 VT_LPWSTR for PT_UNICODE 属性的 OLE 类型 VT_LPSTR 相同  <br/> |
|PT_SYSTIME (PT_MV_SYSTIME)  <br/> |0040  <br/> |64位 (8 字节) 整数数据和时间值, 格式为**FILETIME**结构。 此属性类型与 OLE 类型 VT_FILETIME 相同。  <br/> |
|PT_CLSID (PT_MV_CLSID)  <br/> |0048  <br/> |**CLSID**结构值。 此属性类型与 OLE 类型 VT_CLSID 相同。  <br/> |
|PT_SVREID  <br/> |00FB  <br/> |可变大小, 16 位 (2 字节)**计数**, 后跟结构。  <br/> |
|PT_SRESTRICT  <br/> |00FD  <br/> |可变大小, 表示一个或多个限制结构的字节数组。  <br/> |
|PT_ACTIONS  <br/> |00FE  <br/> |可变大小, 即16位 (2 字节) 操作**计数**(而不是字节), 后跟许多规则操作结构。  <br/> |
|PT_BINARY (PT_MV_BINARY)  <br/> |0102  <br/> |**SBinary**结构值, 一个计数字节数组。  <br/> |
   
> [!NOTE]
> 确定多值属性类型的十六进制值, 或属性类型的十六进制值的 PT_MV 标志 (0x00001000)。 例如, PT_MV_UNICODE 的十六进制值为 0x101F, PT_MV_BINARY 的十六进制值为0x1102。 
  

