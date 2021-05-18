---
title: xlAsyncReturn
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 159bc9bf-8dd5-4cd2-8384-474c74a3f112
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 32d5075af34cda9753c5d082bd4ab00afab1ecff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414107"
---
# <a name="xlasyncreturn"></a>xlAsyncReturn

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用于返回 UDF 中异步用户定义函数 (的结果) 。
  
```cpp
Excel12(xlAsyncReturn, LPXLOPER12 pxRes, 2, LPXLOPER12 pxAsyncHandle, LPXLOPER12 pxFunctionResult);
```

## <a name="parameters"></a>参数

_pxAsyncHandle_ (**xltypeBigData**) 
  
结果返回到的 UDF 的异步句柄。
  
_pxFunctionResult_
  
UDF 的返回值。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，则返回 **xltypeBool** (TRUE) 。  如果失败，则返回 **FALSE**。
  
## <a name="remarks"></a>备注

**xlAsyncReturn** 是重新计算Excel在非计算线程上唯一允许的回调模式。 异步 UDF 的异步部分不得执行 **除 xlAsyncReturn 外的任何回调**。 XLL 必须释放分配的内存以保留返回值。
  
_当 pxAsyncHandle_ 和 _pxFunctionResult_ 参数用于在单个回调中返回句柄和相应值的数组时，其类型还可以为 **xltypeMulti。** 使用单个回调时，传递一个 LPXLOPER12，该 LPXLOPER12 指向包含包含异步句柄和返回值的一维数组的 XLOPER12 结构。 这些数组的顺序必须相同，才能Excel异步句柄及其相应值正确匹配。 
  
以下示例演示如何使用 **xlAsyncReturn 进行批处理调用**。
  
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

