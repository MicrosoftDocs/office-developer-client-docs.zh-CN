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
ms.openlocfilehash: fd0f25f20c9e628a80d27f2b70e01dacc98229b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778578"
---
# <a name="property-types"></a>属性类型

  
  
**适用于**： Outlook 
  
MAPI 支持单值和多值属性。 与单值属性，没有基类型的属性的值。 与多值属性，有多个基类型的值。 
  
下表中描述了 MAPI 支持的单值和多值属性类型。 对于每个具有相应的多值类型的单值类型，多值类型出现在括号之后的单值类型。
  
|**属性类型**|**十六进制值**|**说明**|
|:-----|:-----|:-----|
|PT_UNSPECIFIED  <br/> |0000  <br/> |指示属性类型未知。 此属性类型与接口方法保留供使用。  <br/> |
|PT_NULL  <br/> |0001  <br/> |指示没有属性值。 此属性类型仅供与接口方法一起使用，是 OLE 相同键入 VT_NULL。  <br/> |
|PT_I2 (PT_MV_I2)  <br/> |0002  <br/> |有符号整数 16 位 （双字节）。 PT_SHORT (PT_MV_SHORT) 和 OLE 键入 VT_I2 时，此属性类型都是相同的。  <br/> |
|PT_I4 (PT_MV_I4)  <br/> |0003  <br/> |签名或无符号整数位 （4 个字节）。 PT_LONG (PT_MV_LONG) 和 OLE 键入 vt_i4 类型时，此属性类型都是相同的。  <br/> |
|PT_FLOAT (PT_MV_FLOAT)  <br/> |0004  <br/> |32 位 （8 个字节） 浮点值。 此属性类型是 PT_R4 相同 (PT_MV_R4) 和 OLE 类型 VT_R4。  <br/> |
|PT_DOUBLE (PT_MV_DOUBLE)  <br/> |0005  <br/> |64 位 （8 个字节） 浮点值。 此属性类型为 PT_R8 和 VT_R8 和 VT_DOUBLE OLE 类型相同。  <br/> |
|PT_CURRENCY (PT_MV_CURRENCY)  <br/> |0006  <br/> |64 位 （8 个字节） 整数解释为小数。 此属性类型与 Microsoft Visual Basic 货币类型兼容且 OLE 相同键入 VT_CY。  <br/> |
|PT_APPTIME (PT_MV_APPTIME)  <br/> |0007  <br/> |解释为日期和时间的 double 值。 整数部分是日期，小数部分是时间。 此属性类型与 OLE 类型 VT_DATE 相同，兼容的 Microsoft Visual Basic 时间表示形式。  <br/> |
|PT_ERROR  <br/> |000A  <br/> |SCODE 值;32 位 （4 个字节） 无符号的整数。 此属性类型为 OLE 类型 VT_ERROR 相同。  <br/> |
|PT_BOOLEAN (PT_MV_12)  <br/> |000B  <br/> |其中零等于**false**和非零值等于**true**16 位 （双字节） 布尔值。 此属性类型为 OLE 类型 VT_BOOL 相同。  <br/> |
|PT_OBJECT  <br/> |000D  <br/> |为实现**IUnknown**接口的对象的指针。 此属性类型为类似于多个 OLE 类型，如为 VT_UNKNOWN。  <br/> |
|PT_I8 (PT_MV_I8)  <br/> |0014  <br/> |签名或无符号 64 位 （8 个字节） 整数使用**LARGE_INTEGER**结构。 PT_I8 和 OLE 键入 VT_I8 时，此属性类型都是相同的。  <br/> |
|PT_STRING8 (PT_MV_STRING8)  <br/> |001E  <br/> |Null 结尾的 8 位 （双字节） 字符的字符串。 此属性类型为 OLE 类型 VT_LPSTR 相同。  <br/> |
|PT_TSTRING (PT_MV_TSTRING)  <br/> |001F  <br/> |Null 结尾 16 位 （双字节） 字符的字符串。 与此类型的属性具有不使用 UNICODE 符号编译时重置到 PT_UNICODE UNICODE 符号开头编译时和 PT_STRING8 属性类型。 此属性类型是相同的 OLE 类型 VT_LPSTR 生成 PT_STRING8 属性和 VT_LPWSTR PT_UNICODE 属性  <br/> |
|PT_SYSTIME (PT_MV_SYSTIME)  <br/> |0040  <br/> |64 位 （8 个字节） 整数**FILETIME**结构的表单中日期和时间值。 此属性类型为 OLE 类型 VT_FILETIME 相同。  <br/> |
|PT_CLSID (PT_MV_CLSID)  <br/> |0048  <br/> |**CLSID**结构值。 此属性类型为 OLE 类型 VT_CLSID 相同。  <br/> |
|PT_SVREID  <br/> |00FB  <br/> |变量大小后, 跟一个 16 位 （双字节）**计数**。  <br/> |
|PT_SRESTRICT  <br/> |00FD  <br/> |变量大小，表示一个或多个限制结构的字节数组。  <br/> |
|PT_ACTIONS  <br/> |00FE  <br/> |变量的大小，16 位 （双字节）**计数**的操作 （而不是字节） 后跟的许多规则操作结构。  <br/> |
|PT_BINARY (PT_MV_BINARY)  <br/> |0102  <br/> |**SBinary**结构值，计数的字节数组。  <br/> |
   
> [!NOTE]
> 若要确定多值的属性类型或 PT_MV 的十六进制值为十六进制值的属性的标志 (0x00001000) 键入。 例如，PT_MV_UNICODE 的十六进制值是 0x101F 和 PT_MV_BINARY 的十六进制值是 0x1102。 
  

