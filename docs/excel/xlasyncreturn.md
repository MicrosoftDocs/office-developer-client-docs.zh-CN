---
title: xlAsyncReturn
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 159bc9bf-8dd5-4cd2-8384-474c74a3f112
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 32d5075af34cda9753c5d082bd4ab00afab1ecff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310246"
---
# <a name="xlasyncreturn"></a><span data-ttu-id="860e7-103">xlAsyncReturn</span><span class="sxs-lookup"><span data-stu-id="860e7-103">xlAsyncReturn</span></span>

<span data-ttu-id="860e7-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="860e7-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="860e7-105">用于返回异步用户定义函数 (UDF) 的结果。</span><span class="sxs-lookup"><span data-stu-id="860e7-105">Used to return the result of an asynchronous user-defined function (UDF).</span></span>
  
```cpp
Excel12(xlAsyncReturn, LPXLOPER12 pxRes, 2, LPXLOPER12 pxAsyncHandle, LPXLOPER12 pxFunctionResult);
```

## <a name="parameters"></a><span data-ttu-id="860e7-106">参数</span><span class="sxs-lookup"><span data-stu-id="860e7-106">Parameters</span></span>

<span data-ttu-id="860e7-107">_pxAsyncHandle_(**xltypeBigData**)</span><span class="sxs-lookup"><span data-stu-id="860e7-107">_pxAsyncHandle_ (**xltypeBigData**)</span></span>
  
<span data-ttu-id="860e7-108">将返回其结果的 UDF 的异步句柄。</span><span class="sxs-lookup"><span data-stu-id="860e7-108">The asynchronous handle of the UDF to which the result is returned.</span></span>
  
<span data-ttu-id="860e7-109">_pxFunctionResult_</span><span class="sxs-lookup"><span data-stu-id="860e7-109">_pxFunctionResult_</span></span>
  
<span data-ttu-id="860e7-110">UDF 的返回值。</span><span class="sxs-lookup"><span data-stu-id="860e7-110">The return value of the UDF.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="860e7-111">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="860e7-111">Property value/Return value</span></span>

<span data-ttu-id="860e7-112">如果成功,**则返回 TRUE** (**xltypeBool**)。</span><span class="sxs-lookup"><span data-stu-id="860e7-112">If successful, returns **TRUE** (**xltypeBool**).</span></span> <span data-ttu-id="860e7-113">如果不成功, 则返回**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="860e7-113">If unsuccessful, returns **FALSE**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="860e7-114">注解</span><span class="sxs-lookup"><span data-stu-id="860e7-114">Remarks</span></span>

<span data-ttu-id="860e7-115">**xlAsyncReturn**是 Excel 在重新计算期间允许对非计算线程执行的唯一回调。</span><span class="sxs-lookup"><span data-stu-id="860e7-115">**xlAsyncReturn** is the only callback Excel allows on non-calculation threads during recalculation.</span></span> <span data-ttu-id="860e7-116">异步 UDF 的异步部分不能执行除**xlAsyncReturn**以外的任何回调。</span><span class="sxs-lookup"><span data-stu-id="860e7-116">The asynchronous portion of an asynchronous UDF must not perform any callbacks other than **xlAsyncReturn**.</span></span> <span data-ttu-id="860e7-117">XLL 必须释放分配的内存以容纳返回值。</span><span class="sxs-lookup"><span data-stu-id="860e7-117">The XLL must free memory allocated to hold the return value.</span></span>
  
<span data-ttu-id="860e7-118">_pxAsyncHandle_和_pxFunctionResult_参数也可以是**xltypeMulti**类型, 用于在单个回调中返回句柄的数组和相应的值。</span><span class="sxs-lookup"><span data-stu-id="860e7-118">The _pxAsyncHandle_ and  _pxFunctionResult_ parameters can also be of type **xltypeMulti** when used to return an array of handles and corresponding values in a single callback.</span></span> <span data-ttu-id="860e7-119">使用单个回调时, 传递指向 XLOPER12 结构的 LPXLOPER12, 其中包含一个包含异步句柄和返回值的维度数组。</span><span class="sxs-lookup"><span data-stu-id="860e7-119">When using a single callback, pass an LPXLOPER12 that points to XLOPER12 structures that contain one dimensional arrays that contain the asynchronous handles and return values.</span></span> <span data-ttu-id="860e7-120">这些数组必须具有相同的顺序, Excel 才能正确匹配异步句柄与其对应的值。</span><span class="sxs-lookup"><span data-stu-id="860e7-120">These arrays must be in the same order for Excel to correctly match an asynchronous handle with its corresponding value.</span></span> 
  
<span data-ttu-id="860e7-121">下面的示例展示了如何使用**xlAsyncReturn**进行批处理调用。</span><span class="sxs-lookup"><span data-stu-id="860e7-121">The following example shows how you can make a batch call using **xlAsyncReturn**.</span></span>
  
```cpp
int batchSize = 10;
    LPXLOPER12 pHandles = new XLOPER12[batchSize];
    LPXLOPER12 pValues = new XLOPER12[batchSize];
    /*Add code to fill in LPXLOPER12 arrays (pHandles and pValues)
    with the XOPER12 structures that contain the asynchronous handles
    and values, in respective order*/
    //Create an XLOPER12 of type xltypeMulti, and fill the Handle array
    XLOPER12 handleArray;
    handleArray.xltype = xltypeMulti;
    handleArray.val.array.rows = 1;
    handleArray.val.array.columns = (COL)batchSize;
    handleArray.val.array.lparray = pHandles;
    
    //Create an XLOPER12 if type xltypeMulti, and fill the Values array
    XLOPER12 valueArray;
    valueArray.xltype = xltypeMulti;
    valueArray.val.array.rows = 1;
    valueArray.val.array.columns = (COL)batchSize;
    valueArray.val.array.lparray = pValues;
    //Make the callback with the return value
    int ret = Excel12(xlAsyncReturn, 0, 2, &amp;handleArray, &amp;valueArray);
    //Add code to free the allocated memory here (pHandles, pValues, valueArray, handleArray)
    return ret;

```

## <a name="see-also"></a><span data-ttu-id="860e7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="860e7-122">See also</span></span>

- [<span data-ttu-id="860e7-123">用户定义异步函数</span><span class="sxs-lookup"><span data-stu-id="860e7-123">Asynchronous User-Defined Functions</span></span>](asynchronous-user-defined-functions.md)

