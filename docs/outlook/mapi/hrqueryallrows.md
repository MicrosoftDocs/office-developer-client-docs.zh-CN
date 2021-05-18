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
ms.openlocfilehash: 0f09304f21180d9ebc2a1e1dcc54ebadd3622804
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422892"
---
# <a name="hrqueryallrows"></a><span data-ttu-id="a6b4f-103">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="a6b4f-103">HrQueryAllRows</span></span>

  
  
<span data-ttu-id="a6b4f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a6b4f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a6b4f-105">检索表的所有行。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-105">Retrieves all rows of a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a6b4f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a6b4f-106">Header file:</span></span>  <br/> |<span data-ttu-id="a6b4f-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="a6b4f-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="a6b4f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="a6b4f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a6b4f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a6b4f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a6b4f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="a6b4f-110">Called by:</span></span>  <br/> |<span data-ttu-id="a6b4f-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="a6b4f-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="a6b4f-112">参数</span><span class="sxs-lookup"><span data-stu-id="a6b4f-112">Parameters</span></span>

 <span data-ttu-id="a6b4f-113">_ptable_</span><span class="sxs-lookup"><span data-stu-id="a6b4f-113">_ptable_</span></span>
  
> <span data-ttu-id="a6b4f-114">[in]指向从中检索行的 MAPI 表的指针。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-114">[in] Pointer to the MAPI table from which rows are retrieved.</span></span> 
    
 <span data-ttu-id="a6b4f-115">_ptaga_</span><span class="sxs-lookup"><span data-stu-id="a6b4f-115">_ptaga_</span></span>
  
