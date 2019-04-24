---
title: SAndRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SAndRestriction
api_type:
- COM
ms.assetid: 1b7dfe87-f87f-43e3-8332-a0d9c3f70d16
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da35c9c72f4cf3f076715a7a35a3e3514c672ceb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344658"
---
# <a name="sandrestriction"></a>SAndRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述了一个**和**限制, 该限制用于通过逻辑**AND**操作来联接一组限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SAndRestriction
{
  ULONG cRes;
  LPSRestriction lpRes;
} SAndRestriction;

```

## <a name="members"></a>Members

 **cRes**
  
> 由**lpRes**成员指向的数组中的搜索限制的计数。 
    
 **lpRes**
  
> 指向将与逻辑**AND**运算组合在一起的[SRestriction](srestriction.md)结构数组的指针。 
    
## <a name="remarks"></a>注解

如果其所有子限制的计算结果为 true, 则**SAndRestriction**的结果为 true。 如果任何子限制的计算结果为 false, 则其值为 false。 
  
有关限制类型的说明、如何生成限制以及示例代码, 请参阅[关于限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

