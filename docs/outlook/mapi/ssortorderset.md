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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344420"
---
# <a name="ssortorderset"></a><span data-ttu-id="1f826-103">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="1f826-103">SSortOrderSet</span></span>

  
  
<span data-ttu-id="1f826-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f826-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f826-105">为用于标准或分类排序的表定义排序键的集合。</span><span class="sxs-lookup"><span data-stu-id="1f826-105">Defines a collection of sort keys for a table that is used for standard or categorized sorting.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1f826-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1f826-106">Header file:</span></span>  <br/> |<span data-ttu-id="1f826-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="1f826-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="1f826-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="1f826-108">Related macros:</span></span>  <br/> |<span data-ttu-id="1f826-109">[CbNewSSortOrderSet](cbnewssortorderset.md)、 [CbSSortOrderSet](cbssortorderset.md)、 [SizedSSortOrderSet](sizedssortorderset.md)</span><span class="sxs-lookup"><span data-stu-id="1f826-109">[CbNewSSortOrderSet](cbnewssortorderset.md), [CbSSortOrderSet](cbssortorderset.md), [SizedSSortOrderSet](sizedssortorderset.md)</span></span> <br/> |
   
```cpp
typedef struct _SSortOrderSet
{
  ULONG cSorts;
  ULONG cCategories;
  ULONG cExpanded;
  SSortOrder aSort[MAPI_DIM];
} SSortOrderSet, FAR *LPSSortOrderSet;

```

## <a name="members"></a><span data-ttu-id="1f826-110">Members</span><span class="sxs-lookup"><span data-stu-id="1f826-110">Members</span></span>

 <span data-ttu-id="1f826-111">**cSorts**</span><span class="sxs-lookup"><span data-stu-id="1f826-111">**cSorts**</span></span>
  
> <span data-ttu-id="1f826-112">**根据**成员中包含的[SSortOrder](ssortorder.md)结构的计数。</span><span class="sxs-lookup"><span data-stu-id="1f826-112">Count of [SSortOrder](ssortorder.md) structures that are included in the **aSort** member.</span></span> 
    
 <span data-ttu-id="1f826-113">**cCategories**</span><span class="sxs-lookup"><span data-stu-id="1f826-113">**cCategories**</span></span>
  
> <span data-ttu-id="1f826-114">指定为类别列的列的计数。</span><span class="sxs-lookup"><span data-stu-id="1f826-114">Count of columns that are designated as category columns.</span></span> <span data-ttu-id="1f826-115">可能的值范围为零, 表示对**cSorts**成员指示的数字进行了非分类或标准排序。</span><span class="sxs-lookup"><span data-stu-id="1f826-115">Possible values range from zero, which indicates a non-categorized or standard sort, to the number indicated by the **cSorts** member.</span></span> 
    
 <span data-ttu-id="1f826-116">**cExpanded**</span><span class="sxs-lookup"><span data-stu-id="1f826-116">**cExpanded**</span></span>
  
> <span data-ttu-id="1f826-117">以展开状态启动的类别的计数, 其中所有适用于该类别的行都显示在表格视图中。</span><span class="sxs-lookup"><span data-stu-id="1f826-117">Count of categories that start in an expanded state, where all of the rows that apply to the category are visible in the table view.</span></span> <span data-ttu-id="1f826-118">可能的值范围为0到**cCategories**指示的数字。</span><span class="sxs-lookup"><span data-stu-id="1f826-118">Possible values range from 0 to the number indicated by **cCategories**.</span></span>
    
 <span data-ttu-id="1f826-119">**根据**</span><span class="sxs-lookup"><span data-stu-id="1f826-119">**aSort**</span></span>
  
> <span data-ttu-id="1f826-120">**SSortOrder**结构的数组, 每个结构定义一个排序顺序。</span><span class="sxs-lookup"><span data-stu-id="1f826-120">Array of **SSortOrder** structures, each defining a sort order.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1f826-121">注解</span><span class="sxs-lookup"><span data-stu-id="1f826-121">Remarks</span></span>

<span data-ttu-id="1f826-122">**SSortOrderSet**结构用于定义标准排序和分类排序的多个排序顺序。</span><span class="sxs-lookup"><span data-stu-id="1f826-122">A **SSortOrderSet** structure is used for defining multiple sort orders for standard and categorized sorting.</span></span> 
  
