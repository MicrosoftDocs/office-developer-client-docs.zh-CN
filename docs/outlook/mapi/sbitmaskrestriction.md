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
ms.openlocfilehash: c9197201388530bd7755eb1987ecc863220e3847
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566605"
---
# <a name="sbitmaskrestriction"></a>SBitMaskRestriction

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
描述一个位掩码限制，用来执行按位**AND**操作和测试结果。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 介绍如何在**ulMask**成员中指定的掩码应应用到属性标记的关系运算符。 可能值如下所示： 
    
BMR_EQZ 
  
> 使用由**ulPropTag**成员和检验值等于零的属性**ulMask**成员中执行按位**AND**运算的掩码。 
    
BMR_NEZ 
  
> 使用由**ulPropTag**成员和测试的值不等于零的属性**ulMask**成员中执行按位**AND**运算的掩码。 
    
 **ulPropTag**
  
> 属性标记的位掩码应用到的属性。
    
 **ulMask**
  
> 要应用于由**ulPropTag**标识属性的位掩码。
    
## <a name="remarks"></a>注解

**SBitMaskRestriction**结构执行按位**AND**操作使用**ulMask**成员和描述**ulPropTag**成员属性的值中所述的位掩码。 如果结果为零，则满足 BMR_EQZ。 如果不为零，也就是说，如果该属性值有至少一个相同位设置为**ulMask**，然后 BMR_NEZ 被满足。
  
有关**SBitMaskRestriction**结构和限制的详细信息，请参阅[有关限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

