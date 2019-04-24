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
# <a name="xlasyncreturn"></a>xlAsyncReturn

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于返回异步用户定义函数 (UDF) 的结果。
  
```cpp
Excel12(xlAsyncReturn, LPXLOPER12 pxRes, 2, LPXLOPER12 pxAsyncHandle, LPXLOPER12 pxFunctionResult);
```

## <a name="parameters"></a>参数

_pxAsyncHandle_(**xltypeBigData**)
  
将返回其结果的 UDF 的异步句柄。
  
_pxFunctionResult_
  
UDF 的返回值。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功,**则返回 TRUE** (**xltypeBool**)。 如果不成功, 则返回**FALSE**。
  
## <a name="remarks"></a>注解

**xlAsyncReturn**是 Excel 在重新计算期间允许对非计算线程执行的唯一回调。 异步 UDF 的异步部分不能执行除**xlAsyncReturn**以外的任何回调。 XLL 必须释放分配的内存以容纳返回值。
  
_pxAsyncHandle_和_pxFunctionResult_参数也可以是**xltypeMulti**类型, 用于在单个回调中返回句柄的数组和相应的值。 使用单个回调时, 传递指向 XLOPER12 结构的 LPXLOPER12, 其中包含一个包含异步句柄和返回值的维度数组。 这些数组必须具有相同的顺序, Excel 才能正确匹配异步句柄与其对应的值。 
  
下面的示例展示了如何使用**xlAsyncReturn**进行批处理调用。
  
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

## <a name="see-also"></a>另请参阅

- [用户定义异步函数](asynchronous-user-defined-functions.md)

