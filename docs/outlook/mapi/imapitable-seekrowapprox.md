---
title: IMAPITableSeekRowApprox
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.SeekRowApprox
api_type:
- COM
ms.assetid: ce5e8c43-06af-4afc-9138-5cc51d8fc401
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e6803c54ddd60c1bcebbe7a139c2edf2e7f4449d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572083"
---
# <a name="imapitableseekrowapprox"></a><span data-ttu-id="e209d-103">IMAPITable::SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="e209d-103">IMAPITable::SeekRowApprox</span></span>

  
  
<span data-ttu-id="e209d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e209d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e209d-105">将光标移到表中大约小数位置。</span><span class="sxs-lookup"><span data-stu-id="e209d-105">Moves the cursor to an approximate fractional position in the table.</span></span> 
  
```cpp
HRESULT SeekRowApprox(
ULONG ulNumerator,
ULONG ulDenominator
);
```

## <a name="parameters"></a><span data-ttu-id="e209d-106">参数</span><span class="sxs-lookup"><span data-stu-id="e209d-106">Parameters</span></span>

 <span data-ttu-id="e209d-107">_ulNumerator_</span><span class="sxs-lookup"><span data-stu-id="e209d-107">_ulNumerator_</span></span>
  
> <span data-ttu-id="e209d-108">[in]指向分数表示表位置的分子指针。</span><span class="sxs-lookup"><span data-stu-id="e209d-108">[in] Pointer to the numerator of the fraction representing the table position.</span></span> <span data-ttu-id="e209d-109">如果_ulNumerator_参数为零，光标位于无论分母值表的开头。</span><span class="sxs-lookup"><span data-stu-id="e209d-109">If the  _ulNumerator_ parameter is zero, the cursor is positioned at the beginning of the table regardless of the denominator value.</span></span> <span data-ttu-id="e209d-110">如果_ulNumerator_等于_ulDenominator_参数，将光标定位后最后一个表格行。</span><span class="sxs-lookup"><span data-stu-id="e209d-110">If  _ulNumerator_ is equal to the  _ulDenominator_ parameter, the cursor is positioned after the last table row.</span></span> 
    
 <span data-ttu-id="e209d-111">_ulDenominator_</span><span class="sxs-lookup"><span data-stu-id="e209d-111">_ulDenominator_</span></span>
  
> <span data-ttu-id="e209d-112">[in]指向分母的小数部分表示表位置的指针。</span><span class="sxs-lookup"><span data-stu-id="e209d-112">[in] Pointer to the denominator of the fraction representing the table position.</span></span> <span data-ttu-id="e209d-113">_UlDenominator_参数不能为零。</span><span class="sxs-lookup"><span data-stu-id="e209d-113">The  _ulDenominator_ parameter cannot be zero.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e209d-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e209d-114">Return value</span></span>

<span data-ttu-id="e209d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e209d-115">S_OK</span></span> 
  
> <span data-ttu-id="e209d-116">Seek 操作已成功。</span><span class="sxs-lookup"><span data-stu-id="e209d-116">The seek operation was successful.</span></span>
    
<span data-ttu-id="e209d-117">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="e209d-117">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="e209d-118">另一个操作正在进行阻止寻求操作从起始行中。</span><span class="sxs-lookup"><span data-stu-id="e209d-118">Another operation is in progress that prevents the row seeking operation from starting.</span></span> <span data-ttu-id="e209d-119">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="e209d-119">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e209d-120">注解</span><span class="sxs-lookup"><span data-stu-id="e209d-120">Remarks</span></span>

<span data-ttu-id="e209d-121">对**IMAPITable::SeekRowApprox**方法的调用之后表中的光标位置是试探性地分数，且可能不可准确。</span><span class="sxs-lookup"><span data-stu-id="e209d-121">The cursor position in a table after a call to the **IMAPITable::SeekRowApprox** method is heuristically the fraction and might not be exact.</span></span> <span data-ttu-id="e209d-122">例如，特定提供程序可能实现二进制树中，在表视为出于性能原因树顶部的表的中点。</span><span class="sxs-lookup"><span data-stu-id="e209d-122">For example, certain providers might implement a table on top of a binary tree, treating the table's halfway point as the top of the tree for performance reasons.</span></span> <span data-ttu-id="e209d-123">如果不平衡树，然后使用的中间点可能不是表到完全一半。</span><span class="sxs-lookup"><span data-stu-id="e209d-123">If the tree is not balanced, then the halfway point used might not be exactly halfway through the table.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="e209d-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e209d-124">Notes to callers</span></span>

<span data-ttu-id="e209d-125">调用**SeekRowApprox**滚动栏实现提供数据。</span><span class="sxs-lookup"><span data-stu-id="e209d-125">Call **SeekRowApprox** to provide the data for a scroll bar implementation.</span></span> <span data-ttu-id="e209d-126">例如，如果用户定位滚动框 2/3 上向下滚动条，您可以通过调用**SeekRowApprox**和传递中等效的小数值使用_ulNumerator_和_ulDenominator_建模该操作。</span><span class="sxs-lookup"><span data-stu-id="e209d-126">For example, if the user positions the scroll box 2/3 down the scroll bar, you can model that action by calling **SeekRowApprox** and passing in an equivalent fractional value using  _ulNumerator_ and  _ulDenominator_.</span></span> <span data-ttu-id="e209d-127">**SeekRowApprox**搜索始终是绝对从表的开头。</span><span class="sxs-lookup"><span data-stu-id="e209d-127">The **SeekRowApprox** search is always absolute from the beginning of the table.</span></span> <span data-ttu-id="e209d-128">若要移动到的表的末尾， _ulNumerator_和_ulDenominator_中的值必须相同。</span><span class="sxs-lookup"><span data-stu-id="e209d-128">To move to the end of the table, the values in  _ulNumerator_ and  _ulDenominator_ must be the same.</span></span> 
  
<span data-ttu-id="e209d-129">使用适合任何编号方案。</span><span class="sxs-lookup"><span data-stu-id="e209d-129">Use whatever number scheme is appropriate.</span></span> <span data-ttu-id="e209d-130">即寻求到表到一半的位置，您可以指定 1/2、 10/20 或 50/100。</span><span class="sxs-lookup"><span data-stu-id="e209d-130">That is, to seek to a position halfway through the table, you can specify 1/2, 10/20, or 50/100.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e209d-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e209d-131">See also</span></span>



[<span data-ttu-id="e209d-132">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e209d-132">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

