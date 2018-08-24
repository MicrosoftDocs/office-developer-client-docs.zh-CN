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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 502bc24ece37c91e2cac23cf8486df96d5a71377
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584336"
---
# <a name="imapitablequeryposition"></a><span data-ttu-id="efadd-103">IMAPITable::QueryPosition</span><span class="sxs-lookup"><span data-stu-id="efadd-103">IMAPITable::QueryPosition</span></span>

  
  
<span data-ttu-id="efadd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="efadd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="efadd-105">检索当前表行位置的指针，根据分数的值。</span><span class="sxs-lookup"><span data-stu-id="efadd-105">Retrieves the current table row position of the cursor, based on a fractional value.</span></span>
  
```cpp
HRESULT QueryPosition(
ULONG FAR * lpulRow,
ULONG FAR * lpulNumerator,
ULONG FAR * lpulDenominator
);
```

## <a name="parameters"></a><span data-ttu-id="efadd-106">参数</span><span class="sxs-lookup"><span data-stu-id="efadd-106">Parameters</span></span>

 <span data-ttu-id="efadd-107">_lpulRow_</span><span class="sxs-lookup"><span data-stu-id="efadd-107">_lpulRow_</span></span>
  
> <span data-ttu-id="efadd-108">[输出]到当前行数的指针。</span><span class="sxs-lookup"><span data-stu-id="efadd-108">[out] Pointer to the number of the current row.</span></span> <span data-ttu-id="efadd-109">行号是从零开始;表中的第一行为零。</span><span class="sxs-lookup"><span data-stu-id="efadd-109">The row number is zero-based; the first row in the table is zero.</span></span> 
    
 <span data-ttu-id="efadd-110">_lpulNumerator_</span><span class="sxs-lookup"><span data-stu-id="efadd-110">_lpulNumerator_</span></span>
  
> <span data-ttu-id="efadd-111">[输出]指向分子分数标识表位置的指针。</span><span class="sxs-lookup"><span data-stu-id="efadd-111">[out] Pointer to the numerator for the fraction identifying the table position.</span></span>
    
 <span data-ttu-id="efadd-112">_lpulDenominator_</span><span class="sxs-lookup"><span data-stu-id="efadd-112">_lpulDenominator_</span></span>
  
> <span data-ttu-id="efadd-113">[输出]指向分母分数标识表位置的指针。</span><span class="sxs-lookup"><span data-stu-id="efadd-113">[out] Pointer to the denominator for the fraction identifying the table position.</span></span> <span data-ttu-id="efadd-114">_LpulDenominator_参数不能为零。</span><span class="sxs-lookup"><span data-stu-id="efadd-114">The  _lpulDenominator_ parameter cannot be zero.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="efadd-115">返回值</span><span class="sxs-lookup"><span data-stu-id="efadd-115">Return value</span></span>

<span data-ttu-id="efadd-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="efadd-116">S_OK</span></span> 
  
> <span data-ttu-id="efadd-117">该方法返回_lpulRow_、 _lpulNumerator_和_lpulDenominator_中有效的值。</span><span class="sxs-lookup"><span data-stu-id="efadd-117">The method returned valid values in  _lpulRow_,  _lpulNumerator_, and  _lpulDenominator_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="efadd-118">注解</span><span class="sxs-lookup"><span data-stu-id="efadd-118">Remarks</span></span>

<span data-ttu-id="efadd-119">**IMAPITable::QueryPosition**方法确定当前行位置，并返回这两个当前行和分数的值，该值指示它表末尾的相对位置的数量。</span><span class="sxs-lookup"><span data-stu-id="efadd-119">The **IMAPITable::QueryPosition** method determines the current row position and returns both the number of the current row and a fractional value indicating its relative position to the end of the table.</span></span> <span data-ttu-id="efadd-120">MAPI 将当前行定义为要读取的下一行。</span><span class="sxs-lookup"><span data-stu-id="efadd-120">MAPI defines the current row as the next row to be read.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="efadd-121">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="efadd-121">Notes to implementers</span></span>

