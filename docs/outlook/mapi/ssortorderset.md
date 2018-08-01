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
ms.openlocfilehash: 1604c4a1a0d1bf4008595b0d150b4f7eb3d1c2ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778871"
---
# <a name="ssortorderset"></a><span data-ttu-id="c61c9-103">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="c61c9-103">SSortOrderSet</span></span>

  
  
<span data-ttu-id="c61c9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c61c9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c61c9-105">定义一个表，用于标准或分类排序的排序关键字的集合。</span><span class="sxs-lookup"><span data-stu-id="c61c9-105">Defines a collection of sort keys for a table that is used for standard or categorized sorting.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c61c9-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c61c9-106">Header file:</span></span>  <br/> |<span data-ttu-id="c61c9-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c61c9-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="c61c9-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="c61c9-108">Related macros:</span></span>  <br/> |<span data-ttu-id="c61c9-109">[CbNewSSortOrderSet](cbnewssortorderset.md)， [CbSSortOrderSet](cbssortorderset.md)， [SizedSSortOrderSet](sizedssortorderset.md)</span><span class="sxs-lookup"><span data-stu-id="c61c9-109">[CbNewSSortOrderSet](cbnewssortorderset.md), [CbSSortOrderSet](cbssortorderset.md), [SizedSSortOrderSet](sizedssortorderset.md)</span></span> <br/> |
   
```cpp
typedef struct _SSortOrderSet
{
  ULONG cSorts;
  ULONG cCategories;
  ULONG cExpanded;
  SSortOrder aSort[MAPI_DIM];
} SSortOrderSet, FAR *LPSSortOrderSet;

```

## <a name="members"></a><span data-ttu-id="c61c9-110">Members</span><span class="sxs-lookup"><span data-stu-id="c61c9-110">Members</span></span>

 <span data-ttu-id="c61c9-111">**cSorts**</span><span class="sxs-lookup"><span data-stu-id="c61c9-111">**cSorts**</span></span>
  
> <span data-ttu-id="c61c9-112">[SSortOrder](ssortorder.md)结构**aSort**成员中包含的计数。</span><span class="sxs-lookup"><span data-stu-id="c61c9-112">Count of [SSortOrder](ssortorder.md) structures that are included in the **aSort** member.</span></span> 
    
 <span data-ttu-id="c61c9-113">**cCategories**</span><span class="sxs-lookup"><span data-stu-id="c61c9-113">**cCategories**</span></span>
  
> <span data-ttu-id="c61c9-114">指定为类别列的列数。</span><span class="sxs-lookup"><span data-stu-id="c61c9-114">Count of columns that are designated as category columns.</span></span> <span data-ttu-id="c61c9-115">可能的值范围为 0，表示非分类或标准排序，复制到由**cSorts**成员指示的数字。</span><span class="sxs-lookup"><span data-stu-id="c61c9-115">Possible values range from zero, which indicates a non-categorized or standard sort, to the number indicated by the **cSorts** member.</span></span> 
    
 <span data-ttu-id="c61c9-116">**cExpanded**</span><span class="sxs-lookup"><span data-stu-id="c61c9-116">**cExpanded**</span></span>
  
> <span data-ttu-id="c61c9-117">启动的所有行的适用于类别是可见的表视图中展开状态的类别的计数。</span><span class="sxs-lookup"><span data-stu-id="c61c9-117">Count of categories that start in an expanded state, where all of the rows that apply to the category are visible in the table view.</span></span> <span data-ttu-id="c61c9-118">可能的值范围为从 0 到由**cCategories**指示的数字。</span><span class="sxs-lookup"><span data-stu-id="c61c9-118">Possible values range from 0 to the number indicated by **cCategories**.</span></span>
    
 <span data-ttu-id="c61c9-119">**aSort**</span><span class="sxs-lookup"><span data-stu-id="c61c9-119">**aSort**</span></span>
  
> <span data-ttu-id="c61c9-120">每个定义排序顺序的**SSortOrder**结构数组。</span><span class="sxs-lookup"><span data-stu-id="c61c9-120">Array of **SSortOrder** structures, each defining a sort order.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c61c9-121">说明</span><span class="sxs-lookup"><span data-stu-id="c61c9-121">Remarks</span></span>

<span data-ttu-id="c61c9-122">**SSortOrderSet**结构用于定义多个标准和分类排序的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="c61c9-122">A **SSortOrderSet** structure is used for defining multiple sort orders for standard and categorized sorting.</span></span> 
  
