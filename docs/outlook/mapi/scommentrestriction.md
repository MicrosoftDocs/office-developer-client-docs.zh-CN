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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351413"
---
# <a name="scommentrestriction"></a>SCommentRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述用于对限制进行批注的注释限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 由**lpProp**成员指向的数组中的属性值的计数。 
    
 **lpRes**
  
> 指向[SRestriction](srestriction.md)结构的指针。 
    
 **lpProp**
  
> 指向[SPropValue](spropvalue.md)结构的数组的指针, 其中每个都包含命名属性的属性标记和值。 
    
## <a name="remarks"></a>注解

**SCommentRestriction**结构将对象与一组命名属性相关联。 注释限制与其他限制不同, 因为它们不会进行评估。 即, [IMAPITable:: Restrict](imapitable-restrict.md)方法将忽略它们。 对 imapitable:: [QueryRows](imapitable-queryrows.md)方法返回的行在**imapitable:: Restrict**调用之后不会有任何影响。 
  
**SCommentRestriction**结构可用于将特定于应用程序的信息保存在磁盘上时保持限制。 例如, 在属性限制中保存所使用的命名属性的名称的客户端可以在**SCommentRestriction**结构中执行此操作。 不能在属性限制中保存属性名称, 因为关联的[SPropertyRestriction](spropertyrestriction.md)结构仅保存属性标记。 
  
有关**SCommentRestriction**结构和限制的详细信息, 请参阅[关于限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)
  
[SRestriction](srestriction.md)
  
[SPropertyRestriction](spropertyrestriction.md)


[MAPI 结构](mapi-structures.md)

