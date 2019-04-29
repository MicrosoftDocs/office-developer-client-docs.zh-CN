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
  
定义如何对表的行、要用作排序关键字的列以及排序的方向进行排序。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SSortOrder
{
  ULONG ulPropTag;
  ULONG ulOrder;
} SSortOrder, FAR *LPSSortOrder;

```

## <a name="members"></a>Members

**ulPropTag**
  
> 用于标识排序关键字的属性标记, 对于分类的排序, 则为分类列。
    
**ulOrder**
  
> 对数据进行排序所依据的顺序。 可能的值如下所示:
    
  - TABLE_SORT_ASCEND: 应按升序对表进行排序。
      
  - TABLE_SORT_COMBINE: SORT 操作应创建一个类别, 该类别将**ulPropTag**成员中标识为 "排序关键字" 列的属性与上一**SSortOrder**结构中指定的 "排序" 关键字列组合在一起。 
      
    仅当**SSortOrder**结构用作[SSortOrderSet](ssortorderset.md)结构中的条目以指定已分类排序的多个排序次序时, 才能使用 TABLE_SORT_COMBINE。 TABLE_SORT_COMBINE 不能在**SSortOrderSet**结构中的第一个**SSortOrder**结构中使用。 
      
  - TABLE_SORT_DESCEND: 应按降序顺序对表进行排序。
      
  - TABLE_SORT_CATEG_MAX: 表应按由**SSortOrderSet**结构中的前一排序**** 顺序指定的类别中的数据行的最大值进行排序。 
      
  - TABLE_SORT_CATEG_MIN: 应按照在**SSortOrderSet**结构中的上一排序次序**** 指定的类别中的数据行的最小值对表进行排序。 
    
## <a name="remarks"></a>说明

**SSortOrder**结构用于描述如何执行标准排序操作或已分类的排序操作。 **SSortOrder**结构通常组合到**SSortOrderSet**结构中, 以描述多个排序键和方向。 在以下函数和接口方法中使用**SSortOrderSet**结构: 
  
- [ITableData::HrGetView](itabledata-hrgetview.md)
    
- [IMAPIFolder::SaveContentsSort](imapifolder-savecontentssort.md)
    
- [IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
    
- [IMAPITable::SortTable](imapitable-sorttable.md)
    
- [FBadSortOrderSet](fbadsortorderset.md)
    
- [HrQueryAllRows](hrqueryallrows.md)
    
可用作排序关键字的表中允许的列的范围取决于提供程序。 作为当前列集一部分的列始终可用作排序关键字。 但是, 每个提供程序确定是否可以使用不在当前列集中的可用列来定义排序键。 "可用列" 是设置 TBL_ALL_COLUMNS 标志时从[IMAPITable:: QueryColumns](imapitable-querycolumns.md)返回的列。 
  
**ulOrder**成员指示方向性订单和分类信息, 例如, 通过对话 ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)), 即会话线程, 这是一系列邮件和回复。 可以按升序或降序顺序对行进行排序, 并将所有 NULL 项放置在最后。 
  
TABLE_SORT_COMBINE 值指示在**ulPropTag**中指定的列应与上一个 category 列组合, 以构成一个复合类别。 也就是说, TABLE_SORT_COMBINE 允许对列组合的唯一值进行分类, 而不是对单个列的唯一值进行分类。 例如, 可以将单个类别定义为对来自特定主题的特定发件人收到的邮件进行分组。 将值设置为 TABLE_SORT_COMBINE 可减少显示的类别行的数量。 
  
并非所有表实现都普遍支持对多值列进行排序。 如果支持, 请使用 MVI_PROP 宏将 MV_FLAG 应用于**ulPropTag**成员中的属性标记, 以将排序关键字标识为多值列。 对多值列进行排序基于使用各个值。 
  
> [!IMPORTANT]
> **ulOrder**成员值 TABLE_SORT_CATEG_MAX 和 TABLE_SORT_CATEG_MIN 可能未在您当前拥有的可下载头文件中定义, 在这种情况下, 您可以使用以下值将其添加到代码中: >`#define TABLE_SORT_CATEG_MAX ((ULONG) 0x00000004)`>  `#define TABLE_SORT_CATEG_MIN ((ULONG) 0x00000008)`
  
有关标准排序和已分类排序的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。 
  
## <a name="see-also"></a>另请参阅

- [SSortOrderSet](ssortorderset.md)
- [MAPI 结构](mapi-structures.md)

