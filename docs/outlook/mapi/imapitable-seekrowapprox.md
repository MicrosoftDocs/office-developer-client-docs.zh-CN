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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bbb79097d03a8ea09cb4aff374231ee780e15395
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412147"
---
# <a name="imapitableseekrowapprox"></a><span data-ttu-id="59e83-103">IMAPITable::SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="59e83-103">IMAPITable::SeekRowApprox</span></span>

  
  
<span data-ttu-id="59e83-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="59e83-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="59e83-105">将光标移到表格中的近似小数位置。</span><span class="sxs-lookup"><span data-stu-id="59e83-105">Moves the cursor to an approximate fractional position in the table.</span></span> 
  
```cpp
HRESULT SeekRowApprox(
ULONG ulNumerator,
ULONG ulDenominator
);
```

## <a name="parameters"></a><span data-ttu-id="59e83-106">参数</span><span class="sxs-lookup"><span data-stu-id="59e83-106">Parameters</span></span>

 <span data-ttu-id="59e83-107">_ulNumerator_</span><span class="sxs-lookup"><span data-stu-id="59e83-107">_ulNumerator_</span></span>
  
> <span data-ttu-id="59e83-108">[in]指向表示表格位置的小数的分子的指针。</span><span class="sxs-lookup"><span data-stu-id="59e83-108">[in] Pointer to the numerator of the fraction representing the table position.</span></span> <span data-ttu-id="59e83-109">如果  _ulNumerator_ 参数为零，则游标将位于表的开头，而不考虑分母值。</span><span class="sxs-lookup"><span data-stu-id="59e83-109">If the  _ulNumerator_ parameter is zero, the cursor is positioned at the beginning of the table regardless of the denominator value.</span></span> <span data-ttu-id="59e83-110">如果  _ulNumerator_ 等于  _ulDenominator_ 参数，则光标位于最后一个表格行之后。</span><span class="sxs-lookup"><span data-stu-id="59e83-110">If  _ulNumerator_ is equal to the  _ulDenominator_ parameter, the cursor is positioned after the last table row.</span></span> 
    
 <span data-ttu-id="59e83-111">_ulDenominator_</span><span class="sxs-lookup"><span data-stu-id="59e83-111">_ulDenominator_</span></span>
  
> <span data-ttu-id="59e83-112">[in]指向表示表格位置的小数的分母的指针。</span><span class="sxs-lookup"><span data-stu-id="59e83-112">[in] Pointer to the denominator of the fraction representing the table position.</span></span> <span data-ttu-id="59e83-113">_ulDenominator_ 参数不能为零。</span><span class="sxs-lookup"><span data-stu-id="59e83-113">The  _ulDenominator_ parameter cannot be zero.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="59e83-114">返回值</span><span class="sxs-lookup"><span data-stu-id="59e83-114">Return value</span></span>

<span data-ttu-id="59e83-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="59e83-115">S_OK</span></span> 
  
> <span data-ttu-id="59e83-116">查找操作成功。</span><span class="sxs-lookup"><span data-stu-id="59e83-116">The seek operation was successful.</span></span>
    
<span data-ttu-id="59e83-117">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="59e83-117">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="59e83-118">正在进行另一个操作，该操作阻止行的寻找操作启动。</span><span class="sxs-lookup"><span data-stu-id="59e83-118">Another operation is in progress that prevents the row seeking operation from starting.</span></span> <span data-ttu-id="59e83-119">应允许完成或停止进行中的操作。</span><span class="sxs-lookup"><span data-stu-id="59e83-119">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="59e83-120">备注</span><span class="sxs-lookup"><span data-stu-id="59e83-120">Remarks</span></span>

<span data-ttu-id="59e83-121">调用 **IMAPITable：：SeekRowApprox** 方法后表格中的光标位置是启发式分数，可能并不精确。</span><span class="sxs-lookup"><span data-stu-id="59e83-121">The cursor position in a table after a call to the **IMAPITable::SeekRowApprox** method is heuristically the fraction and might not be exact.</span></span> <span data-ttu-id="59e83-122">例如，某些提供程序可能在二进制树顶部实现一个表，出于性能原因，将表的中点视为树的顶部。</span><span class="sxs-lookup"><span data-stu-id="59e83-122">For example, certain providers might implement a table on top of a binary tree, treating the table's halfway point as the top of the tree for performance reasons.</span></span> <span data-ttu-id="59e83-123">如果树未平衡，则使用的中点可能并非正好在表格的一半。</span><span class="sxs-lookup"><span data-stu-id="59e83-123">If the tree is not balanced, then the halfway point used might not be exactly halfway through the table.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="59e83-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="59e83-124">Notes to callers</span></span>

<span data-ttu-id="59e83-125">调用 **SeekRowApprox** 以提供滚动条实现的数据。</span><span class="sxs-lookup"><span data-stu-id="59e83-125">Call **SeekRowApprox** to provide the data for a scroll bar implementation.</span></span> <span data-ttu-id="59e83-126">例如，如果用户将滚动框定位在滚动条的 2/3 下，则可以通过调用 **SeekRowApprox，** 然后使用  _ulNumerator_ 和  _ulDenominator_ 传递等效的小数值来为该操作建模。</span><span class="sxs-lookup"><span data-stu-id="59e83-126">For example, if the user positions the scroll box 2/3 down the scroll bar, you can model that action by calling **SeekRowApprox** and passing in an equivalent fractional value using  _ulNumerator_ and  _ulDenominator_.</span></span> <span data-ttu-id="59e83-127">**SeekRowApprox** 搜索始终从表开头为绝对搜索。</span><span class="sxs-lookup"><span data-stu-id="59e83-127">The **SeekRowApprox** search is always absolute from the beginning of the table.</span></span> <span data-ttu-id="59e83-128">若要移到表末尾  _，ulNumerator_ 和  _ulDenominator_ 中的值必须相同。</span><span class="sxs-lookup"><span data-stu-id="59e83-128">To move to the end of the table, the values in  _ulNumerator_ and  _ulDenominator_ must be the same.</span></span> 
  
<span data-ttu-id="59e83-129">使用合适的数字方案。</span><span class="sxs-lookup"><span data-stu-id="59e83-129">Use whatever number scheme is appropriate.</span></span> <span data-ttu-id="59e83-130">也就是说，若要在表的一半位置进行查找，可以指定 1/2、10/20 或 50/100。</span><span class="sxs-lookup"><span data-stu-id="59e83-130">That is, to seek to a position halfway through the table, you can specify 1/2, 10/20, or 50/100.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="59e83-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59e83-131">See also</span></span>



[<span data-ttu-id="59e83-132">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="59e83-132">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

