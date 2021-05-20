---
title: SCommentRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SCommentRestriction
api_type:
- COM
ms.assetid: 07631ae1-981e-4c8e-a30b-1213904fe079
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3f66f513cc16bc479dd24c53804d751a396141f4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430607"
---
# <a name="scommentrestriction"></a>SCommentRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述注释限制，用于注释限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SCommentRestriction
{
  ULONG          cValues;
  LPSRestriction lpRes;
  LPSPropValue   lpProp;
} SCommentRestriction;

```

## <a name="members"></a>Members

 **cValues**
  
> **lpProp** 成员指向的数组中的属性值计数。 
    
 **lpRes**
  
> 指向 [SRestriction 结构的](srestriction.md) 指针。 
    
 **lpProp**
  
> 指向 [SPropValue 结构的](spropvalue.md) 数组的指针，每个结构包含命名属性的属性标记和值。 
    
## <a name="remarks"></a>备注

**SCommentRestriction** 结构将对象与一组命名属性关联。 注释限制与其他限制不同，因为它们未进行评估。 即 [，IMAPITable：：Restrict](imapitable-restrict.md) 方法将忽略它们。 执行 **IMAPITable：：Restrict** 调用后 [，对 IMAPITable：：QueryRows](imapitable-queryrows.md)方法返回的行没有影响。 
  
**SCommentRestriction** 结构可用于将特定于应用程序的信息保存在磁盘上时具有限制。 例如，保存属性限制中使用的命名属性的名称的客户端可以在 **SCommentRestriction** 结构中这样做。 在属性限制中无法保存属性名称，因为关联的 [SPropertyRestriction](spropertyrestriction.md) 结构仅保留属性标记。 
  
有关 **SCommentRestriction** 结构和限制的一般详细信息，请参阅关于 [限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)
  
[SRestriction](srestriction.md)
  
[SPropertyRestriction](spropertyrestriction.md)


[MAPI 结构](mapi-structures.md)