<span data-ttu-id="1f826-123">每个**SSortOrderSet**结构至少包含一个**SSortOrder**结构, 用于定义排序的方向以及将用作排序关键字的列。</span><span class="sxs-lookup"><span data-stu-id="1f826-123">Each **SSortOrderSet** structure contains at least one **SSortOrder** structure defining the direction of the sort and the column that will be used as the sort key.</span></span> <span data-ttu-id="1f826-124">对于分类排序, 该列用作类别。</span><span class="sxs-lookup"><span data-stu-id="1f826-124">For categorized sorting, this column is used as the category.</span></span> <span data-ttu-id="1f826-125">当**cSorts**成员的值超过**cCategories**成员的值时, 会有多个排序关键字, 而不是类别, 而是在**SSortOrder**数组中的第一个显示的列中创建类别。</span><span class="sxs-lookup"><span data-stu-id="1f826-125">When the value of the **cSorts** member exceeds the value of the **cCategories** member, there are more sort keys than categories, and categories are created from the columns that appear first in the **SSortOrder** array.</span></span> 
  
<span data-ttu-id="1f826-126">例如, 如果将**cSorts**设置为 3, 并将**cCategories**设置为 2, 则**SSortOrder**数组中前两个条目的**ulPropTag**成员所描述的列将用作分类列。</span><span class="sxs-lookup"><span data-stu-id="1f826-126">For example, if **cSorts** is set to 3 and **cCategories** is set to 2, the columns described by the **ulPropTag** member of the first two entries in the **SSortOrder** array are used as the category columns.</span></span> <span data-ttu-id="1f826-127">第一个条目充当顶级类别分组;第二个条目, 作为辅助分组。</span><span class="sxs-lookup"><span data-stu-id="1f826-127">The first entry serves as the top-level category grouping; the second entry as the secondary grouping.</span></span> <span data-ttu-id="1f826-128">将使用第三个条目中定义的排序关键字对匹配两个类别列的所有行进行排序。</span><span class="sxs-lookup"><span data-stu-id="1f826-128">All of the rows that match the two category columns are sorted by using the sort key defined in the third entry.</span></span> 
  
<span data-ttu-id="1f826-129">**cExpanded**成员指定首次展开的类别的数目。</span><span class="sxs-lookup"><span data-stu-id="1f826-129">The **cExpanded** member specifies the number of categories that are at first expanded.</span></span> <span data-ttu-id="1f826-130">如果有多个类别, 则表实现将从要指定为类别的第一列开始, 并按后续类别列继续按顺序继续排列, 直到超出**cCategories**的数量。</span><span class="sxs-lookup"><span data-stu-id="1f826-130">When there are multiple categories, the table implementation starts with the first column to be designated as a category and continues in sequential order with the subsequent category columns until the number of **cCategories** has been exceeded.</span></span> <span data-ttu-id="1f826-131">如果类别列多于扩展的列, 则会折叠类别列。</span><span class="sxs-lookup"><span data-stu-id="1f826-131">If there are more category columns than there are expanded columns, the category columns are collapsed.</span></span> <span data-ttu-id="1f826-132">如果**cExpanded**等于零, 则只有顶级标题行可供表用户显示。</span><span class="sxs-lookup"><span data-stu-id="1f826-132">If **cExpanded** is equal to zero, only the top level heading row is available to the table user for display.</span></span> <span data-ttu-id="1f826-133">如果**cExpanded**小于类别的数目, 则所有标题行和无叶行均可用。</span><span class="sxs-lookup"><span data-stu-id="1f826-133">If **cExpanded** is equal to one less than the number of categories, then all of the heading rows and none of the leaf rows are available.</span></span> <span data-ttu-id="1f826-134">如果**cExpanded**等于类别的数目, 则完全展开表。</span><span class="sxs-lookup"><span data-stu-id="1f826-134">If **cExpanded** is equal to the number of categories, then the table is fully expanded.</span></span> 
  
<span data-ttu-id="1f826-135">有关标准排序和已分类排序的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="1f826-135">For more information about standard and categorized sorting, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1f826-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f826-136">See also</span></span>



[<span data-ttu-id="1f826-137">SSortOrder</span><span class="sxs-lookup"><span data-stu-id="1f826-137">SSortOrder</span></span>](ssortorder.md)
  
[<span data-ttu-id="1f826-138">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="1f826-138">IMAPITable::ExpandRow</span></span>](imapitable-expandrow.md)
  
[<span data-ttu-id="1f826-139">IMAPITable::CollapseRow</span><span class="sxs-lookup"><span data-stu-id="1f826-139">IMAPITable::CollapseRow</span></span>](imapitable-collapserow.md)


[<span data-ttu-id="1f826-140">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="1f826-140">MAPI Structures</span></span>](mapi-structures.md)

