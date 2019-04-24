---
title: SRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SRow
api_type:
- COM
ms.assetid: 369c2d5c-8c2b-4314-9cb2-aaa89580aa2b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2e75bc6f8e14258787a6c9d80dfbf6334ec698b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336512"
---
# <a name="srow"></a><span data-ttu-id="0a463-103">SRow</span><span class="sxs-lookup"><span data-stu-id="0a463-103">SRow</span></span>

<span data-ttu-id="0a463-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0a463-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0a463-105">描述包含特定对象的选定属性的表中的行。</span><span class="sxs-lookup"><span data-stu-id="0a463-105">Describes a row from a table that contains selected properties for a specific object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0a463-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0a463-106">Header file:</span></span>  <br/> |<span data-ttu-id="0a463-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0a463-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SRow
{
  ULONG ulAdrEntryPad;
  ULONG cValues;
  LPSPropValue lpProps;
} SRow, FAR *LPSRow;

```

## <a name="members"></a><span data-ttu-id="0a463-108">Members</span><span class="sxs-lookup"><span data-stu-id="0a463-108">Members</span></span>

<span data-ttu-id="0a463-109">**ulAdrEntryPad**</span><span class="sxs-lookup"><span data-stu-id="0a463-109">**ulAdrEntryPad**</span></span>
  
> <span data-ttu-id="0a463-110">用于正确对齐**lpProps**成员所指向的属性值的填充字节数。</span><span class="sxs-lookup"><span data-stu-id="0a463-110">Padding bytes to properly align the property values pointed to by the **lpProps** member.</span></span> 
    
<span data-ttu-id="0a463-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="0a463-111">**cValues**</span></span>
  
> <span data-ttu-id="0a463-112">由**lpProps**指向的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="0a463-112">Count of property values pointed to by **lpProps**.</span></span> 
    
<span data-ttu-id="0a463-113">**lpProps**</span><span class="sxs-lookup"><span data-stu-id="0a463-113">**lpProps**</span></span>
  
> <span data-ttu-id="0a463-114">指向描述行中各列的属性值的[SPropValue](spropvalue.md)结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="0a463-114">Pointer to an array of [SPropValue](spropvalue.md) structures that describe the property values for the columns in the row.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="0a463-115">注解</span><span class="sxs-lookup"><span data-stu-id="0a463-115">Remarks</span></span>

<span data-ttu-id="0a463-116">**SRow**结构描述表格中的行。</span><span class="sxs-lookup"><span data-stu-id="0a463-116">An **SRow** structure describes a row in a table.</span></span> <span data-ttu-id="0a463-117">它包含在表通知附带的[TABLE_NOTIFICATION](table_notification.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="0a463-117">It is included in the [TABLE_NOTIFICATION](table_notification.md) structure that accompanies a table notification.</span></span> 
  
<span data-ttu-id="0a463-118">在以下方法中使用**SRow**结构:</span><span class="sxs-lookup"><span data-stu-id="0a463-118">**SRow** structures are used in the following methods:</span></span> 
  
- [<span data-ttu-id="0a463-119">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="0a463-119">IAddrBook::GetSearchPath</span></span>](iaddrbook-getsearchpath.md)
    
- [<span data-ttu-id="0a463-120">IAddrBook::SetSearchPath</span><span class="sxs-lookup"><span data-stu-id="0a463-120">IAddrBook::SetSearchPath</span></span>](iaddrbook-setsearchpath.md)
    
- [<span data-ttu-id="0a463-121">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="0a463-121">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
    
- [<span data-ttu-id="0a463-122">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="0a463-122">IMAPITable::ExpandRow</span></span>](imapitable-expandrow.md)
    
- <span data-ttu-id="0a463-123">[ITableData: IUnknown](itabledataiunknown.md)(多个方法)</span><span class="sxs-lookup"><span data-stu-id="0a463-123">[ITableData : IUnknown](itabledataiunknown.md) (many methods)</span></span> 
    
- [<span data-ttu-id="0a463-124">FBadRowSet</span><span class="sxs-lookup"><span data-stu-id="0a463-124">FBadRowSet</span></span>](fbadrowset.md)
    
- [<span data-ttu-id="0a463-125">FreeProws</span><span class="sxs-lookup"><span data-stu-id="0a463-125">FreeProws</span></span>](freeprows.md)
    
- [<span data-ttu-id="0a463-126">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="0a463-126">HrQueryAllRows</span></span>](hrqueryallrows.md)
    
<span data-ttu-id="0a463-127">如果需要描述多行, 则使用[SRowSet](srowset.md)结构。</span><span class="sxs-lookup"><span data-stu-id="0a463-127">When more than one row needs to be described, an [SRowSet](srowset.md) structure is used.</span></span> <span data-ttu-id="0a463-128">**SRowSet**结构包含**SRow**结构的数组和数组中的结构计数。</span><span class="sxs-lookup"><span data-stu-id="0a463-128">An **SRowSet** structure contains an array of **SRow** structures and a count of structures in the array.</span></span> 
  
<span data-ttu-id="0a463-129">下图显示了**SRow**和**SRowSet**数据结构之间的关系。</span><span class="sxs-lookup"><span data-stu-id="0a463-129">The following illustration shows the relationship between an **SRow** and an **SRowSet** data structure.</span></span> 
  
<span data-ttu-id="0a463-130">**SRow 和 SRowSet 之间的关系**</span><span class="sxs-lookup"><span data-stu-id="0a463-130">**Relationship between SRow and SRowSet**</span></span>
  
<span data-ttu-id="0a463-131">![SRow 和 SRowSet 之间的关系](media/amapi_17.gif "SRow 和 SRowSet 之间的关系")</span><span class="sxs-lookup"><span data-stu-id="0a463-131">![Relationship between SRow and SRowSet](media/amapi_17.gif "Relationship between SRow and SRowSet")</span></span>
  
<span data-ttu-id="0a463-132">**SRow**结构的定义与[ADRENTRY](adrentry.md)结构相同。</span><span class="sxs-lookup"><span data-stu-id="0a463-132">**SRow** structures are defined the same as [ADRENTRY](adrentry.md) structures.</span></span> <span data-ttu-id="0a463-133">因此, 收件人表的行和地址列表中的条目可以被视为相同。</span><span class="sxs-lookup"><span data-stu-id="0a463-133">Therefore, a row of a recipient table and an entry in an address list can be treated the same.</span></span> 
  
<span data-ttu-id="0a463-134">有关应如何分配**SRow**结构的内存的信息, 请参阅[管理内存 for ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="0a463-134">For information about how the memory for **SRow** structures should be allocated, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0a463-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a463-135">See also</span></span>

- [<span data-ttu-id="0a463-136">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="0a463-136">ADRENTRY</span></span>](adrentry.md)
- [<span data-ttu-id="0a463-137">SPropValue</span><span class="sxs-lookup"><span data-stu-id="0a463-137">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="0a463-138">SRowSet</span><span class="sxs-lookup"><span data-stu-id="0a463-138">SRowSet</span></span>](srowset.md)
- [<span data-ttu-id="0a463-139">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="0a463-139">TABLE_NOTIFICATION</span></span>](table_notification.md)
- [<span data-ttu-id="0a463-140">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="0a463-140">MAPI Structures</span></span>](mapi-structures.md)
- [<span data-ttu-id="0a463-141">管理 ADRLIST 和 SRowSet 结构的内存</span><span class="sxs-lookup"><span data-stu-id="0a463-141">Managing Memory for ADRLIST and SRowSet Structures</span></span>](managing-memory-for-adrlist-and-srowset-structures.md)

