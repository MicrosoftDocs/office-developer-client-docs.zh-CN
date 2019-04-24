---
title: SPropValue
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropValue
api_type:
- COM
ms.assetid: faf795a2-84db-432d-a05f-082f25a5cab5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c7f4e8835831af6277cef134bf3961e9928cba33
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326584"
---
# <a name="spropvalue"></a>SPropValue

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述 MAPI 属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[CHANGE_PROP_TYPE](change_prop_type.md)、 [MVI_PROP](mvi_prop.md)、 [PROP_ID](prop_id.md)、 [PROP_TAG](prop_tag.md)、 [PROP_TYPE](prop_type.md) <br/> |
   
```cpp
typedef struct _SPropValue
{
  ULONG ulPropTag;
  ULONG dwAlignPad;
  union _PV Value;
} SPropValue, FAR *LPSPropValue;

```

## <a name="members"></a>Members

 **ulPropTag**
  
> 属性的属性标记。 属性标记是32位无符号整数, 由高序位16位中的属性唯一标识符和低序位16位中的属性类型组成。
    
 **dwAlignPad**
  
> 为 MAPI 保留;请勿使用。 
    
 **值**
  
> 数据值的联合, 由属性类型指定的特定值。 下表列出了每个属性类型、应使用的联合的成员及其关联的数据类型。
    
|**属性类型**|**值**|**值的数据类型**|
|:-----|:-----|:-----|
|PT_I2 或 PT_SHORT  <br/> |**得到** <br/> |短整型  <br/> |
|PT_I4 或 PT_LONG (已签名)  <br/> |**l** <br/> |大量  <br/> |
|PT_I4 或 PT_LONG (无符号)  <br/> |**列名** <br/> |ULONG  <br/> |
|PT_R4 或 PT_FLOAT  <br/> |**flt** <br/> |float  <br/> |
|PT_R8 或 PT_DOUBLE  <br/> |**双** <br/> |double  <br/> |
|PT_BOOLEAN  <br/> |**黑白** <br/> |无符号短整型  <br/> |
|PT_CURRENCY  <br/> |**选用** <br/> |[CURRENCY](currency.md) <br/> |
|PT_APPTIME  <br/> |**个** <br/> |double  <br/> |
|PT_SYSTIME  <br/> |**ft** <br/> |[FILETIME](filetime.md) <br/> |
|PT_STRING8  <br/> |**lpszA** <br/> |LPSTR  <br/> |
|PT_BINARY  <br/> |**区间** <br/> |BYTE [array]  <br/> |
|PT_UNICODE  <br/> |**lpszW** <br/> |LPWSTR  <br/> |
|PT_CLSID  <br/> |**lpguid** <br/> |LPGUID  <br/> |
|PT_I8 或 PT_LONGLONG  <br/> |**i** <br/> |**LARGE_INTEGER** <br/> |
|PT_MV_I2  <br/> |**MVi** <br/> |[SShortArray](sshortarray.md) <br/> |
|PT_MV_LONG  <br/> |**MVI** <br/> |[SLongArray](slongarray.md) <br/> |
|PT_MV_R4  <br/> |**MVflt** <br/> |[SRealArray](srealarray.md) <br/> |
|PT_MV_DOUBLE  <br/> |**MVdbl** <br/> |[SDoubleArray](sdoublearray.md) <br/> |
|PT_MV_CURRENCY  <br/> |**MVcur** <br/> |[SCurrencyArray](scurrencyarray.md) <br/> |
|PT_MV_APPTIME  <br/> |**MVat** <br/> |[SAppTimeArray](sapptimearray.md) <br/> |
|PT_MV_SYSTIME  <br/> |**MVft** <br/> |[SDateTimeArray](sdatetimearray.md) <br/> |
|PT_MV_BINARY  <br/> |**MVbin** <br/> |[SBinaryArray](sbinaryarray.md) <br/> |
|PT_MV_STRING8  <br/> |**MVszA** <br/> |[SLPSTRArray](slpstrarray.md) <br/> |
|PT_MV_UNICODE  <br/> |**MVszW** <br/> |[SWStringArray](swstringarray.md) <br/> |
|PT_MV_CLSID  <br/> |**MVguid** <br/> |[SGuidArray](sguidarray.md) <br/> |
|PT_MV_I8  <br/> |**MVli** <br/> |[SLargeIntegerArray](slargeintegerarray.md) <br/> |
|PT_ERROR  <br/> |**err** <br/> |[SCODE](scode.md) <br/> |
|PT_NULL 或 PT_OBJECT  <br/> |**x** <br/> |大量  <br/> |
|PT_PTR  <br/> |**lpv** <br/> |作废\*  <br/> |
   
## <a name="remarks"></a>注解

**ulPropTag**成员由两部分组成: 
  
- 高顺序16位中的标识符。
    
- 一个低序位16位的类型。
    
标识符是在特定范围内的一个数字值。 MAPI 为标识符定义范围, 以描述该属性的用途, 以及负责维护该属性的参与者。 MAPI 为在 Mapitags 头文件中支持的每个属性标记定义约束。
  
类型指示属性值的格式。 MAPI 为它在 mapidefs.h 头文件中支持的每个属性类型定义常量。 
  
有关标识符和属性类型的有效属性范围的完整列表, 请参阅[属性标识符和类型](property-identifiers-and-types.md)附录。 
  
**dwAlignPad**成员用作填充, 以确保在需要8字节对齐方式的计算机上进行正确的对齐8字节值。 在此类计算机上编写代码的开发人员应使用在8字节边界上分配**SPropValue**数组的内存分配例程。 
  
有关详细信息, 请参阅[mapi 属性类型概述](mapi-property-type-overview.md)和[更新 mapi 属性](updating-mapi-properties.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

