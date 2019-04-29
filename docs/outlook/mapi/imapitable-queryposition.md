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
# <a name="imapitablequeryposition"></a><span data-ttu-id="e1e3a-103">IMAPITable::QueryPosition</span><span class="sxs-lookup"><span data-stu-id="e1e3a-103">IMAPITable::QueryPosition</span></span>

  
  
<span data-ttu-id="e1e3a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e1e3a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e1e3a-105">根据分数值检索游标的当前表行位置。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-105">Retrieves the current table row position of the cursor, based on a fractional value.</span></span>
  
```cpp
HRESULT QueryPosition(
ULONG FAR * lpulRow,
ULONG FAR * lpulNumerator,
ULONG FAR * lpulDenominator
);
```

## <a name="parameters"></a><span data-ttu-id="e1e3a-106">参数</span><span class="sxs-lookup"><span data-stu-id="e1e3a-106">Parameters</span></span>

 <span data-ttu-id="e1e3a-107">_lpulRow_</span><span class="sxs-lookup"><span data-stu-id="e1e3a-107">_lpulRow_</span></span>
  
> <span data-ttu-id="e1e3a-108">排除指向当前行的编号的指针。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-108">[out] Pointer to the number of the current row.</span></span> <span data-ttu-id="e1e3a-109">行号是从零开始的;表格中的第一行为零。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-109">The row number is zero-based; the first row in the table is zero.</span></span> 
    
 <span data-ttu-id="e1e3a-110">_lpulNumerator_</span><span class="sxs-lookup"><span data-stu-id="e1e3a-110">_lpulNumerator_</span></span>
  
> <span data-ttu-id="e1e3a-111">排除指向标识表位置的分数的分子的指针。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-111">[out] Pointer to the numerator for the fraction identifying the table position.</span></span>
    
 <span data-ttu-id="e1e3a-112">_lpulDenominator_</span><span class="sxs-lookup"><span data-stu-id="e1e3a-112">_lpulDenominator_</span></span>
  
> <span data-ttu-id="e1e3a-113">排除指向标识表格位置的分数的分母的指针。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-113">[out] Pointer to the denominator for the fraction identifying the table position.</span></span> <span data-ttu-id="e1e3a-114">_lpulDenominator_参数不能为零。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-114">The  _lpulDenominator_ parameter cannot be zero.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e1e3a-115">返回值</span><span class="sxs-lookup"><span data-stu-id="e1e3a-115">Return value</span></span>

<span data-ttu-id="e1e3a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1e3a-116">S_OK</span></span> 
  
> <span data-ttu-id="e1e3a-117">该方法在_lpulRow_、 _lpulNumerator_和_lpulDenominator_中返回了有效值。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-117">The method returned valid values in  _lpulRow_,  _lpulNumerator_, and  _lpulDenominator_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e1e3a-118">说明</span><span class="sxs-lookup"><span data-stu-id="e1e3a-118">Remarks</span></span>

<span data-ttu-id="e1e3a-119">**IMAPITable:: QueryPosition**方法确定当前行位置, 并同时返回当前行的编号和表示其在表末尾的相对位置的小数值。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-119">The **IMAPITable::QueryPosition** method determines the current row position and returns both the number of the current row and a fractional value indicating its relative position to the end of the table.</span></span> <span data-ttu-id="e1e3a-120">MAPI 将当前行定义为要读取的下一行。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-120">MAPI defines the current row as the next row to be read.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="e1e3a-121">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="e1e3a-121">Notes to implementers</span></span>

<span data-ttu-id="e1e3a-122">您无需为_lpulDenominator_参数返回 table 中的确切行数;它可以是一个近似值。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-122">You do not need to return the exact number of rows in the table for the  _lpulDenominator_ parameter; it can be an approximation.</span></span> 
  
<span data-ttu-id="e1e3a-123">如果无法确定当前行, 则在_lpulRow_中返回值0xffffffff。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-123">If you cannot determine the current row, return a value of 0xFFFFFFFF in  _lpulRow_.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="e1e3a-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e1e3a-124">Notes to callers</span></span>

<span data-ttu-id="e1e3a-125">您可以使用**QueryPosition**在滚动条中定位滚动框。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-125">You can use **QueryPosition** to position a scroll box in a scroll bar.</span></span> <span data-ttu-id="e1e3a-126">例如, 在包含100行的表中, 如果**QueryPosition**在_lpulNumerator_参数中返回值 75, 100 在_lpulDenominator_参数中, 在_lpulRow_参数中为 75, 则可以将滚动框3/4 定位滚动条上的方式。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-126">For example, in a table containing 100 rows, if **QueryPosition** returns a value of 75 in the  _lpulNumerator_ parameter, 100 in the  _lpulDenominator_ parameter, and 75 in the  _lpulRow_ parameter, you can position the scroll box 3/4 of the way across the scroll bar.</span></span> 
  
<span data-ttu-id="e1e3a-127">不要依赖_lpulDenominator_中的值作为表中的行数。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-127">Do not rely on the value in  _lpulDenominator_ being the number of rows in the table.</span></span> <span data-ttu-id="e1e3a-128">**QueryPosition**不能始终识别游标所定位的确切行。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-128">**QueryPosition** cannot always identify the exact row that the cursor is positioned on.</span></span> 
  
<span data-ttu-id="e1e3a-129">对**QueryPosition**的调用可能会涉及大量内存, 尤其是对于大型分类的表。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-129">A call to **QueryPosition** might involve large amounts of memory, particularly for large categorized tables.</span></span> <span data-ttu-id="e1e3a-130">如果将_lpulRow_参数设置为 0xffffffff, 则**QueryPosition**需要过多的内存来确定当前行。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-130">If the  _lpulRow_ parameter is set to 0xFFFFFFFF, too much memory was required for **QueryPosition** to determine the current row.</span></span> <span data-ttu-id="e1e3a-131">调用[IMAPITable:: SeekRowApprox](imapitable-seekrowapprox.md)方法将表定位到由_lpulNumerator_和_lpulDenominator_参数标识的行。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-131">Call the [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) method to position the table to the row identified by the  _lpulNumerator_ and  _lpulDenominator_ parameters.</span></span> <span data-ttu-id="e1e3a-132">但是, 如果内存不是一个因素, 则不总是认为**SeekRowApprox**是与当前位置相同的行**QueryPosition**的当前位置建立的。</span><span class="sxs-lookup"><span data-stu-id="e1e3a-132">However, do not always expect **SeekRowApprox** to establish as the current position the same row **QueryPosition** would have if memory had not been a factor.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e1e3a-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1e3a-133">See also</span></span>



[<span data-ttu-id="e1e3a-134">IMAPITable::SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="e1e3a-134">IMAPITable::SeekRowApprox</span></span>](imapitable-seekrowapprox.md)
  
[<span data-ttu-id="e1e3a-135">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e1e3a-135">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

