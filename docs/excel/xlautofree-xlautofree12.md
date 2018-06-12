---
title: xlAutoFree/xlAutoFree12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoFree
keywords:
- xlautofree 函数 [excel 2007]
localization_priority: Normal
ms.assetid: f73d292c-d6d8-4be5-89c0-bef15db236d6
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: a2d2b8e60b484ba8156acc80d543493e3ec9c564
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773836"
---
# <a name="xlautofreexlautofree12"></a><span data-ttu-id="e5596-104">xlAutoFree/xlAutoFree12</span><span class="sxs-lookup"><span data-stu-id="e5596-104">xlAutoFree/xlAutoFree12</span></span>

 <span data-ttu-id="e5596-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e5596-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="e5596-106">Microsoft Excel XLL 工作表函数返回**XLOPER**后立即调用/ **XLOPER12**向其设置标志告知 XLL 仍需要释放的内存。</span><span class="sxs-lookup"><span data-stu-id="e5596-106">Called by Microsoft Excel just after an XLL worksheet function returns an **XLOPER**/ **XLOPER12** to it with a flag set that tells it there is memory that the XLL still needs to release.</span></span> <span data-ttu-id="e5596-107">这样，XLL 返回动态分配数组、 字符串和不内存泄漏工作表的外部引用。</span><span class="sxs-lookup"><span data-stu-id="e5596-107">This enables the XLL to return dynamically allocated arrays, strings, and external references to the worksheet without memory leaks.</span></span> <span data-ttu-id="e5596-108">有关详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="e5596-108">For more information, see [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
<span data-ttu-id="e5596-109">从 Excel 2007 开始， **xlAutoFree12**函数和**XLOPER12**数据类型的支持。</span><span class="sxs-lookup"><span data-stu-id="e5596-109">Starting in Excel 2007, the **xlAutoFree12** function and the **XLOPER12** data type are supported.</span></span> 
  
<span data-ttu-id="e5596-110">Excel 不需要 XLL 实施和导出其中任一函数。</span><span class="sxs-lookup"><span data-stu-id="e5596-110">Excel does not require an XLL to implement and export either of these functions.</span></span> <span data-ttu-id="e5596-111">但是，您必须完成如果 XLL 函数返回 XLOPER 或 XLOPER12 已动态分配的或包含指向动态分配的内存。</span><span class="sxs-lookup"><span data-stu-id="e5596-111">However, you must do so if your XLL functions return an XLOPER or XLOPER12 that has been dynamically allocated or that contains pointers to dynamically allocated memory.</span></span> <span data-ttu-id="e5596-112">确保您选择如何管理这些类型的内存整个您 XLL 和如何实现**xlAutoFree**和**xlAutoFree12**保持一致。</span><span class="sxs-lookup"><span data-stu-id="e5596-112">Ensure that your choice of how to manage memory for these types is consistent throughout your XLL and with how you implemented **xlAutoFree** and **xlAutoFree12**.</span></span>
  
<span data-ttu-id="e5596-113">内部**xlAutoFree**/ **xlAutoFree12**函数，导入 Excel 回调被禁用，有一个例外： **xlFree**可调用它以释放 Excel 分配内存。</span><span class="sxs-lookup"><span data-stu-id="e5596-113">Inside the **xlAutoFree**/ **xlAutoFree12** function, callbacks into Excel are disabled, with one exception: **xlFree** can be called to free Excel-allocated memory.</span></span> 
  
```cs
void WINAPI xlAutoFree(LPXLOPER pxFree);
void WINAPI xlAutoFree12(LPXLOPER12 pxFree);
```

## <a name="parameters"></a><span data-ttu-id="e5596-114">参数</span><span class="sxs-lookup"><span data-stu-id="e5596-114">Parameters</span></span>

 <span data-ttu-id="e5596-115">_pxFree_(**对于 xlAutoFree LPXLOPER**)</span><span class="sxs-lookup"><span data-stu-id="e5596-115">_pxFree_ (**LPXLOPER in the case of xlAutoFree**)</span></span>
  
 <span data-ttu-id="e5596-116">_pxFree_(**对于 xlAutoFree12 LPXLOPER12**)</span><span class="sxs-lookup"><span data-stu-id="e5596-116">_pxFree_ (**LPXLOPER12 in the case of xlAutoFree12**)</span></span>
  
<span data-ttu-id="e5596-117">一个指向**XLOPER**或**XLOPER12**已被释放所需的内存。</span><span class="sxs-lookup"><span data-stu-id="e5596-117">A pointer to the **XLOPER** or the **XLOPER12** that has memory that needs to be freed.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e5596-118">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="e5596-118">Property value/Return value</span></span>

