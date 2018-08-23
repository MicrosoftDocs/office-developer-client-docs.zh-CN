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
ms.openlocfilehash: 331dc05b30390bb803d186f157e0fe9edb779ab0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571666"
---
# <a name="ssortorder"></a><span data-ttu-id="28bef-103">SSortOrder</span><span class="sxs-lookup"><span data-stu-id="28bef-103">SSortOrder</span></span>
 
<span data-ttu-id="28bef-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="28bef-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="28bef-105">定义如何对表，用于排序的方向排序项，以及哪些列的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="28bef-105">Defines how to sort the rows of a table, what column to use as the sort key, and the direction of the sort.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="28bef-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="28bef-106">Header file:</span></span>  <br/> |<span data-ttu-id="28bef-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="28bef-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SSortOrder
{
  ULONG ulPropTag;
  ULONG ulOrder;
} SSortOrder, FAR *LPSSortOrder;

```

## <a name="members"></a><span data-ttu-id="28bef-108">Members</span><span class="sxs-lookup"><span data-stu-id="28bef-108">Members</span></span>

<span data-ttu-id="28bef-109">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="28bef-109">**ulPropTag**</span></span>
  
> <span data-ttu-id="28bef-110">属性标识键的或对分类进行排序，类别列的排序标记。</span><span class="sxs-lookup"><span data-stu-id="28bef-110">Property tag identifying the sort key or, for a categorized sort, the category column.</span></span>
    
<span data-ttu-id="28bef-111">**ulOrder**</span><span class="sxs-lookup"><span data-stu-id="28bef-111">**ulOrder**</span></span>
  
> <span data-ttu-id="28bef-112">在其中数据的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="28bef-112">The order in which the data is to be sorted.</span></span> <span data-ttu-id="28bef-113">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="28bef-113">Possible values are as follow:</span></span>
    
  - <span data-ttu-id="28bef-114">TABLE_SORT_ASCEND： 表格应以升序排序。</span><span class="sxs-lookup"><span data-stu-id="28bef-114">TABLE_SORT_ASCEND: The table should be sorted in ascending order.</span></span>
      
  - <span data-ttu-id="28bef-115">TABLE_SORT_COMBINE： 排序操作应创建结合使用，标识为排序键列**ulPropTag**成员中与在以前的**SSortOrder**结构中指定的排序键列的属性的类别。</span><span class="sxs-lookup"><span data-stu-id="28bef-115">TABLE_SORT_COMBINE: The sort operation should create a category that combines the property identified as the sort key column in the **ulPropTag** member with the sort key column specified in the previous **SSortOrder** structure.</span></span> 
      
    <span data-ttu-id="28bef-116">正在**SSortOrder**结构用作[SSortOrderSet](ssortorderset.md)结构中的条目，以指定多个排序顺序对分类进行排序时，可以仅使用 TABLE_SORT_COMBINE。</span><span class="sxs-lookup"><span data-stu-id="28bef-116">TABLE_SORT_COMBINE can only be used when the **SSortOrder** structure is being used as an entry in an [SSortOrderSet](ssortorderset.md) structure to specify multiple sort orders for a categorized sort.</span></span> <span data-ttu-id="28bef-117">TABLE_SORT_COMBINE 不能使用**SSortOrderSet**结构中的第一个**SSortOrder**结构中。</span><span class="sxs-lookup"><span data-stu-id="28bef-117">TABLE_SORT_COMBINE cannot be used in the first **SSortOrder** structure in an **SSortOrderSet** structure.</span></span> 
      
  - <span data-ttu-id="28bef-118">TABLE_SORT_DESCEND： 表格应按降序排序。</span><span class="sxs-lookup"><span data-stu-id="28bef-118">TABLE_SORT_DESCEND: The table should be sorted in descending order.</span></span>
      
  - <span data-ttu-id="28bef-119">TABLE_SORT_CATEG_MAX： 表格应根据**SSortOrderSet**结构中的上一排序次序由指定的类别中的数据行的**ulPropTag**成员的最大值排序。</span><span class="sxs-lookup"><span data-stu-id="28bef-119">TABLE_SORT_CATEG_MAX: The table should be sorted on the maximum value of the **ulPropTag** member for the data rows in the categories specified by the previous sort order in the **SSortOrderSet** structure.</span></span> 
      
  - <span data-ttu-id="28bef-120">TABLE_SORT_CATEG_MIN： 表格应在以前的排序顺序在**SSortOrderSet**结构中所指定的类别中的数据行的**ulPropTag**成员的最小值排序。</span><span class="sxs-lookup"><span data-stu-id="28bef-120">TABLE_SORT_CATEG_MIN: The table should be sorted on the minimum value of the **ulPropTag** member for the data rows in the categories specified by the previous sort order in the in **SSortOrderSet** structure.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="28bef-121">注解</span><span class="sxs-lookup"><span data-stu-id="28bef-121">Remarks</span></span>

<span data-ttu-id="28bef-122">**SSortOrder**结构用于说明如何执行标准排序操作或分类的排序操作。</span><span class="sxs-lookup"><span data-stu-id="28bef-122">An **SSortOrder** structure is used to describe how to perform either a standard sort operation or a categorized sort operation.</span></span> <span data-ttu-id="28bef-123">**SSortOrder**结构通常组合成**SSortOrderSet**结构来描述多个排序关键字和方向。</span><span class="sxs-lookup"><span data-stu-id="28bef-123">**SSortOrder** structures are typically combined into an **SSortOrderSet** structure to describe multiple sort keys and directions.</span></span> <span data-ttu-id="28bef-124">使用以下函数和接口方法中使用**SSortOrderSet**结构：</span><span class="sxs-lookup"><span data-stu-id="28bef-124">**SSortOrderSet** structures are used in the following functions and interface methods:</span></span> 
  
- [<span data-ttu-id="28bef-125">ITableData::HrGetView</span><span class="sxs-lookup"><span data-stu-id="28bef-125">ITableData::HrGetView</span></span>](itabledata-hrgetview.md)
    
- [<span data-ttu-id="28bef-126">IMAPIFolder::SaveContentsSort</span><span class="sxs-lookup"><span data-stu-id="28bef-126">IMAPIFolder::SaveContentsSort</span></span>](imapifolder-savecontentssort.md)
    
- [<span data-ttu-id="28bef-127">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="28bef-127">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
    
- [<span data-ttu-id="28bef-128">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="28bef-128">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
    
- [<span data-ttu-id="28bef-129">FBadSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="28bef-129">FBadSortOrderSet</span></span>](fbadsortorderset.md)
    
- [<span data-ttu-id="28bef-130">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="28bef-130">HrQueryAllRows</span></span>](hrqueryallrows.md)
    
<span data-ttu-id="28bef-131">允许表中的列的可用作排序关键字范围取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="28bef-131">The range of allowed columns in a table that can be used as a sort key depends on the provider.</span></span> <span data-ttu-id="28bef-132">当前的列集一部分的列始终可以用作排序关键字。</span><span class="sxs-lookup"><span data-stu-id="28bef-132">Columns that are part of the current column set can always be used as sort keys.</span></span> <span data-ttu-id="28bef-133">但是，每个提供商决定是否可以使用当前列中不包含的可用列定义排序关键字。</span><span class="sxs-lookup"><span data-stu-id="28bef-133">However, each provider determines whether sort keys can be defined by using available columns that are not in the current column set.</span></span> <span data-ttu-id="28bef-134">可用栏是设置 TBL_ALL_COLUMNS 标志时从[IMAPITable::QueryColumns](imapitable-querycolumns.md)返回的列。</span><span class="sxs-lookup"><span data-stu-id="28bef-134">An available column is a column that is returned from [IMAPITable::QueryColumns](imapitable-querycolumns.md) when the TBL_ALL_COLUMNS flag is set.</span></span> 
  
<span data-ttu-id="28bef-135">**UlOrder**成员方向的顺序和分类信息，例如，指示按对话 ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))，即交谈线程，这是一系列邮件和答复。</span><span class="sxs-lookup"><span data-stu-id="28bef-135">The **ulOrder** member indicates both directional order and categorization information, for example, by conversation ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)), that is, conversational thread, which is a series of messages and replies.</span></span> <span data-ttu-id="28bef-136">可以按升序或降序顺序与所有 NULL 条目放置在上次对行进行排序。</span><span class="sxs-lookup"><span data-stu-id="28bef-136">Rows can be sorted in either an ascending or descending sequence with all NULL entries positioned last.</span></span> 
  
<span data-ttu-id="28bef-137">TABLE_SORT_COMBINE 值指示**ulPropTag**中指定的列应结合以前的类别列以形成复合类别。</span><span class="sxs-lookup"><span data-stu-id="28bef-137">The TABLE_SORT_COMBINE value indicates that the column specified in **ulPropTag** should be combined with the previous category column to form a composite category.</span></span> <span data-ttu-id="28bef-138">即，而不是分类的单个列的唯一值，TABLE_SORT_COMBINE 允许分类的列的组合唯一值。</span><span class="sxs-lookup"><span data-stu-id="28bef-138">That is, instead of categorizing on unique values of individual columns, TABLE_SORT_COMBINE allows for categorization on unique values of a combination of columns.</span></span> <span data-ttu-id="28bef-139">例如，无法对来自特定主题上特定发件人邮件进行分组定义单个类别。</span><span class="sxs-lookup"><span data-stu-id="28bef-139">For example, a single category could be defined to group messages received from a particular sender on a particular subject.</span></span> <span data-ttu-id="28bef-140">将值设置为 TABLE_SORT_COMBINE 减少显示的类别行数。</span><span class="sxs-lookup"><span data-stu-id="28bef-140">Setting the value to TABLE_SORT_COMBINE reduces the number of category rows that are displayed.</span></span> 
  
<span data-ttu-id="28bef-141">所有表实现不通用支持对多值列进行排序。</span><span class="sxs-lookup"><span data-stu-id="28bef-141">Sorting on multi-valued columns is not universally supported by all table implementations.</span></span> <span data-ttu-id="28bef-142">如果受支持，应用**ulPropTag**成员中使用属性标记为 MVI_PROP 宏来标识为多值列的排序关键字 MV_FLAG。</span><span class="sxs-lookup"><span data-stu-id="28bef-142">If supported, apply the MV_FLAG using the MVI_PROP macro to the property tag in the **ulPropTag** member to identify the sort key as a multi-valued column.</span></span> <span data-ttu-id="28bef-143">对多值列排序取决于使用的单个值。</span><span class="sxs-lookup"><span data-stu-id="28bef-143">Sorting on a multi-valued column is based on using the individual values.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="28bef-144">TABLE_SORT_CATEG_MAX TABLE_SORT_CATEG_MIN 可能不定义和可下载头文件中的**ulOrder**成员值后，在这种情况下您可以将其添加到代码中使用以下值： >`#define TABLE_SORT_CATEG_MAX ((ULONG) 0x00000004)`>  `#define TABLE_SORT_CATEG_MIN ((ULONG) 0x00000008)`</span><span class="sxs-lookup"><span data-stu-id="28bef-144">The **ulOrder** member values TABLE_SORT_CATEG_MAX and TABLE_SORT_CATEG_MIN might not be defined in the downloadable header file you currently have, in which case you can add it to your code using the following values: >  `#define TABLE_SORT_CATEG_MAX ((ULONG) 0x00000004)`>  `#define TABLE_SORT_CATEG_MIN ((ULONG) 0x00000008)`</span></span>
  
<span data-ttu-id="28bef-145">有关 standard 和分类排序的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="28bef-145">For more information about standard and categorized sorting, see [Sorting and Categorization](sorting-and-categorization.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="28bef-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28bef-146">See also</span></span>

- [<span data-ttu-id="28bef-147">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="28bef-147">SSortOrderSet</span></span>](ssortorderset.md)
- [<span data-ttu-id="28bef-148">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="28bef-148">MAPI Structures</span></span>](mapi-structures.md)

