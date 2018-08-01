---
title: FPropContainsProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FPropContainsProp
api_type:
- COM
ms.assetid: 43da5b59-7691-49aa-b83c-753d43bfd8fd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: abf33e4167d836aeb88fdefb30ba05840e80ce63
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774989"
---
# <a name="fpropcontainsprop"></a>FPropContainsProp

**适用于**： Outlook 
  
比较两个属性值，通常是字符串或二进制数组，如果一个包含其他。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
BOOL FPropContainsProp(
  LPSPropValue lpSPropValueDst,
  LPSPropValue lpSPropValueSrc,
  ULONG ulFuzzyLevel
);
```

## <a name="parameters"></a>参数

_lpSPropValueDst_
  
> [in]指向[SPropValue](spropvalue.md)结构定义可能包含指向由_lpSPropValueSrc_参数的搜索字符串的属性值的指针。 
    
_lpSPropValueSrc_
  
> [in]指向_lpSPropValueDst_参数指向属性值中定义的搜索字符串的查找**FPropContainsProp** **SPropValue**结构。 
    
_ulFuzzyLevel_
  
> [in]选项设置定义的 preciseness 级别比较中使用。 

  - **低 16 位**PT_BINARY 和 PT_STRING8 于类型的属性。 它们必须设置为完全下列值之一：
      
    - FL_FULLSTRING: _lpSPropValueSrc_搜索字符串必须由_lpSPropValueDst_标识该属性值等于。
        
    - FL_PREFIX: _lpSPropValueSrc_搜索字符串必须由_lpSPropValueDst_标识该属性值的开始处出现。 应仅最由_lpSPropValueSrc_搜索字符串的长度比较两个值。 
        
    - FL_SUBSTRING: _lpSPropValueSrc_搜索字符串必须包含无处不在由_lpSPropValueDst_标识该属性值。 
      
  - **高 16 位**仅适用于 PT_STRING8 类型的属性。 它们可以设置为下列值的任意组合：
    
    - FL_IGNORECASE： 无需考虑区分大小写，应进行比较。 
        
    - FL_IGNORENONSPACE： 比较结果应忽略如音符 Unicode 定义无空格字符。 
        
    - FL_LOOSE： 比较结果应指示忽略大小写匹配尽可能敏感性和无空格字符。
    
## <a name="return-value"></a>返回值

TRUE 
  
> 参数是否所有有效且包含_lpSPropValueSrc_搜索字符串中的_lpSPropValueDst_属性值指定。 
    
FALSE 
  
> 要比较的属性值不是类型 PT_STRING8 或 PT_BINARY、 的属性值是不同类型的或不包含_lpSPropValueSrc_搜索字符串中的_lpSPropValueDst_属性值指定。 
    
## <a name="remarks"></a>说明

比较方法取决于[SPropValue](spropvalue.md)属性定义中指定的属性类型和_ulFuzzyLevel_参数中提供的级别模糊推断方法。 [FPropCompareProp](fpropcompareprop.md)和**FPropContainsProp**函数可以用于准备用于生成表的限制。 
  
属性类型 PT_BINARY 忽略_ulFuzzyLevel_高 16 位。 缺失或无效_ulFuzzyLevel_中的设置时，执行完全字符串完全匹配。 有关属性包容详细信息，请参阅[SContentRestriction](scontentrestriction.md)结构。 
  