<span data-ttu-id="e5596-119">此函数不会返回一个值，并应声明为返回无效。</span><span class="sxs-lookup"><span data-stu-id="e5596-119">This function does not return a value and should be declared as returning void.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e5596-120">备注</span><span class="sxs-lookup"><span data-stu-id="e5596-120">Remarks</span></span>

<span data-ttu-id="e5596-121">当 Excel 配置为使用多线程的工作簿重新计算， **xlAutoFree**/ **xlAutoFree12**称为用于调用的函数的返回它的同一线程。</span><span class="sxs-lookup"><span data-stu-id="e5596-121">When Excel is configured to use multithreaded workbook recalculation, **xlAutoFree**/ **xlAutoFree12** is called on the same thread used to call the function that returned it.</span></span> <span data-ttu-id="e5596-122">调用**xlAutoFree**/ **xlAutoFree12**始终进行更改之前在该线程上进行评估任何后续的工作表的单元格。</span><span class="sxs-lookup"><span data-stu-id="e5596-122">The call to **xlAutoFree**/ **xlAutoFree12** is always made before any subsequent worksheet cells are evaluated on that thread.</span></span> <span data-ttu-id="e5596-123">这样可简化您 XLL 中的线程安全设计。</span><span class="sxs-lookup"><span data-stu-id="e5596-123">This simplifies thread-safe design in your XLL.</span></span> 
  
<span data-ttu-id="e5596-124">如果**xlAutoFree**/ 您提供的**xlAutoFree12**函数会_pxFree_的**xltype**域，请记住，仍会设置**xlbitDLLFree**位。</span><span class="sxs-lookup"><span data-stu-id="e5596-124">If the **xlAutoFree**/ **xlAutoFree12** function you provide looks at the **xltype** field of  _pxFree_, remember that the **xlbitDLLFree** bit will still be set.</span></span> 
  
## <a name="example"></a><span data-ttu-id="e5596-125">示例</span><span class="sxs-lookup"><span data-stu-id="e5596-125">Example</span></span>

 <span data-ttu-id="e5596-126">**实现示例 1**</span><span class="sxs-lookup"><span data-stu-id="e5596-126">**Example Implementation 1**</span></span>
  
<span data-ttu-id="e5596-127">从第一个代码`\SAMPLES\EXAMPLE\EXAMPLE.C`演示的**xlAutoFree**，旨在处理只有一个函数， **fArray**非常具体的实现。</span><span class="sxs-lookup"><span data-stu-id="e5596-127">The first code from  `\SAMPLES\EXAMPLE\EXAMPLE.C` demonstrates a very specific implementation of **xlAutoFree**, which is designed to work with just one function, **fArray**.</span></span> <span data-ttu-id="e5596-128">通常情况下，您 XLL 将具有多个函数返回必须释放的内存，在这种情况下较宽松的实现，则需要。</span><span class="sxs-lookup"><span data-stu-id="e5596-128">In general, your XLL will have more than just one function returning memory that needs to be freed, in which case a less restricted implementation is required.</span></span> 
  
 <span data-ttu-id="e5596-129">**实现示例 2**</span><span class="sxs-lookup"><span data-stu-id="e5596-129">**Example implementation 2**</span></span>
  
<span data-ttu-id="e5596-130">第二个示例实现是与**XLOPER12**创建示例的部分 1.6.3、 xl12_Str_example、 xl12_Ref_example 和 xl12_Multi_example 中使用的假设一致。</span><span class="sxs-lookup"><span data-stu-id="e5596-130">The second example implementation is consistent with the assumptions used in the **XLOPER12** creation examples in section 1.6.3, xl12_Str_example, xl12_Ref_example, and xl12_Multi_example.</span></span> <span data-ttu-id="e5596-131">假设是的**xlbitDLLFree**位已设置、 所有字符串、 数组和外部引用内存使用**malloc**，都已动态分配和因此需要释放的调用中释放。</span><span class="sxs-lookup"><span data-stu-id="e5596-131">The assumptions are that, when the **xlbitDLLFree** bit has been set, all string, array, and external reference memory has been dynamically allocated using **malloc**, and so needs to be freed in a call to free.</span></span>
  
 <span data-ttu-id="e5596-132">**实现示例 3**</span><span class="sxs-lookup"><span data-stu-id="e5596-132">**Example implementation 3**</span></span>
  
