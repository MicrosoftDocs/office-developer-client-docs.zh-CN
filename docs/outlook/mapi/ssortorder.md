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
# <a name="ssortorder"></a><span data-ttu-id="368a1-103">SSortOrder</span><span class="sxs-lookup"><span data-stu-id="368a1-103">SSortOrder</span></span>
 
<span data-ttu-id="368a1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="368a1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="368a1-105">定义如何对表的行、要用作排序关键字的列以及排序的方向进行排序。</span><span class="sxs-lookup"><span data-stu-id="368a1-105">Defines how to sort the rows of a table, what column to use as the sort key, and the direction of the sort.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="368a1-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="368a1-106">Header file:</span></span>  <br/> |<span data-ttu-id="368a1-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="368a1-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SSortOrder
{
  ULONG ulPropTag;
  ULONG ulOrder;
} SSortOrder, FAR *LPSSortOrder;

```

## <a name="members"></a><span data-ttu-id="368a1-108">Members</span><span class="sxs-lookup"><span data-stu-id="368a1-108">Members</span></span>

<span data-ttu-id="368a1-109">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="368a1-109">**ulPropTag**</span></span>
  
> <span data-ttu-id="368a1-110">用于标识排序关键字的属性标记, 对于分类的排序, 则为分类列。</span><span class="sxs-lookup"><span data-stu-id="368a1-110">Property tag identifying the sort key or, for a categorized sort, the category column.</span></span>
    
<span data-ttu-id="368a1-111">**ulOrder**</span><span class="sxs-lookup"><span data-stu-id="368a1-111">**ulOrder**</span></span>
  
> <span data-ttu-id="368a1-112">对数据进行排序所依据的顺序。</span><span class="sxs-lookup"><span data-stu-id="368a1-112">The order in which the data is to be sorted.</span></span> <span data-ttu-id="368a1-113">可能的值如下所示:</span><span class="sxs-lookup"><span data-stu-id="368a1-113">Possible values are as follow:</span></span>
    
  - <span data-ttu-id="368a1-114">TABLE_SORT_ASCEND: 应按升序对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="368a1-114">TABLE_SORT_ASCEND: The table should be sorted in ascending order.</span></span>
      
  - <span data-ttu-id="368a1-115">TABLE_SORT_COMBINE: SORT 操作应创建一个类别, 该类别将**ulPropTag**成员中标识为 "排序关键字" 列的属性与上一**SSortOrder**结构中指定的 "排序" 关键字列组合在一起。</span><span class="sxs-lookup"><span data-stu-id="368a1-115">TABLE_SORT_COMBINE: The sort operation should create a category that combines the property identified as the sort key column in the **ulPropTag** member with the sort key column specified in the previous **SSortOrder** structure.</span></span> 
      
    <span data-ttu-id="368a1-116">仅当**SSortOrder**结构用作[SSortOrderSet](ssortorderset.md)结构中的条目以指定已分类排序的多个排序次序时, 才能使用 TABLE_SORT_COMBINE。</span><span class="sxs-lookup"><span data-stu-id="368a1-116">TABLE_SORT_COMBINE can only be used when the **SSortOrder** structure is being used as an entry in an [SSortOrderSet](ssortorderset.md) structure to specify multiple sort orders for a categorized sort.</span></span> <span data-ttu-id="368a1-117">TABLE_SORT_COMBINE 不能在**SSortOrderSet**结构中的第一个**SSortOrder**结构中使用。</span><span class="sxs-lookup"><span data-stu-id="368a1-117">TABLE_SORT_COMBINE cannot be used in the first **SSortOrder** structure in an **SSortOrderSet** structure.</span></span> 
      
  - <span data-ttu-id="368a1-118">TABLE_SORT_DESCEND: 应按降序顺序对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="368a1-118">TABLE_SORT_DESCEND: The table should be sorted in descending order.</span></span>
      
  - <span data-ttu-id="368a1-119">TABLE_SORT_CATEG_MAX: 表应按由**SSortOrderSet**结构中的前一排序\*\*\*\* 顺序指定的类别中的数据行的最大值进行排序。</span><span class="sxs-lookup"><span data-stu-id="368a1-119">TABLE_SORT_CATEG_MAX: The table should be sorted on the maximum value of the **ulPropTag** member for the data rows in the categories specified by the previous sort order in the **SSortOrderSet** structure.</span></span> 
      
  - <span data-ttu-id="368a1-120">TABLE_SORT_CATEG_MIN: 应按照在**SSortOrderSet**结构中的上一排序次序\*\*\*\* 指定的类别中的数据行的最小值对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="368a1-120">TABLE_SORT_CATEG_MIN: The table should be sorted on the minimum value of the **ulPropTag** member for the data rows in the categories specified by the previous sort order in the in **SSortOrderSet** structure.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="368a1-121">说明</span><span class="sxs-lookup"><span data-stu-id="368a1-121">Remarks</span></span>

<span data-ttu-id="368a1-122">**SSortOrder**结构用于描述如何执行标准排序操作或已分类的排序操作。</span><span class="sxs-lookup"><span data-stu-id="368a1-122">An **SSortOrder** structure is used to describe how to perform either a standard sort operation or a categorized sort operation.</span></span> <span data-ttu-id="368a1-123">**SSortOrder**结构通常组合到**SSortOrderSet**结构中, 以描述多个排序键和方向。</span><span class="sxs-lookup"><span data-stu-id="368a1-123">**SSortOrder** structures are typically combined into an **SSortOrderSet** structure to describe multiple sort keys and directions.</span></span> <span data-ttu-id="368a1-124">在以下函数和接口方法中使用**SSortOrderSet**结构:</span><span class="sxs-lookup"><span data-stu-id="368a1-124">**SSortOrderSet** structures are used in the following functions and interface methods:</span></span> 
  
- [<span data-ttu-id="368a1-125">ITableData::HrGetView</span><span class="sxs-lookup"><span data-stu-id="368a1-125">ITableData::HrGetView</span></span>](itabledata-hrgetview.md)
    
- [<span data-ttu-id="368a1-126">IMAPIFolder::SaveContentsSort</span><span class="sxs-lookup"><span data-stu-id="368a1-126">IMAPIFolder::SaveContentsSort</span></span>](imapifolder-savecontentssort.md)
    
- [<span data-ttu-id="368a1-127">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="368a1-127">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
    
- [<span data-ttu-id="368a1-128">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="368a1-128">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
    
- [<span data-ttu-id="368a1-129">FBadSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="368a1-129">FBadSortOrderSet</span></span>](fbadsortorderset.md)
    
- [<span data-ttu-id="368a1-130">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="368a1-130">HrQueryAllRows</span></span>](hrqueryallrows.md)
    
<span data-ttu-id="368a1-131">可用作排序关键字的表中允许的列的范围取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="368a1-131">The range of allowed columns in a table that can be used as a sort key depends on the provider.</span></span> <span data-ttu-id="368a1-132">作为当前列集一部分的列始终可用作排序关键字。</span><span class="sxs-lookup"><span data-stu-id="368a1-132">Columns that are part of the current column set can always be used as sort keys.</span></span> <span data-ttu-id="368a1-133">但是, 每个提供程序确定是否可以使用不在当前列集中的可用列来定义排序键。</span><span class="sxs-lookup"><span data-stu-id="368a1-133">However, each provider determines whether sort keys can be defined by using available columns that are not in the current column set.</span></span> <span data-ttu-id="368a1-134">"可用列" 是设置 TBL_ALL_COLUMNS 标志时从[IMAPITable:: QueryColumns](imapitable-querycolumns.md)返回的列。</span><span class="sxs-lookup"><span data-stu-id="368a1-134">An available column is a column that is returned from [IMAPITable::QueryColumns](imapitable-querycolumns.md) when the TBL_ALL_COLUMNS flag is set.</span></span> 
  
<span data-ttu-id="368a1-135">**ulOrder**成员指示方向性订单和分类信息, 例如, 通过对话 ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)), 即会话线程, 这是一系列邮件和回复。</span><span class="sxs-lookup"><span data-stu-id="368a1-135">The **ulOrder** member indicates both directional order and categorization information, for example, by conversation ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)), that is, conversational thread, which is a series of messages and replies.</span></span> <span data-ttu-id="368a1-136">可以按升序或降序顺序对行进行排序, 并将所有 NULL 项放置在最后。</span><span class="sxs-lookup"><span data-stu-id="368a1-136">Rows can be sorted in either an ascending or descending sequence with all NULL entries positioned last.</span></span> 
  
<span data-ttu-id="368a1-137">TABLE_SORT_COMBINE 值指示在**ulPropTag**中指定的列应与上一个 category 列组合, 以构成一个复合类别。</span><span class="sxs-lookup"><span data-stu-id="368a1-137">The TABLE_SORT_COMBINE value indicates that the column specified in **ulPropTag** should be combined with the previous category column to form a composite category.</span></span> <span data-ttu-id="368a1-138">也就是说, TABLE_SORT_COMBINE 允许对列组合的唯一值进行分类, 而不是对单个列的唯一值进行分类。</span><span class="sxs-lookup"><span data-stu-id="368a1-138">That is, instead of categorizing on unique values of individual columns, TABLE_SORT_COMBINE allows for categorization on unique values of a combination of columns.</span></span> <span data-ttu-id="368a1-139">例如, 可以将单个类别定义为对来自特定主题的特定发件人收到的邮件进行分组。</span><span class="sxs-lookup"><span data-stu-id="368a1-139">For example, a single category could be defined to group messages received from a particular sender on a particular subject.</span></span> <span data-ttu-id="368a1-140">将值设置为 TABLE_SORT_COMBINE 可减少显示的类别行的数量。</span><span class="sxs-lookup"><span data-stu-id="368a1-140">Setting the value to TABLE_SORT_COMBINE reduces the number of category rows that are displayed.</span></span> 
  
<span data-ttu-id="368a1-141">并非所有表实现都普遍支持对多值列进行排序。</span><span class="sxs-lookup"><span data-stu-id="368a1-141">Sorting on multi-valued columns is not universally supported by all table implementations.</span></span> <span data-ttu-id="368a1-142">如果支持, 请使用 MVI_PROP 宏将 MV_FLAG 应用于**ulPropTag**成员中的属性标记, 以将排序关键字标识为多值列。</span><span class="sxs-lookup"><span data-stu-id="368a1-142">If supported, apply the MV_FLAG using the MVI_PROP macro to the property tag in the **ulPropTag** member to identify the sort key as a multi-valued column.</span></span> <span data-ttu-id="368a1-143">对多值列进行排序基于使用各个值。</span><span class="sxs-lookup"><span data-stu-id="368a1-143">Sorting on a multi-valued column is based on using the individual values.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="368a1-144">**ulOrder**成员值 TABLE_SORT_CATEG_MAX 和 TABLE_SORT_CATEG_MIN 可能未在您当前拥有的可下载头文件中定义, 在这种情况下, 您可以使用以下值将其添加到代码中: >`#define TABLE_SORT_CATEG_MAX ((ULONG) 0x00000004)`>  `#define TABLE_SORT_CATEG_MIN ((ULONG) 0x00000008)`</span><span class="sxs-lookup"><span data-stu-id="368a1-144">The **ulOrder** member values TABLE_SORT_CATEG_MAX and TABLE_SORT_CATEG_MIN might not be defined in the downloadable header file you currently have, in which case you can add it to your code using the following values: >  `#define TABLE_SORT_CATEG_MAX ((ULONG) 0x00000004)`>  `#define TABLE_SORT_CATEG_MIN ((ULONG) 0x00000008)`</span></span>
  
<span data-ttu-id="368a1-145">有关标准排序和已分类排序的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="368a1-145">For more information about standard and categorized sorting, see [Sorting and Categorization](sorting-and-categorization.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="368a1-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="368a1-146">See also</span></span>

- [<span data-ttu-id="368a1-147">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="368a1-147">SSortOrderSet</span></span>](ssortorderset.md)
- [<span data-ttu-id="368a1-148">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="368a1-148">MAPI Structures</span></span>](mapi-structures.md)

