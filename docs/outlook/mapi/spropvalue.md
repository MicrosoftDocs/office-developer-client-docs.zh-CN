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
ms.openlocfilehash: 60528162917a8a383060adbcadefb610aa42ce32
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580969"
---
# <a name="spropvalue"></a>SPropValue

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
描述的 MAPI 属性。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[CHANGE_PROP_TYPE](change_prop_type.md)、 [MVI_PROP](mvi_prop.md)、 [PROP_ID](prop_id.md)、 [PROP_TAG](prop_tag.md)、 [PROP_TYPE](prop_type.md) <br/> |
   
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
  
> 属性标记属性。 属性标记是 32 位无符号的整数组成的属性中高阶 16 位的唯一标识符和低序位 16 位中的该属性的类型。
    
 **dwAlignPad**
  
> 供 MAPI;不要使用。 
    
 **值**
  
> 联合的数据值，指明属性类型的特定值。 下表列出了针对每个属性类型、 联合应使用的成员和其关联的数据类型。
    
|**属性类型**|**值**|**值的数据类型**|
|:-----|:-----|:-----|
|PT_I2 或 PT_SHORT  <br/> |**我** <br/> |short int  <br/> |
|PT_I4 或 PT_LONG （签名）  <br/> |**l** <br/> |长  <br/> |
|PT_I4 或 PT_LONG （无符号）  <br/> |**ul** <br/> |ULONG  <br/> |
|PT_R4 或 PT_FLOAT  <br/> |**flt** <br/> |float  <br/> |
|PT_R8 或 PT_DOUBLE  <br/> |**双** <br/> |double  <br/> |
|PT_BOOLEAN  <br/> |**b** <br/> |未签署的简短 int  <br/> |
|PT_CURRENCY  <br/> |**当前** <br/> |[CURRENCY](currency.md) <br/> |
|PT_APPTIME  <br/> |**在** <br/> |double  <br/> |
|PT_SYSTIME  <br/> |**ft** <br/> |[FILETIME](filetime.md) <br/> |
|PT_STRING8  <br/> |**lpszA** <br/> |LPSTR  <br/> |
|PT_BINARY  <br/> |**回收站** <br/> |字节 [数组]  <br/> |
|PT_UNICODE  <br/> |**lpszW** <br/> |LPWSTR  <br/> |
|PT_CLSID  <br/> |**lpguid** <br/> |LPGUID  <br/> |
|PT_I8 或 PT_LONGLONG  <br/> |**li** <br/> |**LARGE_INTEGER** <br/> |
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
|PT_NULL 或 PT_OBJECT  <br/> |**x** <br/> |长  <br/> |
|PT_PTR  <br/> |**lpv** <br/> |VOID\*  <br/> |
   
## <a name="remarks"></a>注解

**UlPropTag**成员由两部分组成： 
  
- 中高阶 16 位的标识符。
    
- 低序位 16 位中的类型。
    
标识符是一个数值在特定范围内。 MAPI 定义标识符来描述属性用于和谁负责维护它的区域。 MAPI 属性标记它 Mapitags.h 头文件中所支持的每个定义的约束。
  
该类型指示该属性的值的格式。 MAPI 的属性类型，它支持 Mapidefs.h 头文件中的每个定义的常数。 
  
标识符和属性类型的有效属性范围的完整列表，请参阅附录[属性标识符和类型](property-identifiers-and-types.md)。 
  
**DwAlignPad**成员作为填充使用，以确保正确的对齐方式为 8 字节值需要 8 字节对齐的计算机上。 开发人员编写代码在该计算机上应使用分配**SPropValue**数组 8 字节边界上的内存分配例程。 
  
有关详细信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)和[更新 MAPI 属性](updating-mapi-properties.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