<span data-ttu-id="e5596-133">其中导出的函数的返回**XLOPER12**s 分配字符串、 外部引用和数组使用**malloc**，且还动态分配**XLOPER12**本身的第三个示例实现与 XLL 一致。</span><span class="sxs-lookup"><span data-stu-id="e5596-133">The third example implementation is consistent with an XLL where exported functions that return **XLOPER12**s allocate strings, external references and arrays using **malloc**, and where the **XLOPER12** itself is also dynamically allocated.</span></span> <span data-ttu-id="e5596-134">返回一个指针动态分配**XLOPER12**是一种方法，以确保的功能是线程安全。</span><span class="sxs-lookup"><span data-stu-id="e5596-134">Returning a pointer to a dynamically allocated **XLOPER12** is one way to ensure that the function is thread safe.</span></span> 
  
```cs
//////////////////////////////////////////
//       BEGIN EXAMPLE IMPLEMENTATION 1
//////////////////////////////////////////
LPXLOPER12 WINAPI fArray(void)
{
    LPXLOPER12 pxArray;
    static XLOPER12 xMulti;
    int i;
    int rwcol;
    xMulti.xltype = xltypeMulti | xlbitDLLFree;
    xMulti.val.array.columns = 1;
    xMulti.val.array.rows = 8;
    // For large values of rows and columns, this would overflow
    // use __int64 in that case and return an error if rwcol
    // contains a number that won't fit in sizeof(int) bytes
    rwcol = xMulti.val.array.columns * xMulti.val.array.rows; 
    pxArray = (LPXLOPER12)GlobalLock(hArray = GlobalAlloc(GMEM_ZEROINIT, rwcol * sizeof(XLOPER12)));
    xMulti.val.array.lparray = pxArray;
    for(i = 0; i < rwcol; i++) 
    {
        pxArray[i].xltype = xltypeInt;
        pxArray[i].val.w = i;
    }
// Word of caution - returning static XLOPERs/XLOPER12s is not thread safe
// for UDFs declared as thread safe, use alternate memory allocation mechanisms
    return (LPXLOPER12)&xMulti;
}
void WINAPI xlAutoFree12(LPXLOPER12 pxFree)
{
    GlobalUnlock(hArray);
    GlobalFree(hArray);
    return;
}
//////////////////////////////////////////
//       BEGIN EXAMPLE IMPLEMENTATION 2
//////////////////////////////////////////
void WINAPI xlAutoFree12(LPXLOPER12 pxFree)
{
    if(pxFree->xltype & xltypeMulti)
    {
/* Assume all string elements were allocated using malloc, and
** need to be freed using free.  Then free the array itself.
*/
        int size = pxFree->val.array.rows *
            pxFree->val.array.columns;
        LPXLOPER12 p = pxFree->val.array.lparray;
        for(; size-- > 0; p++) // check elements for strings
            if(p->xltype == xltypeStr)
                free(p->val.str);
        free(pxFree->val.array.lparray);
    }
    else if(pxFree->xltype & xltypeStr)
    {
        free(pxFree->val.str);
    }
    else if(pxFree->xltype & xltypeRef)
    {
        free(pxFree->val.mref.lpmref);
    }
}
//////////////////////////////////////////
//       BEGIN EXAMPLE IMPLEMENTATION 3
//////////////////////////////////////////
LPXLOPER12 WINAPI example_xll_function(LPXLOPER12 pxArg)
{
// Thread-safe return value. Every invocation of this function
// gets its own piece of memory.
    LPXLOPER12 pxRtnValue = (LPXLOPER12)malloc(sizeof(XLOPER12));
// Initialize to a safe default
    pxRtnValue->xltype = xltypeNil;
// Set the value of pxRtnValue making sure that strings, external
// references, arrays, and strings within arrays are all dynamically
// allocated using malloc.
//    (code omitted)
//    ...
// Set xlbitDLLFree regardless of the type of the return value to
// ensure xlAutoFree12 is called and pxRtnValue is freed.
    pxRtnValue->xltype |= xlbitDLLFree;
    return pxRtnValue;
}
void WINAPI xlAutoFree12(LPXLOPER pxFree)
{
    if(pxFree->xltype & xltypeMulti)
    {
// Assume all string elements were allocated using malloc, and
// need to be freed using free. Then free the array itself.
        int size = pxFree->val.array.rows *
            pxFree->val.array.columns;
        LPXLOPER12 p = pxFree->val.array.lparray;
        for(; size-- > 0; p++) // check elements for strings
            if(p->xltype == xltypeStr)
                free(p->val.str);
        free(pxFree->val.array.lparray);
    }
    else if(pxFree->xltype & xltypeStr)
    {
        free(pxFree->val.str);
    }
    else if(pxFree->xltype & xltypeRef)
    {
        free(pxFree->val.mref.lpmref);
    }
// Assume pxFree was itself dynamically allocated using malloc.
    free(pxFree);
}
```

## <a name="see-also"></a><span data-ttu-id="e5596-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5596-135">See also</span></span>



[<span data-ttu-id="e5596-136">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="e5596-136">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

