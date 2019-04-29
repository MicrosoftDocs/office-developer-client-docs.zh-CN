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
  
介绍用于执行按位**and**运算并测试结果的位掩码限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 描述**ulMask**成员中指定的掩码应如何应用于属性标记的关系运算符。 可能的值如下所示: 
    
BMR_EQZ 
  
> 使用**ulPropTag**成员表示的属性对**ulMask**成员中的掩码执行按位 "**与**" 运算, 并测试是否等于零。 
    
BMR_NEZ 
  
> 对**ulMask**成员中的掩码执行按位**and**运算, 该属性由**ulPropTag**成员表示, 并测试为不等于零。 
    
 **ulPropTag**
  
> 要应用位掩码的属性的属性标记。
    
 **ulMask**
  
> 应用于由**ulPropTag**标识的属性的位掩码。
    
## <a name="remarks"></a>说明

**SBitMaskRestriction**结构使用**ulMask**成员中描述的位掩码和**ulPropTag**成员描述的属性值执行按位**and**运算。 如果结果为零, 则表示已满足 BMR_EQZ。 如果该属性值为非零, 即如果属性值至少有一个相同的位设置为**ulMask**, 则满足 BMR_NEZ。
  
有关**SBitMaskRestriction**结构和限制的详细信息, 请参阅[关于限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

