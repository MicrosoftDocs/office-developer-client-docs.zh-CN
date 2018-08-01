---
title: xlAsyncReturn
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 159bc9bf-8dd5-4cd2-8384-474c74a3f112
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e7ba37629ff2198339394448410ffd16477d4766
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773832"
---
# <a name="xlasyncreturn"></a>xlAsyncReturn

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于返回结果的异步的用户定义函数 (UDF)。
  
```cpp
Excel12(xlAsyncReturn, LPXLOPER12 pxRes, 2, LPXLOPER12 pxAsyncHandle, LPXLOPER12 pxFunctionResult);
```

## <a name="parameters"></a>参数

_pxAsyncHandle_(**xltypeBigData**)
  
结果返回到 UDF 异步句柄。
  
_pxFunctionResult_
  
UDF 返回值。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，则返回**TRUE** (**xltypeBool**)。 如果不成功，则返回**FALSE**。
  
## <a name="remarks"></a>说明

**xlAsyncReturn**是仅重新计算过程中允许非计算线程的 Excel 的回调。 异步 UDF 的异步部分未对执行**xlAsyncReturn**之外的任何回调。 XLL 必须释放内存分配用于存放的返回值。
  
类型**xltypeMulti**用于在单个回调返回数组的句柄和相应的值时，也可以是在_pxAsyncHandle_和_pxFunctionResult_参数。 使用单个回调时, 传递指向包含一个二维数组，包含异步句柄和返回值的 XLOPER12 结构 LPXLOPER12。 这些阵列必须 excel 以正确匹配异步句柄，其相应的值相同的顺序。 
  
下面的示例演示如何才能使用**xlAsyncReturn**调用的批次。
  
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

- [用户定义的异步函数](asynchronous-user-defined-functions.md)

