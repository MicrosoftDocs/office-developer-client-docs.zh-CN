---
title: SSortOrderSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SSortOrderSet
api_type:
- COM
ms.assetid: e7f9be6a-92e7-44a8-93ee-b087713a31df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e8d85ba55c5aa2f3780ad8e04cf1326cd7c35865
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575936"
---
# <a name="ssortorderset"></a>SSortOrderSet

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
定义一个表，用于标准或分类排序的排序关键字的集合。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[CbNewSSortOrderSet](cbnewssortorderset.md)， [CbSSortOrderSet](cbssortorderset.md)， [SizedSSortOrderSet](sizedssortorderset.md) <br/> |
   
```cpp
typedef struct _SSortOrderSet
{
  ULONG cSorts;
  ULONG cCategories;
  ULONG cExpanded;
  SSortOrder aSort[MAPI_DIM];
} SSortOrderSet, FAR *LPSSortOrderSet;

```

## <a name="members"></a>Members

 **cSorts**
  
> [SSortOrder](ssortorder.md)结构**aSort**成员中包含的计数。 
    
 **cCategories**
  
> 指定为类别列的列数。 可能的值范围为 0，表示非分类或标准排序，复制到由**cSorts**成员指示的数字。 
    
 **cExpanded**
  
> 启动的所有行的适用于类别是可见的表视图中展开状态的类别的计数。 可能的值范围为从 0 到由**cCategories**指示的数字。
    
 **aSort**
  
> 每个定义排序顺序的**SSortOrder**结构数组。 
    
## <a name="remarks"></a>注解

**SSortOrderSet**结构用于定义多个标准和分类排序的排序顺序。 
  
每个**SSortOrderSet**结构包含至少一个**SSortOrder**结构定义方向的排序和将用作排序关键字列。 对于分类排序，此列将用作类别。 时**cSorts**成员的值超出**cCategories**成员的值，有多个排序关键字比类别，并显示第一个**SSortOrder**数组中的列中创建的类别。 
  
例如，如果**cSorts**设置为 3 和**cCategories**设置为 2，由**SSortOrder**数组中的前两个条目**ulPropTag**成员所述的列用作类别列。 第一个条目充当顶级类别分组;为辅助分组第二个条目。 所有匹配的两个类别列的行进行排序使用第三项中定义的排序密钥。 
  
**CExpanded**成员指定第一个在展开的分类的数。 当存在多个类别时，表实现开头的第一列被指定为一个类别，并继续按顺序使用后续类别列，直到**cCategories**数超过。 如果有多个类别列比扩展的列，，折叠类别列。 如果**cExpanded**等于零，则仅顶部级别的标题行位于表用户的显示。 如果**cExpanded**等于减数类别，然后的所有标题行和叶行均不可用。 如果**cExpanded**等于的分类数，则完全扩展表。 
  
有关 standard 和分类排序的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。
  
## <a name="see-also"></a>另请参阅



[SSortOrder](ssortorder.md)
  
[IMAPITable::ExpandRow](imapitable-expandrow.md)
  
[IMAPITable::CollapseRow](imapitable-collapserow.md)


[MAPI 结构](mapi-structures.md)

