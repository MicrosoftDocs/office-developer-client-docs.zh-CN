---
title: SSortOrder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SSortOrder
api_type:
- COM
ms.assetid: fe181b9a-5903-4cc0-bcd5-2061b440b5b1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7cb511c7a021c4e65214acc7efa785be0e02ffc8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778868"
---
# <a name="ssortorder"></a>SSortOrder
 
**适用于**： Outlook 
  
定义如何对表，用于排序的方向排序项，以及哪些列的行进行排序。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SSortOrder
{
  ULONG ulPropTag;
  ULONG ulOrder;
} SSortOrder, FAR *LPSSortOrder;

```

## <a name="members"></a>Members

**ulPropTag**
  
> 属性标识键的或对分类进行排序，类别列的排序标记。
    
**ulOrder**
  
> 在其中数据的排序顺序。 可能值如下所示：
    
  - TABLE_SORT_ASCEND： 表格应以升序排序。
      
  - TABLE_SORT_COMBINE： 排序操作应创建结合使用，标识为排序键列**ulPropTag**成员中与在以前的**SSortOrder**结构中指定的排序键列的属性的类别。 
      
    正在**SSortOrder**结构用作[SSortOrderSet](ssortorderset.md)结构中的条目，以指定多个排序顺序对分类进行排序时，可以仅使用 TABLE_SORT_COMBINE。 TABLE_SORT_COMBINE 不能使用**SSortOrderSet**结构中的第一个**SSortOrder**结构中。 
      
  - TABLE_SORT_DESCEND： 表格应按降序排序。
      
  - TABLE_SORT_CATEG_MAX： 表格应根据**SSortOrderSet**结构中的上一排序次序由指定的类别中的数据行的**ulPropTag**成员的最大值排序。 
      
  - TABLE_SORT_CATEG_MIN： 表格应在以前的排序顺序在**SSortOrderSet**结构中所指定的类别中的数据行的**ulPropTag**成员的最小值排序。 
    
## <a name="remarks"></a>说明

**SSortOrder**结构用于说明如何执行标准排序操作或分类的排序操作。 **SSortOrder**结构通常组合成**SSortOrderSet**结构来描述多个排序关键字和方向。 使用以下函数和接口方法中使用**SSortOrderSet**结构： 
  
- [ITableData::HrGetView](itabledata-hrgetview.md)
    
- [IMAPIFolder::SaveContentsSort](imapifolder-savecontentssort.md)
    
- [IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
    
- [IMAPITable::SortTable](imapitable-sorttable.md)
    
- [FBadSortOrderSet](fbadsortorderset.md)
    
- [HrQueryAllRows](hrqueryallrows.md)
    
允许表中的列的可用作排序关键字范围取决于提供程序。 当前的列集一部分的列始终可以用作排序关键字。 但是，每个提供商决定是否可以使用当前列中不包含的可用列定义排序关键字。 可用栏是设置 TBL_ALL_COLUMNS 标志时从[IMAPITable::QueryColumns](imapitable-querycolumns.md)返回的列。 
  
**UlOrder**成员方向的顺序和分类信息，例如，指示按对话 ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))，即交谈线程，这是一系列邮件和答复。 可以按升序或降序顺序与所有 NULL 条目放置在上次对行进行排序。 
  
TABLE_SORT_COMBINE 值指示**ulPropTag**中指定的列应结合以前的类别列以形成复合类别。 即，而不是分类的单个列的唯一值，TABLE_SORT_COMBINE 允许分类的列的组合唯一值。 例如，无法对来自特定主题上特定发件人邮件进行分组定义单个类别。 将值设置为 TABLE_SORT_COMBINE 减少显示的类别行数。 
  
所有表实现不通用支持对多值列进行排序。 如果受支持，应用**ulPropTag**成员中使用属性标记为 MVI_PROP 宏来标识为多值列的排序关键字 MV_FLAG。 对多值列排序取决于使用的单个值。 
  
> [!IMPORTANT]
> TABLE_SORT_CATEG_MAX TABLE_SORT_CATEG_MIN 可能不定义和可下载头文件中的**ulOrder**成员值后，在这种情况下您可以将其添加到代码中使用以下值： >`#define TABLE_SORT_CATEG_MAX ((ULONG) 0x00000004)`>  `#define TABLE_SORT_CATEG_MIN ((ULONG) 0x00000008)`
  
有关 standard 和分类排序的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。 
  
## <a name="see-also"></a>另请参阅

- [SSortOrderSet](ssortorderset.md)
- [MAPI 结构](mapi-structures.md)

