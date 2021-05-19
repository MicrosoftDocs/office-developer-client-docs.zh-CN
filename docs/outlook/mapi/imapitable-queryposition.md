---
title: IMAPITableQueryPosition
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.QueryPosition
api_type:
- COM
ms.assetid: 510b2e21-ba27-47dd-87cb-2a549e31fa28
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2e44d824bbb5cc96c51d7ca91eb639001bc52a71
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415661"
---
# <a name="imapitablequeryposition"></a><span data-ttu-id="c19d3-103">IMAPITable::QueryPosition</span><span class="sxs-lookup"><span data-stu-id="c19d3-103">IMAPITable::QueryPosition</span></span>

  
  
<span data-ttu-id="c19d3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c19d3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c19d3-105">基于小数值检索游标的当前表格行位置。</span><span class="sxs-lookup"><span data-stu-id="c19d3-105">Retrieves the current table row position of the cursor, based on a fractional value.</span></span>
  
```cpp
HRESULT QueryPosition(
ULONG FAR * lpulRow,
ULONG FAR * lpulNumerator,
ULONG FAR * lpulDenominator
);
```

## <a name="parameters"></a><span data-ttu-id="c19d3-106">参数</span><span class="sxs-lookup"><span data-stu-id="c19d3-106">Parameters</span></span>

 <span data-ttu-id="c19d3-107">_lpulRow_</span><span class="sxs-lookup"><span data-stu-id="c19d3-107">_lpulRow_</span></span>
  
> <span data-ttu-id="c19d3-108">[out]指向当前行的编号的指针。</span><span class="sxs-lookup"><span data-stu-id="c19d3-108">[out] Pointer to the number of the current row.</span></span> <span data-ttu-id="c19d3-109">行号从零开始;表中的第一行为零。</span><span class="sxs-lookup"><span data-stu-id="c19d3-109">The row number is zero-based; the first row in the table is zero.</span></span> 
    
 <span data-ttu-id="c19d3-110">_lpulNumerator_</span><span class="sxs-lookup"><span data-stu-id="c19d3-110">_lpulNumerator_</span></span>
  
> <span data-ttu-id="c19d3-111">[out]指向确定表格位置的小数的分子的指针。</span><span class="sxs-lookup"><span data-stu-id="c19d3-111">[out] Pointer to the numerator for the fraction identifying the table position.</span></span>
    
 <span data-ttu-id="c19d3-112">_lpulDenominator_</span><span class="sxs-lookup"><span data-stu-id="c19d3-112">_lpulDenominator_</span></span>
  
> <span data-ttu-id="c19d3-113">[out]指向用于标识表格位置的小数的分母的指针。</span><span class="sxs-lookup"><span data-stu-id="c19d3-113">[out] Pointer to the denominator for the fraction identifying the table position.</span></span> <span data-ttu-id="c19d3-114">_lpulDenominator_ 参数不能为零。</span><span class="sxs-lookup"><span data-stu-id="c19d3-114">The  _lpulDenominator_ parameter cannot be zero.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c19d3-115">返回值</span><span class="sxs-lookup"><span data-stu-id="c19d3-115">Return value</span></span>

<span data-ttu-id="c19d3-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="c19d3-116">S_OK</span></span> 
  
> <span data-ttu-id="c19d3-117">方法在  _lpulRow_  _、lpulNumerator_ 和  _lpulDenominator 中返回有效值_。</span><span class="sxs-lookup"><span data-stu-id="c19d3-117">The method returned valid values in  _lpulRow_,  _lpulNumerator_, and  _lpulDenominator_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c19d3-118">备注</span><span class="sxs-lookup"><span data-stu-id="c19d3-118">Remarks</span></span>

<span data-ttu-id="c19d3-119">**IMAPITable：：QueryPosition** 方法确定当前行的位置，并返回当前行的编号和指示其相对于表格末尾位置的小数值。</span><span class="sxs-lookup"><span data-stu-id="c19d3-119">The **IMAPITable::QueryPosition** method determines the current row position and returns both the number of the current row and a fractional value indicating its relative position to the end of the table.</span></span> <span data-ttu-id="c19d3-120">MAPI 将当前行定义为要读取的下一行。</span><span class="sxs-lookup"><span data-stu-id="c19d3-120">MAPI defines the current row as the next row to be read.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="c19d3-121">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="c19d3-121">Notes to implementers</span></span>

