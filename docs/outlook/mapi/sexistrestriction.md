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
  
描述用于测试特定属性是否作为表中的列存在的一个存在的限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 保留必须为零。 
    
 **ulPropTag**
  
> 用于标识要测试每行中是否存在的列的属性标记。
    
 **ulReserved2**
  
> 保留必须为零。
    
## <a name="remarks"></a>说明

存在的限制用于确保对涉及属性的其他类型的限制 (如属性和内容限制) 的有意义的结果。 如果将涉及某个属性的限制传递给[IMAPITable:: Restrict](imapitable-restrict.md)或[IMAPITable:: FindRow](imapitable-findrow.md) , 并且该属性不存在, 则限制的结果将是不确定的。 通过创建**和**限制将属性限制与存在的限制联接在一起, 可以保证正确结果的调用者。 
  
存在的限制不能与具有类型 PT_OBJECT 的子对象属性一起使用。 
  
有关**SExistRestriction**结构的详细信息, 请参阅[关于限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