<span data-ttu-id="c61c9-123">每个**SSortOrderSet**结构包含至少一个**SSortOrder**结构定义方向的排序和将用作排序关键字列。</span><span class="sxs-lookup"><span data-stu-id="c61c9-123">Each **SSortOrderSet** structure contains at least one **SSortOrder** structure defining the direction of the sort and the column that will be used as the sort key.</span></span> <span data-ttu-id="c61c9-124">对于分类排序，此列将用作类别。</span><span class="sxs-lookup"><span data-stu-id="c61c9-124">For categorized sorting, this column is used as the category.</span></span> <span data-ttu-id="c61c9-125">时**cSorts**成员的值超出**cCategories**成员的值，有多个排序关键字比类别，并显示第一个**SSortOrder**数组中的列中创建的类别。</span><span class="sxs-lookup"><span data-stu-id="c61c9-125">When the value of the **cSorts** member exceeds the value of the **cCategories** member, there are more sort keys than categories, and categories are created from the columns that appear first in the **SSortOrder** array.</span></span> 
  
<span data-ttu-id="c61c9-126">例如，如果**cSorts**设置为 3 和**cCategories**设置为 2，由**SSortOrder**数组中的前两个条目**ulPropTag**成员所述的列用作类别列。</span><span class="sxs-lookup"><span data-stu-id="c61c9-126">For example, if **cSorts** is set to 3 and **cCategories** is set to 2, the columns described by the **ulPropTag** member of the first two entries in the **SSortOrder** array are used as the category columns.</span></span> <span data-ttu-id="c61c9-127">第一个条目充当顶级类别分组;为辅助分组第二个条目。</span><span class="sxs-lookup"><span data-stu-id="c61c9-127">The first entry serves as the top-level category grouping; the second entry as the secondary grouping.</span></span> <span data-ttu-id="c61c9-128">所有匹配的两个类别列的行进行排序使用第三项中定义的排序密钥。</span><span class="sxs-lookup"><span data-stu-id="c61c9-128">All of the rows that match the two category columns are sorted by using the sort key defined in the third entry.</span></span> 
  
<span data-ttu-id="c61c9-129">**CExpanded**成员指定第一个在展开的分类的数。</span><span class="sxs-lookup"><span data-stu-id="c61c9-129">The **cExpanded** member specifies the number of categories that are at first expanded.</span></span> <span data-ttu-id="c61c9-130">当存在多个类别时，表实现开头的第一列被指定为一个类别，并继续按顺序使用后续类别列，直到**cCategories**数超过。</span><span class="sxs-lookup"><span data-stu-id="c61c9-130">When there are multiple categories, the table implementation starts with the first column to be designated as a category and continues in sequential order with the subsequent category columns until the number of **cCategories** has been exceeded.</span></span> <span data-ttu-id="c61c9-131">如果有多个类别列比扩展的列，，折叠类别列。</span><span class="sxs-lookup"><span data-stu-id="c61c9-131">If there are more category columns than there are expanded columns, the category columns are collapsed.</span></span> <span data-ttu-id="c61c9-132">如果**cExpanded**等于零，则仅顶部级别的标题行位于表用户的显示。</span><span class="sxs-lookup"><span data-stu-id="c61c9-132">If **cExpanded** is equal to zero, only the top level heading row is available to the table user for display.</span></span> <span data-ttu-id="c61c9-133">如果**cExpanded**等于减数类别，然后的所有标题行和叶行均不可用。</span><span class="sxs-lookup"><span data-stu-id="c61c9-133">If **cExpanded** is equal to one less than the number of categories, then all of the heading rows and none of the leaf rows are available.</span></span> <span data-ttu-id="c61c9-134">如果**cExpanded**等于的分类数，则完全扩展表。</span><span class="sxs-lookup"><span data-stu-id="c61c9-134">If **cExpanded** is equal to the number of categories, then the table is fully expanded.</span></span> 
  
<span data-ttu-id="c61c9-135">有关 standard 和分类排序的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="c61c9-135">For more information about standard and categorized sorting, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c61c9-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c61c9-136">See also</span></span>



[<span data-ttu-id="c61c9-137">SSortOrder</span><span class="sxs-lookup"><span data-stu-id="c61c9-137">SSortOrder</span></span>](ssortorder.md)
  
[<span data-ttu-id="c61c9-138">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="c61c9-138">IMAPITable::ExpandRow</span></span>](imapitable-expandrow.md)
  
[<span data-ttu-id="c61c9-139">IMAPITable::CollapseRow</span><span class="sxs-lookup"><span data-stu-id="c61c9-139">IMAPITable::CollapseRow</span></span>](imapitable-collapserow.md)


[<span data-ttu-id="c61c9-140">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c61c9-140">MAPI Structures</span></span>](mapi-structures.md)