<span data-ttu-id="c19d3-122">无需为  _lpulDenominator_ 参数返回表中的准确行数;它可以是近似值。</span><span class="sxs-lookup"><span data-stu-id="c19d3-122">You do not need to return the exact number of rows in the table for the  _lpulDenominator_ parameter; it can be an approximation.</span></span> 
  
<span data-ttu-id="c19d3-123">如果无法确定当前行，则返回 _lpulRow 0xFFFFFFFF值。_</span><span class="sxs-lookup"><span data-stu-id="c19d3-123">If you cannot determine the current row, return a value of 0xFFFFFFFF in  _lpulRow_.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="c19d3-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c19d3-124">Notes to callers</span></span>

<span data-ttu-id="c19d3-125">可以使用 **QueryPosition** 在滚动条中定位滚动框。</span><span class="sxs-lookup"><span data-stu-id="c19d3-125">You can use **QueryPosition** to position a scroll box in a scroll bar.</span></span> <span data-ttu-id="c19d3-126">例如，在包含 100 行的表中，如果 **QueryPosition** 在  _lpulNumerator_ 参数中返回值 75，  _在 lpulDenominator_ 参数中返回 100，在  _lpulRow_ 参数中返回 75，可以在滚动条中将滚动框定位 3/4。</span><span class="sxs-lookup"><span data-stu-id="c19d3-126">For example, in a table containing 100 rows, if **QueryPosition** returns a value of 75 in the  _lpulNumerator_ parameter, 100 in the  _lpulDenominator_ parameter, and 75 in the  _lpulRow_ parameter, you can position the scroll box 3/4 of the way across the scroll bar.</span></span> 
  
<span data-ttu-id="c19d3-127">不要依赖于  _lpulDenominator_ 中的值是表中的行数。</span><span class="sxs-lookup"><span data-stu-id="c19d3-127">Do not rely on the value in  _lpulDenominator_ being the number of rows in the table.</span></span> <span data-ttu-id="c19d3-128">**QueryPosition** 不能始终标识光标定位到的确切行。</span><span class="sxs-lookup"><span data-stu-id="c19d3-128">**QueryPosition** cannot always identify the exact row that the cursor is positioned on.</span></span> 
  
<span data-ttu-id="c19d3-129">对 **QueryPosition 的** 调用可能涉及大量内存，特别是对于大型分类表。</span><span class="sxs-lookup"><span data-stu-id="c19d3-129">A call to **QueryPosition** might involve large amounts of memory, particularly for large categorized tables.</span></span> <span data-ttu-id="c19d3-130">如果  _lpulRow_ 参数设置为 0xFFFFFFFF，则 **QueryPosition** 确定当前行所需的内存过多。</span><span class="sxs-lookup"><span data-stu-id="c19d3-130">If the  _lpulRow_ parameter is set to 0xFFFFFFFF, too much memory was required for **QueryPosition** to determine the current row.</span></span> <span data-ttu-id="c19d3-131">调用 [IMAPITable：：SeekRowApprox](imapitable-seekrowapprox.md) 方法将表定位到  _由 lpulNumerator_ 和  _lpulDenominator_ 参数标识的行。</span><span class="sxs-lookup"><span data-stu-id="c19d3-131">Call the [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) method to position the table to the row identified by the  _lpulNumerator_ and  _lpulDenominator_ parameters.</span></span> <span data-ttu-id="c19d3-132">但是，不要始终预期 **SeekRowApprox** 将同一行 **QueryPosition（** 如果内存不是一个因素）建立为当前位置。</span><span class="sxs-lookup"><span data-stu-id="c19d3-132">However, do not always expect **SeekRowApprox** to establish as the current position the same row **QueryPosition** would have if memory had not been a factor.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c19d3-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c19d3-133">See also</span></span>



[<span data-ttu-id="c19d3-134">IMAPITable::SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="c19d3-134">IMAPITable::SeekRowApprox</span></span>](imapitable-seekrowapprox.md)
  
[<span data-ttu-id="c19d3-135">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c19d3-135">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

