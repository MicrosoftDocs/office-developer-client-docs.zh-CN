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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433526"
---
# <a name="spropvalue"></a>SPropValue

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述 MAPI 属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[](change_prop_type.md)CHANGE_PROP_TYPE、MVI_PROP、PROP_ID、PROP_TAG、PROP_TYPE [](prop_id.md) [](mvi_prop.md) [](prop_tag.md) [](prop_type.md) <br/> |
   
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
  
> 属性的属性标记。 属性标记是 32 位无符号整数，由该属性在高顺序 16 位中的唯一标识符和低顺序 16 位中的属性类型组成。
    
 **dwAlignPad**
  
> 保留用于 MAPI;请勿使用。 
    
 **值**
  
> 数据值联合，由属性类型指示的特定值。 下表列出了每种属性类型、应该使用的联合成员及其关联的数据类型。
    
|**属性类型**|**值**|**Value 的数据类型**|
|:-----|:-----|:-----|
|PT_I2 或 PT_SHORT  <br/> |**i** <br/> |short int  <br/> |
|PT_I4或PT_LONG (签名)   <br/> |**l** <br/> |LONG  <br/> |
|PT_I4或PT_LONG (未签名)   <br/> |**ul** <br/> |ULONG  <br/> |
|PT_R4 或 PT_FLOAT  <br/> |**flt** <br/> |float  <br/> |
|PT_R8 或 PT_DOUBLE  <br/> |**dbl** <br/> |double  <br/> |
|PT_BOOLEAN  <br/> |**b** <br/> |unsigned short int  <br/> |
|PT_CURRENCY  <br/> |**cur** <br/> |[CURRENCY](currency.md) <br/> |
|PT_APPTIME  <br/> |**at** <br/> |double  <br/> |
|PT_SYSTIME  <br/> |**ft** <br/> |[FILETIME](filetime.md) <br/> |
|PT_STRING8  <br/> |**lpszA** <br/> |LPSTR  <br/> |
|PT_BINARY  <br/> |**bin** <br/> |BYTE [array]  <br/> |
|PT_UNICODE  <br/> |**lpszW** <br/> |LPWSTR  <br/> |
|PT_CLSID  <br/> |**lpguid** <br/> |LPGUID  <br/> |
|PT_I8 或 PT_LONGLONG  <br/> |**li** <br/> |**LARGE_INTEGER** <br/> |
|PT_MV_I2  <br/> |**MVi** <br/> |[SShortArray](sshortarray.md) <br/> |
|PT_MV_LONG  <br/> |**MVI** <br/> |[SLongArray](slongarray.md) <br/> |
|PT_MV_R4  <br/> |**MLt** <br/> |[SRealArray](srealarray.md) <br/> |
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
|PT_NULL 或 PT_OBJECT  <br/> |**x** <br/> |LONG  <br/> |
|PT_PTR  <br/> |**lpv** <br/> |VOID \*  <br/> |
   
## <a name="remarks"></a>备注

**ulPropTag** 成员由两部分组成： 
  
- 高顺序 16 位中的标识符。
    
- 低顺序 16 位中的类型。
    
标识符是特定范围内的数值。 MAPI 为标识符定义范围，以描述属性用于什么以及谁负责维护它。 MAPI 为 Mapitags.h 头文件中支持的每个属性标记定义约束。
  
类型指示属性值的格式。 MAPI 为 Mapidefs.h 头文件中支持的每个属性类型定义常量。 
  
有关标识符和属性类型的有效属性范围的完整列表，请参阅属性 [标识符和类型](property-identifiers-and-types.md) 附录。 
  
**dwAlignPad** 成员用作填充，以确保在需要 8 字节对齐的 8 字节值的计算机上正确对齐。 在此类计算机上编写代码的开发人员应该使用在 8 字节边界上分配 **SPropValue** 数组的内存分配例程。 
  
有关详细信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)[和更新 MAPI 属性](updating-mapi-properties.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

