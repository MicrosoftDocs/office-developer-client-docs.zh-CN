---
title: IMAPITableGetStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.GetStatus
api_type:
- COM
ms.assetid: f114f1fa-bc05-4587-875b-71548c5912ea
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ec305fc872d1bf1718592dabdd230617d50d3f54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328894"
---
# <a name="imapitablegetstatus"></a><span data-ttu-id="53b0c-103">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="53b0c-103">IMAPITable::GetStatus</span></span>

  
  
<span data-ttu-id="53b0c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53b0c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53b0c-105">返回表的状态和类型。</span><span class="sxs-lookup"><span data-stu-id="53b0c-105">Returns the table's status and type.</span></span>
  
```cpp
HRESULT GetStatus(
ULONG FAR * lpulTableStatus,
ULONG FAR * lpulTableType
);
```

## <a name="parameters"></a><span data-ttu-id="53b0c-106">参数</span><span class="sxs-lookup"><span data-stu-id="53b0c-106">Parameters</span></span>

 <span data-ttu-id="53b0c-107">_lpulTableStatus_</span><span class="sxs-lookup"><span data-stu-id="53b0c-107">_lpulTableStatus_</span></span>
  
> <span data-ttu-id="53b0c-108">排除指向一个指示表状态的值的指针。</span><span class="sxs-lookup"><span data-stu-id="53b0c-108">[out] Pointer to a value indicating the status of the table.</span></span> <span data-ttu-id="53b0c-109">可以返回下列值之一:</span><span class="sxs-lookup"><span data-stu-id="53b0c-109">One of the following values can be returned:</span></span>
    
<span data-ttu-id="53b0c-110">TBLSTAT_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="53b0c-110">TBLSTAT_COMPLETE</span></span> 
  
> <span data-ttu-id="53b0c-111">没有正在进行的操作。</span><span class="sxs-lookup"><span data-stu-id="53b0c-111">No operations are in progress.</span></span>
    
<span data-ttu-id="53b0c-112">TBLSTAT_QCHANGED</span><span class="sxs-lookup"><span data-stu-id="53b0c-112">TBLSTAT_QCHANGED</span></span> 
  
> <span data-ttu-id="53b0c-113">表的内容已更改 expectantly。</span><span class="sxs-lookup"><span data-stu-id="53b0c-113">The contents of the table have expectantly changed.</span></span> <span data-ttu-id="53b0c-114">对于由排序或限制操作导致的更改, 不会返回此状态值。</span><span class="sxs-lookup"><span data-stu-id="53b0c-114">This status value is not returned for changes that result from sort or restriction operations.</span></span>
    
<span data-ttu-id="53b0c-115">TBLSTAT_RESTRICT_ERROR</span><span class="sxs-lookup"><span data-stu-id="53b0c-115">TBLSTAT_RESTRICT_ERROR</span></span> 
  
> <span data-ttu-id="53b0c-116">[IMAPITable:: Restrict](imapitable-restrict.md)操作期间发生错误。</span><span class="sxs-lookup"><span data-stu-id="53b0c-116">An error occurred during an [IMAPITable::Restrict](imapitable-restrict.md) operation.</span></span> 
    
<span data-ttu-id="53b0c-117">TBLSTAT_RESTRICTING</span><span class="sxs-lookup"><span data-stu-id="53b0c-117">TBLSTAT_RESTRICTING</span></span> 
  
> <span data-ttu-id="53b0c-118">**IMAPITable:: Restrict**操作正在进行中。</span><span class="sxs-lookup"><span data-stu-id="53b0c-118">An **IMAPITable::Restrict** operation is in progress.</span></span> 
    
<span data-ttu-id="53b0c-119">TBLSTAT_SETCOL_ERROR</span><span class="sxs-lookup"><span data-stu-id="53b0c-119">TBLSTAT_SETCOL_ERROR</span></span> 
  
> <span data-ttu-id="53b0c-120">[IMAPITable:: SetColumns](imapitable-setcolumns.md)操作期间发生错误。</span><span class="sxs-lookup"><span data-stu-id="53b0c-120">An error occurred during an [IMAPITable::SetColumns](imapitable-setcolumns.md) operation.</span></span> 
    
<span data-ttu-id="53b0c-121">TBLSTAT_SETTING_COLS</span><span class="sxs-lookup"><span data-stu-id="53b0c-121">TBLSTAT_SETTING_COLS</span></span> 
  
> <span data-ttu-id="53b0c-122">**IMAPITable:: SetColumns**操作正在进行中。</span><span class="sxs-lookup"><span data-stu-id="53b0c-122">An **IMAPITable::SetColumns** operation is in progress.</span></span> 
    
<span data-ttu-id="53b0c-123">TBLSTAT_SORT_ERROR</span><span class="sxs-lookup"><span data-stu-id="53b0c-123">TBLSTAT_SORT_ERROR</span></span> 
  
> <span data-ttu-id="53b0c-124">[IMAPITable:: SortTable](imapitable-sorttable.md)操作期间发生错误。</span><span class="sxs-lookup"><span data-stu-id="53b0c-124">An error occurred during an [IMAPITable::SortTable](imapitable-sorttable.md) operation.</span></span> 
    
<span data-ttu-id="53b0c-125">TBLSTAT_SORTING</span><span class="sxs-lookup"><span data-stu-id="53b0c-125">TBLSTAT_SORTING</span></span> 
  
> <span data-ttu-id="53b0c-126">**IMAPITable:: SortTable**操作正在进行中。</span><span class="sxs-lookup"><span data-stu-id="53b0c-126">An **IMAPITable::SortTable** operation is in progress.</span></span> 
    
 <span data-ttu-id="53b0c-127">_lpulTableType_</span><span class="sxs-lookup"><span data-stu-id="53b0c-127">_lpulTableType_</span></span>
  
