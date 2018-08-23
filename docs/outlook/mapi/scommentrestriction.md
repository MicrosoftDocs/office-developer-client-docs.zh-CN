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
ms.openlocfilehash: 84fb79b1922669db9c8e5d518a833a6866f11cea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589180"
---
# <a name="scommentrestriction"></a>SCommentRestriction

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
描述注释限制，用来限制批注。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> Count 属性值数组中的指向由**lpProp**成员。 
    
 **lpRes**
  
> 指向[SRestriction](srestriction.md)结构。 
    
 **lpProp**
  
> 给[SPropValue](spropvalue.md)结构，每个包含属性标记和的命名属性值的数组的指针。 
    
## <a name="remarks"></a>注解

**SCommentRestriction**结构将与一组命名属性一起对象相关联。 注释限制是与其他限制不同，因为不会评估这些。 即，它们将被忽略[IMAPITable::Restrict](imapitable-restrict.md)方法。 没有任何影响后**IMAPITable::Restrict**呼叫已由[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的行。 
  
**SCommentRestriction**结构可用于保存在磁盘上时保留了一条限制的特定于应用程序的信息。 例如，保存在属性限制中使用的命名属性的名称的客户端可以这样做**SCommentRestriction**结构中。 因为关联的[SPropertyRestriction](spropertyrestriction.md)结构保留仅属性标记，保存的属性名称不能在属性限制中。 
  
有关**SCommentRestriction**结构和限制的详细信息，请参阅[有关限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)
  
[SRestriction](srestriction.md)
  
[SPropertyRestriction](spropertyrestriction.md)


[MAPI 结构](mapi-structures.md)