> <span data-ttu-id="a6b4f-116">[in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，该结构包含指示表列的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-116">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags indicating table columns.</span></span> <span data-ttu-id="a6b4f-117">这些标记用于选择要检索的特定列。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-117">These tags are used to select the specific columns to be retrieved.</span></span> <span data-ttu-id="a6b4f-118">如果  _ptaga_ 参数为 **NULL，HrQueryAllRows** 将检索在  _ptable_ 参数中传递的当前表视图的整个列集。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-118">If the  _ptaga_ parameter is NULL, **HrQueryAllRows** retrieves the entire column set of the current table view passed in the  _ptable_ parameter.</span></span> 
    
 <span data-ttu-id="a6b4f-119">_pres_</span><span class="sxs-lookup"><span data-stu-id="a6b4f-119">_pres_</span></span>
  
> <span data-ttu-id="a6b4f-120">[in]指向包含检索限制的 [SRestriction](srestriction.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-120">[in] Pointer to an [SRestriction](srestriction.md) structure that contains retrieval restrictions.</span></span> <span data-ttu-id="a6b4f-121">如果  _pres_ 参数为 NULL， **则 HrQueryAllRows** 将没有任何限制。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-121">If the  _pres_ parameter is NULL, **HrQueryAllRows** makes no restrictions.</span></span> 
    
 <span data-ttu-id="a6b4f-122">_psos_</span><span class="sxs-lookup"><span data-stu-id="a6b4f-122">_psos_</span></span>
  
> <span data-ttu-id="a6b4f-123">[in]指向标识要检索的列的排序顺序的 [SSortOrderSet](ssortorderset.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-123">[in] Pointer to an [SSortOrderSet](ssortorderset.md) structure identifying the sort order of the columns to be retrieved.</span></span> <span data-ttu-id="a6b4f-124">如果  _psos_ 参数为 NULL，则使用表的默认排序顺序。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-124">If the  _psos_ parameter is NULL, the default sort order for the table is used.</span></span> 
    
 <span data-ttu-id="a6b4f-125">_一些_</span><span class="sxs-lookup"><span data-stu-id="a6b4f-125">_crowsMax_</span></span>
  
> <span data-ttu-id="a6b4f-126">[in]要检索的最大行数。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-126">[in] Maximum number of rows to be retrieved.</span></span> <span data-ttu-id="a6b4f-127">如果  _为 0，则对_ 检索到的行数没有限制。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-127">If the value of the  _crowsMax_ parameter is zero, no limit on the number of rows retrieved is set.</span></span> 
    
 <span data-ttu-id="a6b4f-128">_pprows_</span><span class="sxs-lookup"><span data-stu-id="a6b4f-128">_pprows_</span></span>
  
> <span data-ttu-id="a6b4f-129">[out]指向返回的 [SRowSet](srowset.md) 结构的指针的指针，该结构包含指向检索到的表行的指针数组。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-129">[out] Pointer to a pointer to the returned [SRowSet](srowset.md) structure that contains an array of pointers to the retrieved table rows.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a6b4f-130">返回值</span><span class="sxs-lookup"><span data-stu-id="a6b4f-130">Return value</span></span>

<span data-ttu-id="a6b4f-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6b4f-131">S_OK</span></span> 
  
> <span data-ttu-id="a6b4f-132">调用检索表的预期行。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-132">The call retrieved the expected rows of a table.</span></span> 
    
<span data-ttu-id="a6b4f-133">MAPI_E_TABLE_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="a6b4f-133">MAPI_E_TABLE_TOO_BIG</span></span> 
  
> <span data-ttu-id="a6b4f-134">表格中的行数大于为  _用户传递的 rowssMax_ 参数所传递的行数。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-134">The number of rows in the table is larger than the number passed for the  _crowsMax_ parameter.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a6b4f-135">备注</span><span class="sxs-lookup"><span data-stu-id="a6b4f-135">Remarks</span></span>

<span data-ttu-id="a6b4f-136">客户端应用程序或服务提供商无法控制 **HrQueryAllRows** 尝试检索的行数，但通过阻止  _pres_ 参数指向的限制。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-136">A client application or service provider has no control over the number of rows **HrQueryAllRows** attempts to retrieve, other than by imposing a restriction pointed to by the  _pres_ parameter.</span></span> <span data-ttu-id="a6b4f-137">_一个系统_ 参数不限制检索到一定数量的表行，而是定义可用于保留所有检索到的行的最大内存量。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-137">The  _crowsMax_ parameter does not limit the retrieval to a certain number of table rows, but rather defines a maximum amount of memory available to hold all retrieved rows.</span></span> <span data-ttu-id="a6b4f-138">防止大量内存溢出的唯一保护是 stopgap 功能，它通过  _设置 overflowsMax 提供_。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-138">The only protection against massive memory overflow is the stopgap feature provided by setting  _crowsMax_.</span></span> <span data-ttu-id="a6b4f-139">错误返回MAPI_E_TABLE_TOO_BIG意味着表包含太多行，无法一次在内存中全部存储。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-139">The error return MAPI_E_TABLE_TOO_BIG means the table contains too many rows to be held all at once in memory.</span></span> 
  
<span data-ttu-id="a6b4f-140">通常较小的表（如邮件存储表或提供程序表）通常可以使用 **HrQueryAllRows** 安全检索。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-140">Tables that are typically small, such as a message store table or a provider table, usually can be safely retrieved with **HrQueryAllRows**.</span></span> <span data-ttu-id="a6b4f-141">应该使用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法在子节中遍历风险非常大的表，如内容表甚至收件人表。</span><span class="sxs-lookup"><span data-stu-id="a6b4f-141">Tables at risk of being very large, such as a contents table or even a recipients table, should be traversed in subsections using the [IMAPITable::QueryRows](imapitable-queryrows.md) method.</span></span> 
  
<span data-ttu-id="a6b4f-142">如果调用 **HrQueryAllRows** 时未定义任何表属性，则返回的属性类型为 PT_NULL，属性标识符为 PROP_ID_NULL</span><span class="sxs-lookup"><span data-stu-id="a6b4f-142">If any table properties are undefined when **HrQueryAllRows** is called, they are returned with property type PT_NULL and property identifier PROP_ID_NULL</span></span> 
  

