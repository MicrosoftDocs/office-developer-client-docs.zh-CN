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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3dfba5ae98b0635c95308eac01bf2f10867678e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303967"
---
# <a name="xlautofreexlautofree12"></a>xlAutoFree/xlAutoFree12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
在 xll 工作表函数返回一个**XLOPER**/ **XLOPER12**为其的标志集后, 由 Microsoft Excel 调用它, 以告知存在 XLL 仍需要释放的内存。 这将会使 XLL 动态返回已分配的数组、字符串以及没有内部泄漏的工作表的外部引用。 有关详细信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。
  
从 Excel 2007 开始, 支持**xlAutoFree12**函数和**XLOPER12**数据类型。 
  
Excel 不需要 XLL 即可实现和导出这两个函数中的任何一个。 但是, 如果 XLL 函数返回的 XLOPER 或 XLOPER12 已动态分配或包含指向动态分配的内存的指针, 则必须执行此操作。 确保您选择的如何管理这些类型的内存在整个 XLL 中是一致的, 以及您如何实现**xlAutoFree**和**xlAutoFree12**。
  
在**xlAutoFree**/ **xlAutoFree12**函数的内部, 将禁用对 Excel 的回调, 但有一个例外: 可以调用**xlFree**以释放 Excel 分配的内存。 
  
```cs
void WINAPI xlAutoFree(LPXLOPER pxFree);
void WINAPI xlAutoFree12(LPXLOPER12 pxFree);
```

## <a name="parameters"></a>参数

 _pxFree_(**在 xlAutoFree 的情况下为 LPXLOPER**)
  
 _pxFree_(**在 xlAutoFree12 的情况下为 LPXLOPER12**)
  
指向包含需要释放的内存的**XLOPER**或**XLOPER12**的指针。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数不返回值, 应声明为返回 void。
  
## <a name="remarks"></a>注解

将 Excel 配置为使用多线程工作簿重新计算时, 将对用于调用返回它的函数的同一线程调用**xlAutoFree**/ **xlAutoFree12** 。 在对该线程上的任何后续工作表单元格进行求值之前，始终调用 **xlAutoFree**/ **xlAutoFree12**。 这可以简化 XLL 中的线程安全设计。 
  
如果您提供的**xlAutoFree**/ **xlAutoFree12**函数将查看_pxFree_的**xltype**字段, 请注意, 仍将设置**xlbitDLLFree**位。 
  
## <a name="example"></a>示例

 **示例实现1**
  
中`\SAMPLES\EXAMPLE\EXAMPLE.C`的第一个代码演示**xlAutoFree**的非常具体的实现, 该实现仅用于一个函数**fArray**。 通常情况下, XLL 将不仅有一个返回需要释放的内存的函数, 在这种情况下, 需要的实现较少。 
  
 **示例实现2**
  
第二个示例实现符合**XLOPER12**在1.6.3、xl12_Str_example、xl12_Ref_example 和 xl12_Multi_example 一节中的 "创建" 示例中使用的假设。 假定在设置**xlbitDLLFree**位后, 已使用**malloc**动态分配所有字符串、数组和外部引用内存, 因此需要在空闲调用中释放。
  
 **示例实现3**
  
第三个示例实现与 XLL (其中返回**XLOPER12**的导出函数使用**malloc**分配字符串、外部引用和数组) 保持一致, 同时还动态分配**XLOPER12**本身。 将指针返回到动态分配的**XLOPER12**是一种确保函数是线程安全的方法。 
  
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

