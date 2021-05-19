---
title: CallUDF
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6421c9a2-07f7-4deb-aa43-c50d82cb0002
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 096f57335572c3788fdf129dd3bcf4a76cf62b01
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433008"
---
# <a name="calludf"></a>CallUDF

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
在高性能计算环境中调用用户定义的函数。
  
```cpp
int CallUDF(int SessionId, WCHAR *XllName, WCHAR *UDFName, LPXLOPER12 pxAsyncHandle, int (*CallBackAddr)(), int ArgCount, LPXLOPER12 Parameter1, ...)
```

## <a name="parameters"></a>参数

_SessionId_
  
> 要调用的会话的 ID。
    
_XLLName_
  
> 包含用户定义函数的 XLL 的名称。
    
_UDFName_
  
> 用户定义的函数的名称。
    
_CallBackAddr_
  
> 完成用户定义函数后连接器应调用的函数。
    
_pxAsyncHandle_
  
> 客户端和连接器Excel用于跟踪挂起的用户定义函数调用的异步句柄。 连接器稍后在调用完成时，使用 _CallBackAddr_ 参数中传递的函数指针Excel回调用回代码时使用它。 
    
_ArgCount_
  
> 要传递给用户定义函数的参数数。 允许的最大值为 255。
    
_Parameter1_
  
> 要传递给用户定义的函数的值。 对  _ArgCount_ 指示的每个参数重复此参数。
    
## <a name="return-value"></a>返回值

**xlHpcRetSuccess（** 如果成功启动 UDF 调用）;**xlHpcRetInvalidSessionId** 如果 _SessionId_ 参数无效;**xlHpcRetCallFailed** 其他故障，包括退出。如果调用返回任何错误代码 (**除 xlHpcRetSuccess**) 之外的任何错误代码，Excel 会认为 UDF 调用失败，使 _pxAsyncHandle_ 无效，并且预计不会发生回调。
  
## <a name="remarks"></a>备注

此函数异步执行。
  
## <a name="see-also"></a>另请参阅

- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

