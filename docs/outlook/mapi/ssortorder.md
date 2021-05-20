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
ms.openlocfilehash: f9d38c90fa5795d34f78c61ce0faa5f76d8f740d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439721"
---
# <a name="ssortorder"></a>SSortOrder
 
**适用于**：Outlook 2013 | Outlook 2016 
  
定义如何对表的行进行排序、用作排序键的列以及排序方向。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SSortOrder
{
  ULONG ulPropTag;
  ULONG ulOrder;
} SSortOrder, FAR *LPSSortOrder;

```

## <a name="members"></a>Members

**ulPropTag**
  
> 属性标记，用于标识分类键或分类列。
    
**ulOrder**
  
> 数据的排序顺序。 可能的值如下：
    
  - TABLE_SORT_ASCEND：表应按升序排序。
      
  - TABLE_SORT_COMBINE：排序操作应创建一个类别，该类别将 **ulPropTag** 成员中标识为排序键列的属性与在之前的 **SSortOrder** 结构中指定的排序键列组合在一起。 
      
    TABLE_SORT_COMBINE **SSortOrder** 结构用作 [SSortOrderSet](ssortorderset.md) 结构中的条目来为分类排序指定多个排序顺序时，才能使用参数。 TABLE_SORT_COMBINE **SSortOrderSet** 结构中的第一 **个 SSortOrder 结构中** 使用。 
      
  - TABLE_SORT_DESCEND：表应按降序排序。
      
  - TABLE_SORT_CATEG_MAX：该表应按 **SSortOrderSet** 结构中上一排序顺序指定的类别中数据行的 **ulPropTag** 成员最大值进行排序。 
      
  - TABLE_SORT_CATEG_MIN：该表应按照在 **SSortOrderSet** 结构中的上一排序顺序指定的类别中数据行的 **ulPropTag** 成员最小值进行排序。 
    
## <a name="remarks"></a>备注

**SSortOrder** 结构用于描述如何执行标准排序操作或分类排序操作。 **SSortOrder** 结构通常组合到一个 **SSortOrderSet** 结构中，用于描述多个排序键和方向。 **SSortOrderSet** 结构用于以下函数和接口方法： 
  
- [ITableData::HrGetView](itabledata-hrgetview.md)
    
- [IMAPIFolder::SaveContentsSort](imapifolder-savecontentssort.md)
    
- [IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
    
- [IMAPITable::SortTable](imapitable-sorttable.md)
    
- [FBadSortOrderSet](fbadsortorderset.md)
    
- [HrQueryAllRows](hrqueryallrows.md)
    
表中可用作排序键的允许列的范围取决于提供程序。 属于当前列集的列始终可以用作排序键。 但是，每个提供程序确定是否可以使用当前列集外可用的列定义排序键。 可用列是在设置数据透视表标志时从 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 返回TBL_ALL_COLUMNS列。 
  
**ulOrder** 成员指示方向顺序和分类信息，例如，通过对话 ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)) ，即对话线程，即一系列消息和回复。 行可以按升序或降序排序，所有 NULL 条目都位于最后。 
  
the TABLE_SORT_COMBINE value indicates that the column specified in **ulPropTag** should be combined with the previous category column to form a composite category. 也就是说，允许对列组合的唯一值进行分类TABLE_SORT_COMBINE对各个列的唯一值进行分类，而不是对各个列的唯一值进行分类。 例如，可以定义单个类别以对从特定主题的特定发件人接收的邮件进行分组。 将该值设置为 TABLE_SORT_COMBINE可以减少显示的类别行数。 
  
并非所有表实现都普遍支持对多值列进行排序。 如果受支持，MV_FLAG使用 MVI_PROP 宏应用到 **ulPropTag** 成员中的属性标记，以将排序键标识为多值列。 对多值列进行排序基于使用单个值。 
  
> [!IMPORTANT]
> 当前具有TABLE_SORT_CATEG_MAX和 TABLE_SORT_CATEG_MIN 的 **ulOrder** 成员值可能未在可下载头文件中定义，在这种情况下，您可以使用以下值将其添加到代码中：>  `#define TABLE_SORT_CATEG_MAX ((ULONG) 0x00000004)`>  `#define TABLE_SORT_CATEG_MIN ((ULONG) 0x00000008)`
  
有关标准和分类排序的信息，请参阅 [排序和分类](sorting-and-categorization.md)。 
  
## <a name="see-also"></a>另请参阅

- [SSortOrderSet](ssortorderset.md)
- [MAPI 结构](mapi-structures.md)

