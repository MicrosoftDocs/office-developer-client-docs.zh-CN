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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438881"
---
# <a name="sandrestriction"></a>SAndRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述 **AND** 限制，该限制用于使用逻辑 **AND** 操作加入一组限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SAndRestriction
{
  ULONG cRes;
  LPSRestriction lpRes;
} SAndRestriction;

```

## <a name="members"></a>Members

 **cRes**
  
> **lpRes** 成员指向的数组中的搜索限制计数。 
    
 **lpRes**
  
> 指向将结合逻辑 [AND 运算的 SRestriction](srestriction.md) 结构的 **数组的指针** 。 
    
## <a name="remarks"></a>备注

如果 **SAndRestriction** 的所有子限制计算结果为 TRUE，则结果为 TRUE。 如果任何子限制计算结果为 FALSE，则其为 FALSE。 
  
有关限制类型的说明、如何构建它们以及示例代码，请参阅关于 [限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

