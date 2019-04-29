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
# <a name="hrqueryallrows"></a><span data-ttu-id="c50e9-103">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="c50e9-103">HrQueryAllRows</span></span>

  
  
<span data-ttu-id="c50e9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c50e9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c50e9-105">检索表的所有行。</span><span class="sxs-lookup"><span data-stu-id="c50e9-105">Retrieves all rows of a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c50e9-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c50e9-106">Header file:</span></span>  <br/> |<span data-ttu-id="c50e9-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="c50e9-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="c50e9-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="c50e9-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="c50e9-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="c50e9-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="c50e9-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="c50e9-110">Called by:</span></span>  <br/> |<span data-ttu-id="c50e9-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="c50e9-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="c50e9-112">参数</span><span class="sxs-lookup"><span data-stu-id="c50e9-112">Parameters</span></span>

 <span data-ttu-id="c50e9-113">_ptable_</span><span class="sxs-lookup"><span data-stu-id="c50e9-113">_ptable_</span></span>
  
> <span data-ttu-id="c50e9-114">实时指向从中检索行的 MAPI 表的指针。</span><span class="sxs-lookup"><span data-stu-id="c50e9-114">[in] Pointer to the MAPI table from which rows are retrieved.</span></span> 
    
 <span data-ttu-id="c50e9-115">_ptaga_</span><span class="sxs-lookup"><span data-stu-id="c50e9-115">_ptaga_</span></span>
  
> <span data-ttu-id="c50e9-116">实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含指示表列的属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="c50e9-116">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags indicating table columns.</span></span> <span data-ttu-id="c50e9-117">这些标记用于选择要检索的特定列。</span><span class="sxs-lookup"><span data-stu-id="c50e9-117">These tags are used to select the specific columns to be retrieved.</span></span> <span data-ttu-id="c50e9-118">如果_ptaga_参数为 NULL, 则**HrQueryAllRows**将检索在_ptable_参数中传递的当前表格视图的整个列集。</span><span class="sxs-lookup"><span data-stu-id="c50e9-118">If the  _ptaga_ parameter is NULL, **HrQueryAllRows** retrieves the entire column set of the current table view passed in the  _ptable_ parameter.</span></span> 
    
 <span data-ttu-id="c50e9-119">_展示_</span><span class="sxs-lookup"><span data-stu-id="c50e9-119">_pres_</span></span>
  
