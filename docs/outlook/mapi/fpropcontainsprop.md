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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432629"
---
# <a name="fpropcontainsprop"></a>FPropContainsProp

**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个属性值（通常是字符串或二进制数组）以查看其中一个是否包含另一个。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
BOOL FPropContainsProp(
  LPSPropValue lpSPropValueDst,
  LPSPropValue lpSPropValueSrc,
  ULONG ulFuzzyLevel
);
```

## <a name="parameters"></a>参数

_lpSPropValueDst_
  
> [in]指向 [SPropValue](spropvalue.md) 结构的指针，该结构定义可能包含  _由 lpSPropValueSrc_ 参数指向的搜索字符串的属性值。 
    
_lpSPropValueSrc_
  
> [in]指向 **SPropValue** 结构的指针，该结构定义 **FPropContainsProp** 在  _lpSPropValueDst_ 参数指向的属性值中查找的搜索字符串。 
    
_ulFuzzyLevel_
  
> [in]定义要用于比较的精度级别的选项设置。 

  - 较低的 **16 位** 适用于 PT_BINARY 和 PT_STRING8。 必须完全设置为以下值之一：
      
    - _FL_FULLSTRING：lpSPropValueSrc_ 搜索字符串必须等于 _由 lpSPropValueDst 标识的属性值_。
        
    - _FL_PREFIX：lpSPropValueSrc_ 搜索字符串必须出现在 _由 lpSPropValueDst 标识的属性值的开头_。 这两个值应仅与  _lpSPropValueSrc_ 指示的搜索字符串的长度进行比较。 
        
    - _FL_SUBSTRING：lpSPropValueSrc_ 搜索字符串必须包含在 _由 lpSPropValueDst_ 标识的属性值中的任何位置。 
      
  - 上面的 **16 位** 仅适用于类型为 PT_STRING8。 可以任意组合方式将这些值设置为以下值：
    
    - FL_IGNORECASE：应在不考虑区分大小写的情况下进行比较。 
        
    - FL_IGNORENONSPACE：比较应忽略 Unicode 定义的非区域字符，如音调符号。 
        
    - FL_LOOSE：比较应尽可能指示匹配，忽略区分大小写和非空格字符。
    
## <a name="return-value"></a>返回值

TRUE 
  
> 参数全部有效  _，lpSPropValueSrc_ 搜索字符串包含在  _lpSPropValueDst_ 属性值中指定。 
    
FALSE 
  
> 进行比较的属性值的类型不是 PT_STRING8 或 PT_BINARY，属性值是不同类型的，或者  _lpSPropValueSrc_ 搜索字符串未包含在  _lpSPropValueDst_ 属性值中指定。 
    
## <a name="remarks"></a>备注

比较方法取决于 [SPropValue](spropvalue.md) 属性定义中指定的属性类型和  _ulFuzzyLevel_ 参数中提供的模糊级别启发。 [FPropCompareProp](fpropcompareprop.md)和 **FPropContainsProp** 函数可用于准备生成表的限制。 
  
对于属性类型属性类型，将忽略  _ulFuzzyLevel_ 的 16 位PT_BINARY。 如果  _ulFuzzyLevel_ 中的设置缺失或无效，将执行完全字符串完全匹配。 有关属性包含性详细信息，请参阅 [SContentRestriction](scontentrestriction.md) 结构。 
  

