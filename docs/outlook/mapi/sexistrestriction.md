---
title: SExistRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SExistRestriction
api_type:
- COM
ms.assetid: 48d5ab42-ee70-4f6e-9184-18d22b08ea1b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6e3cdcf3579b26776d9e278bb339758d4f56d890
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418937"
---
# <a name="sexistrestriction"></a>SExistRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述一个存在限制，该限制用于测试特定属性是否存在为表中的列。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SExistRestriction
{
  ULONG ulReserved1;
  ULONG ulPropTag;
  ULONG ulReserved2;
} SExistRestriction;

```

## <a name="members"></a>Members

 **ulReserved1**
  
> 保留;必须为零。 
    
 **ulPropTag**
  
> 属性标记，用于标识每行中是否存在要测试的列。
    
 **ulReserved2**
  
> 保留;必须为零。
    
## <a name="remarks"></a>备注

存在限制用于保证对涉及属性的其他类型的限制（如属性和内容限制）产生有意义的结果。 当涉及属性的限制被传递到 [IMAPITable：：Restrict](imapitable-restrict.md) 或 [IMAPITable：：FindRow](imapitable-findrow.md) 并且该属性不存在时，限制的结果将不确定。 通过创建将属性限制与存在限制联接的 **AND** 限制，可以保证调用方得到准确的结果。 
  
存在限制不能与类型为 PT_OBJECT 的子对象属性一PT_OBJECT。 
  
有关 **SExistRestriction** 结构详细信息，请参阅关于 [限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