<span data-ttu-id="efadd-122">不需要返回_lpulDenominator_参数; 表中的确切的行数它可以是近似值。</span><span class="sxs-lookup"><span data-stu-id="efadd-122">You do not need to return the exact number of rows in the table for the  _lpulDenominator_ parameter; it can be an approximation.</span></span> 
  
<span data-ttu-id="efadd-123">如果无法确定当前行，请在_lpulRow_返回 0xFFFFFFFF 值。</span><span class="sxs-lookup"><span data-stu-id="efadd-123">If you cannot determine the current row, return a value of 0xFFFFFFFF in  _lpulRow_.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="efadd-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="efadd-124">Notes to callers</span></span>

<span data-ttu-id="efadd-125">您可以使用**QueryPosition**定位滚动条中的滚动框。</span><span class="sxs-lookup"><span data-stu-id="efadd-125">You can use **QueryPosition** to position a scroll box in a scroll bar.</span></span> <span data-ttu-id="efadd-126">例如，在表包含 100 的行，如果**QueryPosition** _lpulNumerator_参数， _lpulDenominator_参数中的 100 和_lpulRow_参数中的 75 中返回的值为 75 可以定位滚动框的 3/4跨滚动条方式。</span><span class="sxs-lookup"><span data-stu-id="efadd-126">For example, in a table containing 100 rows, if **QueryPosition** returns a value of 75 in the  _lpulNumerator_ parameter, 100 in the  _lpulDenominator_ parameter, and 75 in the  _lpulRow_ parameter, you can position the scroll box 3/4 of the way across the scroll bar.</span></span> 
  
<span data-ttu-id="efadd-127">不依赖中_lpulDenominator_正在的表中的行数的值。</span><span class="sxs-lookup"><span data-stu-id="efadd-127">Do not rely on the value in  _lpulDenominator_ being the number of rows in the table.</span></span> <span data-ttu-id="efadd-128">**QueryPosition**始终不能确定将光标定位的确切行。</span><span class="sxs-lookup"><span data-stu-id="efadd-128">**QueryPosition** cannot always identify the exact row that the cursor is positioned on.</span></span> 
  
<span data-ttu-id="efadd-129">调用**QueryPosition**可能涉及大量内存，特别是对于大分类表。</span><span class="sxs-lookup"><span data-stu-id="efadd-129">A call to **QueryPosition** might involve large amounts of memory, particularly for large categorized tables.</span></span> <span data-ttu-id="efadd-130">如果_lpulRow_参数设置为 0xFFFFFFFF，太多的内存，需要**QueryPosition**以确定当前行。</span><span class="sxs-lookup"><span data-stu-id="efadd-130">If the  _lpulRow_ parameter is set to 0xFFFFFFFF, too much memory was required for **QueryPosition** to determine the current row.</span></span> <span data-ttu-id="efadd-131">调用[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)方法来定位到由_lpulNumerator_和_lpulDenominator_参数标识的行的表。</span><span class="sxs-lookup"><span data-stu-id="efadd-131">Call the [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) method to position the table to the row identified by the  _lpulNumerator_ and  _lpulDenominator_ parameters.</span></span> <span data-ttu-id="efadd-132">但是，不始终希望**SeekRowApprox** **QueryPosition**如果内存不已经因素将具有同一行建立与当前的位置。</span><span class="sxs-lookup"><span data-stu-id="efadd-132">However, do not always expect **SeekRowApprox** to establish as the current position the same row **QueryPosition** would have if memory had not been a factor.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="efadd-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efadd-133">See also</span></span>



[<span data-ttu-id="efadd-134">IMAPITable::SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="efadd-134">IMAPITable::SeekRowApprox</span></span>](imapitable-seekrowapprox.md)
  
[<span data-ttu-id="efadd-135">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="efadd-135">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

