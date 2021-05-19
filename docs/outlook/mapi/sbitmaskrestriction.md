---
title: SBitMaskRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SBitMaskRestriction
api_type:
- COM
ms.assetid: ddd42180-6e4f-410c-9f78-d868a91452dc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: afac8c352ad0a07fcb1cd98683b6a5c87940ab4d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424474"
---
# <a name="sbitmaskrestriction"></a>SBitMaskRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述位掩码限制，该限制用于执行位 **AND** 操作并测试结果。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SBitMaskRestriction
{
  ULONG relBMR;
  PT_LONG ulPropTag;
  ULONG ulMask;
} SBitMaskRestriction;

```

## <a name="members"></a>Members

 **relBMR**
  
> 描述如何将 **ulMask** 成员中指定的掩码应用于属性标记的关系运算符。 可能的值如下所示： 
    
BMR_EQZ 
  
> 使用 **ulPropTag** 成员所代表的属性对 **ulMask** 成员中的掩码执行按位 **AND** 操作，并测试其等于零。 
    
BMR_NEZ 
  
> 使用 **ulPropTag** 成员所代表的属性对 **ulMask** 成员中的掩码执行按位 **AND** 操作，并测试其不等于零。 
    
 **ulPropTag**
  
> 应用位掩码的属性的属性标记。
    
 **ulMask**
  
> 要应用于由 **ulPropTag 标识的属性的位掩码**。
    
## <a name="remarks"></a>备注

**SBitMaskRestriction** 结构使用 **ulMask** 成员中描述的位掩码和 **ulPropTag** 成员描述的属性值执行按位 **AND** 操作。 如果结果为零，则BMR_EQZ结果。 如果不是零，即，如果属性值至少具有一个设置为 **ulMask** 的相同位，则BMR_NEZ满足。
  
有关 **SBitMaskRestriction** 结构和限制的一般详细信息，请参阅关于 [限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

