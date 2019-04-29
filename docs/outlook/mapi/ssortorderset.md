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
ms.openlocfilehash: db19c3908c419b98b8deb71e2a86d0aa6eebe240
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438097"
---
# <a name="ssortorderset"></a>SSortOrderSet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为用于标准或分类排序的表定义排序键的集合。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[CbNewSSortOrderSet](cbnewssortorderset.md)、 [CbSSortOrderSet](cbssortorderset.md)、 [SizedSSortOrderSet](sizedssortorderset.md) <br/> |
   
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
  
> **根据**成员中包含的[SSortOrder](ssortorder.md)结构的计数。 
    
 **cCategories**
  
> 指定为类别列的列的计数。 可能的值范围为零, 表示对**cSorts**成员指示的数字进行了非分类或标准排序。 
    
 **cExpanded**
  
> 以展开状态启动的类别的计数, 其中所有适用于该类别的行都显示在表格视图中。 可能的值范围为0到**cCategories**指示的数字。
    
 **根据**
  
> **SSortOrder**结构的数组, 每个结构定义一个排序顺序。 
    
## <a name="remarks"></a>说明

**SSortOrderSet**结构用于定义标准排序和分类排序的多个排序顺序。 
  
每个**SSortOrderSet**结构至少包含一个**SSortOrder**结构, 用于定义排序的方向以及将用作排序关键字的列。 对于分类排序, 该列用作类别。 当**cSorts**成员的值超过**cCategories**成员的值时, 会有多个排序关键字, 而不是类别, 而是在**SSortOrder**数组中的第一个显示的列中创建类别。 
  
例如, 如果将**cSorts**设置为 3, 并将**cCategories**设置为 2, 则**SSortOrder**数组中前两个条目的**ulPropTag**成员所描述的列将用作分类列。 第一个条目充当顶级类别分组;第二个条目, 作为辅助分组。 将使用第三个条目中定义的排序关键字对匹配两个类别列的所有行进行排序。 
  
**cExpanded**成员指定首次展开的类别的数目。 如果有多个类别, 则表实现将从要指定为类别的第一列开始, 并按后续类别列继续按顺序继续排列, 直到超出**cCategories**的数量。 如果类别列多于扩展的列, 则会折叠类别列。 如果**cExpanded**等于零, 则只有顶级标题行可供表用户显示。 如果**cExpanded**小于类别的数目, 则所有标题行和无叶行均可用。 如果**cExpanded**等于类别的数目, 则完全展开表。 
  
有关标准排序和已分类排序的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。
  
## <a name="see-also"></a>另请参阅



[SSortOrder](ssortorder.md)
  
[IMAPITable::ExpandRow](imapitable-expandrow.md)
  
[IMAPITable::CollapseRow](imapitable-collapserow.md)


[MAPI 结构](mapi-structures.md)

