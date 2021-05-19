---
title: SNotRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SNotRestriction
api_type:
- COM
ms.assetid: e86ca032-d973-4b79-976e-5240ab38a0da
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 07a1a0a1953d136da534fbdc6339d326c877bebf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426651"
---
# <a name="snotrestriction"></a>SNotRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述 **NOT** 限制，该限制用于将逻辑 **NOT** 操作应用于限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SNotRestriction
{
  ULONG ulReserved;
  LPSRestriction lpRes;
} SNotRestriction;

```

## <a name="members"></a>Members

 **ulReserved**
  
> [in]保留;必须为零。
    
 **lpRes**
  
> 指向描述要联接逻辑 **NOT** 运算符的限制的 [SRestriction](srestriction.md)结构的指针。 
    
## <a name="remarks"></a>备注

有关 **SNotRestriction** 结构详细信息，请参阅关于 [限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