> <span data-ttu-id="c50e9-120">实时指向包含检索限制的[SRestriction](srestriction.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="c50e9-120">[in] Pointer to an [SRestriction](srestriction.md) structure that contains retrieval restrictions.</span></span> <span data-ttu-id="c50e9-121">如果_展示_参数为 NULL, 则**HrQueryAllRows**不会产生任何限制。</span><span class="sxs-lookup"><span data-stu-id="c50e9-121">If the  _pres_ parameter is NULL, **HrQueryAllRows** makes no restrictions.</span></span> 
    
 <span data-ttu-id="c50e9-122">_pso_</span><span class="sxs-lookup"><span data-stu-id="c50e9-122">_psos_</span></span>
  
> <span data-ttu-id="c50e9-123">实时指向[SSortOrderSet](ssortorderset.md)结构的指针, 该结构标识要检索的列的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="c50e9-123">[in] Pointer to an [SSortOrderSet](ssortorderset.md) structure identifying the sort order of the columns to be retrieved.</span></span> <span data-ttu-id="c50e9-124">如果_pso_参数为 NULL, 则使用表的默认排序顺序。</span><span class="sxs-lookup"><span data-stu-id="c50e9-124">If the  _psos_ parameter is NULL, the default sort order for the table is used.</span></span> 
    
 <span data-ttu-id="c50e9-125">_crowsMax_</span><span class="sxs-lookup"><span data-stu-id="c50e9-125">_crowsMax_</span></span>
  
> <span data-ttu-id="c50e9-126">实时要检索的最大行数。</span><span class="sxs-lookup"><span data-stu-id="c50e9-126">[in] Maximum number of rows to be retrieved.</span></span> <span data-ttu-id="c50e9-127">如果_crowsMax_参数的值为零, 则对检索到的行数的限制不会设置。</span><span class="sxs-lookup"><span data-stu-id="c50e9-127">If the value of the  _crowsMax_ parameter is zero, no limit on the number of rows retrieved is set.</span></span> 
    
 <span data-ttu-id="c50e9-128">_pprows_</span><span class="sxs-lookup"><span data-stu-id="c50e9-128">_pprows_</span></span>
  
> <span data-ttu-id="c50e9-129">排除指向指向返回的[SRowSet](srowset.md)结构的指针的指针, 该结构包含指向检索到的表格行的指针数组。</span><span class="sxs-lookup"><span data-stu-id="c50e9-129">[out] Pointer to a pointer to the returned [SRowSet](srowset.md) structure that contains an array of pointers to the retrieved table rows.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c50e9-130">返回值</span><span class="sxs-lookup"><span data-stu-id="c50e9-130">Return value</span></span>

<span data-ttu-id="c50e9-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="c50e9-131">S_OK</span></span> 
  
> <span data-ttu-id="c50e9-132">调用检索到表的预期行。</span><span class="sxs-lookup"><span data-stu-id="c50e9-132">The call retrieved the expected rows of a table.</span></span> 
    
<span data-ttu-id="c50e9-133">MAPI_E_TABLE_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="c50e9-133">MAPI_E_TABLE_TOO_BIG</span></span> 
  
> <span data-ttu-id="c50e9-134">表中的行数大于为_crowsMax_参数传递的数目。</span><span class="sxs-lookup"><span data-stu-id="c50e9-134">The number of rows in the table is larger than the number passed for the  _crowsMax_ parameter.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c50e9-135">说明</span><span class="sxs-lookup"><span data-stu-id="c50e9-135">Remarks</span></span>

<span data-ttu-id="c50e9-136">客户端应用程序或服务提供程序不能控制**HrQueryAllRows**尝试检索的行数, 而不是通过限制_展示_参数所指向的限制。</span><span class="sxs-lookup"><span data-stu-id="c50e9-136">A client application or service provider has no control over the number of rows **HrQueryAllRows** attempts to retrieve, other than by imposing a restriction pointed to by the  _pres_ parameter.</span></span> <span data-ttu-id="c50e9-137">_crowsMax_参数不会将检索限制为一定数量的表行, 而是定义可用于保存所有检索到的行的最大内存量。</span><span class="sxs-lookup"><span data-stu-id="c50e9-137">The  _crowsMax_ parameter does not limit the retrieval to a certain number of table rows, but rather defines a maximum amount of memory available to hold all retrieved rows.</span></span> <span data-ttu-id="c50e9-138">对对大量内存溢出的唯一保护是通过设置_crowsMax_提供的 stopgap 功能。</span><span class="sxs-lookup"><span data-stu-id="c50e9-138">The only protection against massive memory overflow is the stopgap feature provided by setting  _crowsMax_.</span></span> <span data-ttu-id="c50e9-139">错误返回 MAPI_E_TABLE_TOO_BIG 表示该表包含的行太多, 无法同时保留在内存中。</span><span class="sxs-lookup"><span data-stu-id="c50e9-139">The error return MAPI_E_TABLE_TOO_BIG means the table contains too many rows to be held all at once in memory.</span></span> 
  
<span data-ttu-id="c50e9-140">通常情况下, 可以使用**HrQueryAllRows**安全地检索通常很小的表 (如邮件存储表或提供程序表)。</span><span class="sxs-lookup"><span data-stu-id="c50e9-140">Tables that are typically small, such as a message store table or a provider table, usually can be safely retrieved with **HrQueryAllRows**.</span></span> <span data-ttu-id="c50e9-141">应使用[IMAPITable:: QueryRows](imapitable-queryrows.md)方法在子部分中遍历非常大的风险 (如内容表甚至收件人表) 中的表。</span><span class="sxs-lookup"><span data-stu-id="c50e9-141">Tables at risk of being very large, such as a contents table or even a recipients table, should be traversed in subsections using the [IMAPITable::QueryRows](imapitable-queryrows.md) method.</span></span> 
  
<span data-ttu-id="c50e9-142">如果在调用**HrQueryAllRows**时未定义任何表属性, 则将使用属性类型 PT_NULL 和属性标识符返回它们 PROP_ID_NULL</span><span class="sxs-lookup"><span data-stu-id="c50e9-142">If any table properties are undefined when **HrQueryAllRows** is called, they are returned with property type PT_NULL and property identifier PROP_ID_NULL</span></span> 
  

