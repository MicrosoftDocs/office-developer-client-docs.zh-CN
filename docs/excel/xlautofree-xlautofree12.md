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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3dfba5ae98b0635c95308eac01bf2f10867678e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413288"
---
# <a name="xlautofreexlautofree12"></a>xlAutoFree/xlAutoFree12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
XLL Microsoft Excel函数将 **XLOPER** /  **XLOPER12 返回给 XLOPER12** 后调用，该标记集指示有 XLL 仍然需要释放的内存。 这将会使 XLL 动态返回已分配的数组、字符串以及没有内部泄漏的工作表的外部引用。 有关详细信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。
  
从 2007 Excel开始，**支持 xlAutoFree12** 函数和 **XLOPER12** 数据类型。 
  
Excel不需要 XLL 来实现和导出其中任一函数。 但是，如果 XLL 函数返回已动态分配的 XLOPER 或 XLOPER12 或包含动态分配内存的指针，则必须这样做。 确保你选择如何管理这些类型的内存在整个 XLL 中以及实现 **xlAutoFree** 和 **xlAutoFree12** 的方式一致。
  
在 **xlAutoFree** /  **xlAutoFree12** 函数中，将禁用对 Excel 的回调，但只有一个例外：可以调用 **xlFree** 以释放Excel分配的内存。 
  
```cs
void WINAPI xlAutoFree(LPXLOPER pxFree);
void WINAPI xlAutoFree12(LPXLOPER12 pxFree);
```

## <a name="parameters"></a>参数

 对于 **xlAutoFree** _(，pxFree_) 
  
 对于 **xlAutoFree12 (** _pxFree_) 
  
指向 **XLOPER** 或具有需要释放内存的 **XLOPER12** 的指针。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数不返回值，应声明为返回 void。
  
## <a name="remarks"></a>备注

当Excel工作簿重新计算时，将在用于调用返回函数的同一线程上调用 **xlAutoFree** /  **xlAutoFree12。** 在对该线程上的任何后续工作表单元格进行求值之前，始终调用 **xlAutoFree**/ **xlAutoFree12**。 这可以简化 XLL 中的线程安全设计。 
  
如果您提供的 **xlAutoFree** /  **xlAutoFree12** 函数查看 _pxFree_ 的 **xltype** 字段，请记住 **，仍将设置 xlbitDLLFree** 位。 
  
## <a name="example"></a>示例

 **示例实现 1**
  
来自 的第一  `\SAMPLES\EXAMPLE\EXAMPLE.C` 个代码演示 **了 xlAutoFree** 的非常具体的实现，该实现设计为仅与一个函数 **fArray 一起使用**。 一般情况下，你的 XLL 将具有多个返回需要释放的内存的函数，在这种情况下需要不太受限制的实现。 
  
 **示例实现 2**
  
第二个示例实现与第 1.6.3 节中 **的 XLOPER12** 创建示例、xl12_Str_example、xl12_Ref_example 和 xl12_Multi_example 中使用的假设一致。 假定前提是，在 **设置了 xlbitDLLFree** 位后，所有字符串、数组和外部引用内存已使用 **arrayoc** 动态分配，因此需要在调用中释放以释放。
  
 **示例实现 3**
  
第三个示例实现与 XLL 一致，其中返回 **XLOPER12** 的导出函数使用 **arrayoc** 分配字符串、外部引用和数组，并且 **XLOPER12** 本身也动态分配。 返回指向动态分配的 **XLOPER12** 的指针是确保函数是线程安全的一种方式。 
  
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

## <a name="see-also"></a>另请参阅



[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

