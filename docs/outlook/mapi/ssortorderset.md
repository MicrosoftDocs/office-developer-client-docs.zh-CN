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
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[CbNewsSortOrderSet](cbnewssortorderset.md) [、CbsSortOrderSet](cbssortorderset.md) [、SizedssortOrderSet](sizedssortorderset.md) <br/> |
   
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
  
> aSort 成员中包含的[SSortOrder](ssortorder.md)结构计数。 
    
 **cCategories**
  
> 指定为类别列的列数。 可能的值范围从零（表示非分类或标准排序）到 **cSorts** 成员指示的编号。 
    
 **cExpanded**
  
> 以展开状态开始的类别计数，其中应用于类别的所有行都显示在表视图中。 可能的值范围为 0 到 **cCategories 指示的数值**。
    
 **aSort**
  
> **SSortOrder** 结构数组，每个结构都定义排序顺序。 
    
## <a name="remarks"></a>备注

**SSortOrderSet** 结构用于为标准和分类排序定义多个排序顺序。 
  
每个 **SSortOrderSet** 结构至少包含一个定义排序方向和将用作排序键的列的 **SSortOrder** 结构。 对于分类排序，此列用作类别。 当 **cSorts** 成员的值超过 **cCategories** 成员的值时，排序键多于类别，并且类别从 **SSortOrder** 数组中首先出现的列创建。 
  
例如，如果 **cSorts** 设置为 3，cCategories 设置为 2，**则 SSortOrder** 数组中前两个条目的 **ulPropTag** 成员描述的列将用作类别列。  第一个条目充当顶级类别分组;第二个条目作为辅助分组。 使用第三项中定义的排序键对匹配这两个类别列的所有行进行排序。 
  
**cExpanded** 成员指定最初展开的类别数。 存在多个类别时，表实现从要指定为类别的第一列开始，并按顺序与后续类别列一起继续，直到超出 **cCategories** 的数量。 如果类别列数多于展开列数，则折叠类别列。 如果 **cExpanded** 等于零，则只有顶级标题行可供表用户显示。 如果 **cExpanded** 等于比类别数少一个，则所有标题行和叶行均不可用。 如果 **cExpanded** 等于类别数，则表将完全展开。 
  
有关标准和分类排序的信息，请参阅 [排序和分类](sorting-and-categorization.md)。
  
## <a name="see-also"></a>另请参阅



[SSortOrder](ssortorder.md)
  
[IMAPITable::ExpandRow](imapitable-expandrow.md)
  
[IMAPITable::CollapseRow](imapitable-collapserow.md)


[MAPI 结构](mapi-structures.md)

