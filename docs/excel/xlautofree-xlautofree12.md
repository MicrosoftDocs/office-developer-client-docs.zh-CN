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
# <a name="xlautofreexlautofree12"></a>xlAutoFree/xlAutoFree12

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
Microsoft Excel XLL 工作表函数返回**XLOPER**后立即调用/ **XLOPER12**向其设置标志告知 XLL 仍需要释放的内存。 这样，XLL 返回动态分配数组、 字符串和不内存泄漏工作表的外部引用。 有关详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。
  
从 Excel 2007 开始， **xlAutoFree12**函数和**XLOPER12**数据类型的支持。 
  
Excel 不需要 XLL 实施和导出其中任一函数。 但是，您必须完成如果 XLL 函数返回 XLOPER 或 XLOPER12 已动态分配的或包含指向动态分配的内存。 确保您选择如何管理这些类型的内存整个您 XLL 和如何实现**xlAutoFree**和**xlAutoFree12**保持一致。
  
内部**xlAutoFree**/ **xlAutoFree12**函数，导入 Excel 回调被禁用，有一个例外： **xlFree**可调用它以释放 Excel 分配内存。 
  
```cs
void WINAPI xlAutoFree(LPXLOPER pxFree);
void WINAPI xlAutoFree12(LPXLOPER12 pxFree);
```

## <a name="parameters"></a>参数

 _pxFree_(**对于 xlAutoFree LPXLOPER**)
  
 _pxFree_(**对于 xlAutoFree12 LPXLOPER12**)
  
一个指向**XLOPER**或**XLOPER12**已被释放所需的内存。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数不会返回一个值，并应声明为返回无效。
  
## <a name="remarks"></a>备注

当 Excel 配置为使用多线程的工作簿重新计算， **xlAutoFree**/ **xlAutoFree12**称为用于调用的函数的返回它的同一线程。 调用**xlAutoFree**/ **xlAutoFree12**始终进行更改之前在该线程上进行评估任何后续的工作表的单元格。 这样可简化您 XLL 中的线程安全设计。 
  
如果**xlAutoFree**/ 您提供的**xlAutoFree12**函数会_pxFree_的**xltype**域，请记住，仍会设置**xlbitDLLFree**位。 
  
## <a name="example"></a>示例

 **实现示例 1**
  
从第一个代码`\SAMPLES\EXAMPLE\EXAMPLE.C`演示的**xlAutoFree**，旨在处理只有一个函数， **fArray**非常具体的实现。 通常情况下，您 XLL 将具有多个函数返回必须释放的内存，在这种情况下较宽松的实现，则需要。 
  
 **实现示例 2**
  
第二个示例实现是与**XLOPER12**创建示例的部分 1.6.3、 xl12_Str_example、 xl12_Ref_example 和 xl12_Multi_example 中使用的假设一致。 假设是的**xlbitDLLFree**位已设置、 所有字符串、 数组和外部引用内存使用**malloc**，都已动态分配和因此需要释放的调用中释放。
  
 **实现示例 3**
  
其中导出的函数的返回**XLOPER12**s 分配字符串、 外部引用和数组使用**malloc**，且还动态分配**XLOPER12**本身的第三个示例实现与 XLL 一致。 返回一个指针动态分配**XLOPER12**是一种方法，以确保的功能是线程安全。 
  
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