> <span data-ttu-id="53b0c-128">排除指向指示表的类型的值的指针。</span><span class="sxs-lookup"><span data-stu-id="53b0c-128">[out] Pointer to a value that indicates the table's type.</span></span> <span data-ttu-id="53b0c-129">可以返回以下三种表格类型之一:</span><span class="sxs-lookup"><span data-stu-id="53b0c-129">One of the following three table types can be returned:</span></span>
    
<span data-ttu-id="53b0c-130">TBLTYPE_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="53b0c-130">TBLTYPE_DYNAMIC</span></span> 
  
> <span data-ttu-id="53b0c-131">表的内容是动态的;行和列的值会随着基础数据的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="53b0c-131">The table's contents are dynamic; the rows and column values can change as the underlying data changes.</span></span>
    
<span data-ttu-id="53b0c-132">TBLTYPE_KEYSET</span><span class="sxs-lookup"><span data-stu-id="53b0c-132">TBLTYPE_KEYSET</span></span> 
  
> <span data-ttu-id="53b0c-133">表中的行是固定的, 但这些行中的列的值是动态的, 并且可以随着基础数据的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="53b0c-133">The rows within the table are fixed, but the values of the columns within these rows are dynamic and can change as the underlying data changes.</span></span>
    
<span data-ttu-id="53b0c-134">TBLTYPE_SNAPSHOT</span><span class="sxs-lookup"><span data-stu-id="53b0c-134">TBLTYPE_SNAPSHOT</span></span> 
  
> <span data-ttu-id="53b0c-135">该表是静态的, 并且在基础数据发生更改时它的内容不会更改。</span><span class="sxs-lookup"><span data-stu-id="53b0c-135">The table is static, and its contents do not change when the underlying data changes.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="53b0c-136">返回值</span><span class="sxs-lookup"><span data-stu-id="53b0c-136">Return value</span></span>

<span data-ttu-id="53b0c-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="53b0c-137">S_OK</span></span> 
  
> <span data-ttu-id="53b0c-138">成功返回表的状态。</span><span class="sxs-lookup"><span data-stu-id="53b0c-138">The table's status was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="53b0c-139">注解</span><span class="sxs-lookup"><span data-stu-id="53b0c-139">Remarks</span></span>

<span data-ttu-id="53b0c-140">**IMAPTable:: GetStatus**方法检索有关表的类型和当前状态的信息。</span><span class="sxs-lookup"><span data-stu-id="53b0c-140">The **IMAPTable::GetStatus** method retrieves information about a table's type and current status.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="53b0c-141">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="53b0c-141">Notes to callers</span></span>

<span data-ttu-id="53b0c-142">您可以将**GetStatus**与其他三个**IMAPITable**方法结合使用, 以监视这些操作的状态并确定对表的影响。</span><span class="sxs-lookup"><span data-stu-id="53b0c-142">You can use **GetStatus** in conjunction with three other **IMAPITable** methods to monitor the status of those operations and determine the effect on the table.</span></span> <span data-ttu-id="53b0c-143">在进行以下**IMAPITable**调用之一后调用**GetStatus** :</span><span class="sxs-lookup"><span data-stu-id="53b0c-143">Call **GetStatus** after making one of the following **IMAPITable** calls:</span></span> 
  
- <span data-ttu-id="53b0c-144">[IMAPITable:: Restrict](imapitable-restrict.md)设置限制。</span><span class="sxs-lookup"><span data-stu-id="53b0c-144">[IMAPITable::Restrict](imapitable-restrict.md) to set a restriction.</span></span> 
    
- <span data-ttu-id="53b0c-145">[IMAPITable:: SortTable](imapitable-sorttable.md)以建立排序顺序。</span><span class="sxs-lookup"><span data-stu-id="53b0c-145">[IMAPITable::SortTable](imapitable-sorttable.md) to establish a sort order.</span></span> 
    
- <span data-ttu-id="53b0c-146">[IMAPITable:: SetColumns](imapitable-setcolumns.md)定义列集。</span><span class="sxs-lookup"><span data-stu-id="53b0c-146">[IMAPITable::SetColumns](imapitable-setcolumns.md) to define a column set.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="53b0c-147">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="53b0c-147">MFCMAPI reference</span></span>

<span data-ttu-id="53b0c-148">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="53b0c-148">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="53b0c-149">**文件**</span><span class="sxs-lookup"><span data-stu-id="53b0c-149">**File**</span></span>|<span data-ttu-id="53b0c-150">**函数**</span><span class="sxs-lookup"><span data-stu-id="53b0c-150">**Function**</span></span>|<span data-ttu-id="53b0c-151">**备注**</span><span class="sxs-lookup"><span data-stu-id="53b0c-151">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="53b0c-152">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="53b0c-152">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="53b0c-153">CContentsTableListCtrl:: GetStatus</span><span class="sxs-lookup"><span data-stu-id="53b0c-153">CContentsTableListCtrl::GetStatus</span></span>  <br/> |<span data-ttu-id="53b0c-154">MFCMAPI 使用**IMAPITable:: GetStatus**方法报告表的状态。</span><span class="sxs-lookup"><span data-stu-id="53b0c-154">MFCMAPI uses the **IMAPITable::GetStatus** method to report the status of a table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="53b0c-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53b0c-155">See also</span></span>



[<span data-ttu-id="53b0c-156">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="53b0c-156">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
  
[<span data-ttu-id="53b0c-157">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="53b0c-157">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="53b0c-158">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="53b0c-158">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="53b0c-159">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="53b0c-159">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="53b0c-160">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="53b0c-160">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

