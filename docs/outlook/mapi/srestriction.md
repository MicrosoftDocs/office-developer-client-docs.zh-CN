---
title: SRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SRestriction
api_type:
- COM
ms.assetid: c12b4409-da6f-480b-87af-1e5baea2e8bd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9748229799641d62b1649491c432f10164b49192
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778867"
---
# <a name="srestriction"></a>SRestriction

  
  
**适用于**： Outlook 
  
介绍限制到特定行表的视图的筛选器。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SRestriction
{
  ULONG rt;
  union
  {
    SComparePropsRestriction resCompareProps;
    SAndRestriction resAnd;
    SOrRestriction resOr;
    SNotRestriction resNot;
    SContentRestriction resContent;
    SPropertyRestriction resProperty;
    SBitMaskRestriction resBitMask;
    SSizeRestriction resSize;
    SExistRestriction resExist;
    SSubRestriction resSub;
    SCommentRestriction resComment;
  } res;
} SRestriction;

```

## <a name="members"></a>Members

 **rt**
  
> 限制类型。 可能值如下所示： 
    
RES_AND 
  
> 限制应用于的按位**AND**操作**和**限制。 
    
RES_BITMASK 
  
> 位掩码限制，适用于属性值的位掩码。
    
RES_COMMENT 
  
> 注释限制，将批注与限制相关联。
    
RES_COMPAREPROPS 
  
> 属性比较限制，比较两个属性值。
    
RES_CONTENT 
  
> 内容限制，搜索特定内容的属性值。
    
RES_EXIST 
  
> 确定是否支持属性存在限制。
    
RES_NOT 
  
> **不**限制，适用于限制的逻辑**NOT**操作。 
    
RES_OR 
  
> **或**限制，适用于限制的逻辑**OR**运算。 
    
RES_PROPERTY 
  
> 属性限制，确定属性值是否与特定值匹配。
    
RES_SIZE 
  
> 大小限制，确定属性值是否是特定大小。
    
RES_SUBRESTRICTION 
  
> 子对象限制，适用于邮件的附件或收件人的限制。
    
 **res**
  
> 要应用的描述筛选器的限制结构联合。 **Res**成员中包含的特定结构取决于**rt**成员的值。 下表中列出的限制类型和结构之间的映射。 
    
|||
|:-----|:-----|
|**限制类型** <br/> |**限制结构** <br/> |
|RES_AND  <br/> |[SAndRestriction](sandrestriction.md) <br/> |
|RES_BITMASK  <br/> |[SBitMaskRestriction](sbitmaskrestriction.md) <br/> |
|RES_COMMENT  <br/> |[SCommentRestriction](scommentrestriction.md) <br/> |
|RES_COMPAREPROPS  <br/> |[SComparePropsRestriction](scomparepropsrestriction.md) <br/> |
|RES_CONTENT  <br/> |[SContentRestriction](scontentrestriction.md) <br/> |
|RES_EXIST  <br/> |[SExistRestriction](sexistrestriction.md) <br/> |
|RES_NOT  <br/> |[SNotRestriction](snotrestriction.md) <br/> |
|RES_OR  <br/> |[SOrRestriction](sorrestriction.md) <br/> |
|RES_PROPERTY  <br/> |[SPropertyRestriction](spropertyrestriction.md) <br/> |
|RES_SIZE  <br/> |[SSizeRestriction](ssizerestriction.md) <br/> |
|RES_SUBRESTRICTION  <br/> |[SSubRestriction](ssubrestriction.md) <br/> |
   
## <a name="remarks"></a>说明

若要限制的数量和类型，其表的视图中的行并搜索的文件夹中的特定邮件，则客户端使用**SRestriction**结构。 若要实施的限制表上，客户端调用[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)。 若要实施的文件夹的限制，客户端调用该文件夹的[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法。 
  
有关如何使用表的限制，请参阅[有关限制](about-restrictions.md)的信息。 
  
## <a name="see-also"></a>另请参阅



[SAndRestriction](sandrestriction.md)
  
[SBitMaskRestriction](sbitmaskrestriction.md)
  
[SCommentRestriction](scommentrestriction.md)
  
[SComparePropsRestriction](scomparepropsrestriction.md)
  
[SContentRestriction](scontentrestriction.md)
  
[SExistRestriction](sexistrestriction.md)
  
[SNotRestriction](snotrestriction.md)
  
[SOrRestriction](sorrestriction.md)
  
[SPropertyRestriction](spropertyrestriction.md)
  
[SSizeRestriction](ssizerestriction.md)
  
[SSubRestriction](ssubrestriction.md)


[MAPI 结构](mapi-structures.md)

