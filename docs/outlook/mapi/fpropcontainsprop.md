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
ms.openlocfilehash: ea56996ad56bb4ce93d103a75eba2c29e6059a87
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328040"
---
# <a name="fpropcontainsprop"></a>FPropContainsProp

**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个属性值 (通常为字符串或二进制数组), 以查看是否有一个属性值包含另一个。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
BOOL FPropContainsProp(
  LPSPropValue lpSPropValueDst,
  LPSPropValue lpSPropValueSrc,
  ULONG ulFuzzyLevel
);
```

## <a name="parameters"></a>参数

_lpSPropValueDst_
  
> 实时指向[SPropValue](spropvalue.md)结构的指针, 该结构定义可能包含由_lpSPropValueSrc_参数指向的搜索字符串的属性值。 
    
_lpSPropValueSrc_
  
> 实时指向**SPropValue**结构的指针, 该结构定义**FPropContainsProp**在由_lpSPropValueDst_参数指向的属性值中查找的搜索字符串。 
    
_ulFuzzyLevel_
  
> 实时用于定义要在比较中使用的 preciseness 级别的选项设置。 

  - **较低的16位**适用于类型 PT_BINARY 和 PT_STRING8 的属性。 必须将它们完全设置为以下值之一:
      
    - FL_FULLSTRING: _lpSPropValueSrc_搜索字符串必须等于_lpSPropValueDst_标识的属性值。
        
    - FL_PREFIX: _lpSPropValueSrc_搜索字符串必须出现在_lpSPropValueDst_标识的属性值的开头。 这两个值只应与_lpSPropValueSrc_指示的搜索字符串的长度进行比较。 
        
    - FL_SUBSTRING: _lpSPropValueSrc_搜索字符串必须包含在_lpSPropValueDst_标识的属性值中的任何位置。 
      
  - **较高的16位**仅适用于 PT_STRING8 类型的属性。 可以通过任意组合将它们设置为以下值:
    
    - FL_IGNORECASE: 应进行比较, 而不考虑区分大小写。 
        
    - FL_IGNORENONSPACE: 比较操作应忽略 Unicode 定义的非空格字符, 如变音标记。 
        
    - FL_LOOSE: 如果可能, 比较应指示匹配项, 忽略区分大小写和非空格字符。
    
## <a name="return-value"></a>返回值

TRUE 
  
> 参数都是有效的, 并且_lpSPropValueSrc_搜索字符串包含在_lpSPropValueDst_属性值中指定的。 
    
FALSE 
  
> 要比较的属性值不是类型 PT_STRING8 或 PT_BINARY, 属性值的类型不同, 或者_lpSPropValueSrc_搜索字符串不包含在_lpSPropValueDst_属性值中指定的情况下。 
    
## <a name="remarks"></a>注解

比较方法取决于在[SPropValue](spropvalue.md)属性定义中指定的属性类型以及_ulFuzzyLevel_参数中提供的模糊级别试探法。 [FPropCompareProp](fpropcompareprop.md)和**FPropContainsProp**函数可用于准备生成表的限制。 
  
对于属性类型 PT_BINARY, 将忽略_ulFuzzyLevel_的高16位。 如果_ulFuzzyLevel_中的设置缺失或无效, 则执行完全字符串完全匹配。 有关属性控制的详细信息, 请参阅[SContentRestriction](scontentrestriction.md)结构。 
  

