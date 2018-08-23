---
title: HrQueryAllRows
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrQueryAllRows
api_type:
- HeaderDef
ms.assetid: b08fadcf-cdf3-48b7-9489-d7f745266482
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c165bcaedfc3dbab0c950d0674228b15dfeee958
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592274"
---
# <a name="hrqueryallrows"></a><span data-ttu-id="1fc65-103">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="1fc65-103">HrQueryAllRows</span></span>

  
  
<span data-ttu-id="1fc65-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1fc65-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1fc65-105">检索表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="1fc65-105">Retrieves all rows of a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1fc65-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="1fc65-106">Header file:</span></span>  <br/> |<span data-ttu-id="1fc65-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="1fc65-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="1fc65-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="1fc65-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="1fc65-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="1fc65-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="1fc65-110">调用：</span><span class="sxs-lookup"><span data-stu-id="1fc65-110">Called by:</span></span>  <br/> |<span data-ttu-id="1fc65-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="1fc65-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrQueryAllRows(
  LPMAPITABLE ptable,
  LPSPropTagArray ptaga,
  LPSRestriction pres,
  LPSSortOrderSet psos,
  LONG crowsMax,
  LPSRowSet FAR * pprows
);
```

## <a name="parameters"></a><span data-ttu-id="1fc65-112">参数</span><span class="sxs-lookup"><span data-stu-id="1fc65-112">Parameters</span></span>

 <span data-ttu-id="1fc65-113">_ptable_</span><span class="sxs-lookup"><span data-stu-id="1fc65-113">_ptable_</span></span>
  
> <span data-ttu-id="1fc65-114">[in]指向从中检索行的 MAPI 表。</span><span class="sxs-lookup"><span data-stu-id="1fc65-114">[in] Pointer to the MAPI table from which rows are retrieved.</span></span> 
    
 <span data-ttu-id="1fc65-115">_ptaga_</span><span class="sxs-lookup"><span data-stu-id="1fc65-115">_ptaga_</span></span>
  
> <span data-ttu-id="1fc65-116">[in]指向包含属性的数组[SPropTagArray](sproptagarray.md)结构标记指示表格列。</span><span class="sxs-lookup"><span data-stu-id="1fc65-116">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags indicating table columns.</span></span> <span data-ttu-id="1fc65-117">这些标记用于选择要检索的特定列。</span><span class="sxs-lookup"><span data-stu-id="1fc65-117">These tags are used to select the specific columns to be retrieved.</span></span> <span data-ttu-id="1fc65-118">如果_ptaga_参数为 NULL，则**HrQueryAllRows**检索当前表视图_ptable_参数中传递的整个列集。</span><span class="sxs-lookup"><span data-stu-id="1fc65-118">If the  _ptaga_ parameter is NULL, **HrQueryAllRows** retrieves the entire column set of the current table view passed in the  _ptable_ parameter.</span></span> 
    
 <span data-ttu-id="1fc65-119">_展示_</span><span class="sxs-lookup"><span data-stu-id="1fc65-119">_pres_</span></span>
  
> <span data-ttu-id="1fc65-120">[in]指向包含检索限制[SRestriction](srestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="1fc65-120">[in] Pointer to an [SRestriction](srestriction.md) structure that contains retrieval restrictions.</span></span> <span data-ttu-id="1fc65-121">如果_展示_参数为 NULL，则**HrQueryAllRows**使没有限制。</span><span class="sxs-lookup"><span data-stu-id="1fc65-121">If the  _pres_ parameter is NULL, **HrQueryAllRows** makes no restrictions.</span></span> 
    
 <span data-ttu-id="1fc65-122">_pso_</span><span class="sxs-lookup"><span data-stu-id="1fc65-122">_psos_</span></span>
  
> <span data-ttu-id="1fc65-123">[in]标识要检索列的排序顺序[SSortOrderSet](ssortorderset.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="1fc65-123">[in] Pointer to an [SSortOrderSet](ssortorderset.md) structure identifying the sort order of the columns to be retrieved.</span></span> <span data-ttu-id="1fc65-124">如果_pso_参数为 NULL，则使用表的默认排序次序。</span><span class="sxs-lookup"><span data-stu-id="1fc65-124">If the  _psos_ parameter is NULL, the default sort order for the table is used.</span></span> 
    
 <span data-ttu-id="1fc65-125">_crowsMax_</span><span class="sxs-lookup"><span data-stu-id="1fc65-125">_crowsMax_</span></span>
  
> <span data-ttu-id="1fc65-126">[in]要检索的行的最大数量。</span><span class="sxs-lookup"><span data-stu-id="1fc65-126">[in] Maximum number of rows to be retrieved.</span></span> <span data-ttu-id="1fc65-127">如果_crowsMax_参数的值为零，检索的行数不限制设置。</span><span class="sxs-lookup"><span data-stu-id="1fc65-127">If the value of the  _crowsMax_ parameter is zero, no limit on the number of rows retrieved is set.</span></span> 
    
 <span data-ttu-id="1fc65-128">_pprows_</span><span class="sxs-lookup"><span data-stu-id="1fc65-128">_pprows_</span></span>
  
> <span data-ttu-id="1fc65-129">[输出]为包含指向检索到的表格行的指针数组返回[SRowSet](srowset.md)结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1fc65-129">[out] Pointer to a pointer to the returned [SRowSet](srowset.md) structure that contains an array of pointers to the retrieved table rows.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1fc65-130">返回值</span><span class="sxs-lookup"><span data-stu-id="1fc65-130">Return value</span></span>

<span data-ttu-id="1fc65-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="1fc65-131">S_OK</span></span> 
  
> <span data-ttu-id="1fc65-132">呼叫检索预期的表格行。</span><span class="sxs-lookup"><span data-stu-id="1fc65-132">The call retrieved the expected rows of a table.</span></span> 
    
<span data-ttu-id="1fc65-133">MAPI_E_TABLE_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="1fc65-133">MAPI_E_TABLE_TOO_BIG</span></span> 
  
> <span data-ttu-id="1fc65-134">值大于数为_crowsMax_参数传递的表中的行数。</span><span class="sxs-lookup"><span data-stu-id="1fc65-134">The number of rows in the table is larger than the number passed for the  _crowsMax_ parameter.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1fc65-135">注解</span><span class="sxs-lookup"><span data-stu-id="1fc65-135">Remarks</span></span>

<span data-ttu-id="1fc65-136">客户端应用程序或服务提供商具有不能控制**HrQueryAllRows**尝试检索，以外通过提出限制_展示_参数指向的行数。</span><span class="sxs-lookup"><span data-stu-id="1fc65-136">A client application or service provider has no control over the number of rows **HrQueryAllRows** attempts to retrieve, other than by imposing a restriction pointed to by the  _pres_ parameter.</span></span> <span data-ttu-id="1fc65-137">_CrowsMax_参数不会限制为特定的表格行数检索但而定义最大可用来保存所有检索的行的内存量。</span><span class="sxs-lookup"><span data-stu-id="1fc65-137">The  _crowsMax_ parameter does not limit the retrieval to a certain number of table rows, but rather defines a maximum amount of memory available to hold all retrieved rows.</span></span> <span data-ttu-id="1fc65-138">仅针对大规模内存溢出保护是通过设置_crowsMax_提供应急功能。</span><span class="sxs-lookup"><span data-stu-id="1fc65-138">The only protection against massive memory overflow is the stopgap feature provided by setting  _crowsMax_.</span></span> <span data-ttu-id="1fc65-139">错误返回 MAPI_E_TABLE_TOO_BIG 意味着表包含太多行一次性彻底保留在内存中。</span><span class="sxs-lookup"><span data-stu-id="1fc65-139">The error return MAPI_E_TABLE_TOO_BIG means the table contains too many rows to be held all at once in memory.</span></span> 
  
<span data-ttu-id="1fc65-140">表的通常较小，如消息存储表或提供程序表中，通常可以安全地检索与**HrQueryAllRows**。</span><span class="sxs-lookup"><span data-stu-id="1fc65-140">Tables that are typically small, such as a message store table or a provider table, usually can be safely retrieved with **HrQueryAllRows**.</span></span> <span data-ttu-id="1fc65-141">应在使用[IMAPITable::QueryRows](imapitable-queryrows.md)方法的小节遍历危险的太大，内容或甚至收件人目录，如表。</span><span class="sxs-lookup"><span data-stu-id="1fc65-141">Tables at risk of being very large, such as a contents table or even a recipients table, should be traversed in subsections using the [IMAPITable::QueryRows](imapitable-queryrows.md) method.</span></span> 
  
<span data-ttu-id="1fc65-142">如果调用**HrQueryAllRows**时未定义任何表属性，也会返回与属性类型 PT_NULL 属性标识符 PROP_ID_NULL</span><span class="sxs-lookup"><span data-stu-id="1fc65-142">If any table properties are undefined when **HrQueryAllRows** is called, they are returned with property type PT_NULL and property identifier PROP_ID_NULL</span></span> 
  

