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
ms.openlocfilehash: a2a6d273495df52adb83393dc5549b0872c8f6f3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341739"
---
# <a name="srestriction"></a>SRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍用于将表的视图限制为特定行的筛选器。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 限制类型。 可能的值如下所示: 
    
RES_AND 
  
> **和**限制, 这将对限制应用按位**and**运算。 
    
RES_BITMASK 
  
> 一个位掩码限制, 它将位掩码应用于属性值。
    
RES_COMMENT 
  
> 一种注释限制, 它将注释与限制相关联。
    
RES_COMPAREPROPS 
  
> 属性比较限制, 它将比较两个属性值。
    
RES_CONTENT 
  
> 内容限制, 用于搜索特定内容的属性值。
    
RES_EXIST 
  
> 一个存在的限制, 用于确定是否支持某个属性。
    
RES_NOT 
  
> 一个**不**受限制, 它将逻辑**非**操作应用于限制。 
    
RES_OR 
  
> **或**限制, 这将对限制应用逻辑**或**操作。 
    
RES_PROPERTY 
  
> 属性限制, 用于确定属性值是否与特定值匹配。
    
RES_SIZE 
  
> 大小限制, 用于确定属性值是否为特定大小。
    
RES_SUBRESTRICTION 
  
> 子对象限制, 它对邮件的附件或收件人应用限制。
    
 **res**
  
> 限制结构的联合, 用于描述要应用的筛选器。 **res**成员中包含的特定结构取决于**rt**成员的值。 在下表中列出了限制类型和结构之间的映射。 
    
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
   
## <a name="remarks"></a>注解

客户端使用**SRestriction**结构来限制其表视图中的行数和类型, 并在文件夹中搜索特定邮件。 若要对表施加限制, 客户端可以调用[IMAPITable:: Restrict](imapitable-restrict.md)或[IMAPITable:: FindRow](imapitable-findrow.md)。 若要对文件夹施加限制, 客户端可以调用文件夹的[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法。 
  
有关如何对表使用限制的信息, 请参阅[关于限制](about-restrictions.md)。 
  
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

