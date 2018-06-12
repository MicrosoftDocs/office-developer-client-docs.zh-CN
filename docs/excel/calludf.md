---
title: CallUDF
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6421c9a2-07f7-4deb-aa43-c50d82cb0002
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 1d55f22de88b274d0403f81717d0fddefbea0219
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773630"
---
# <a name="calludf"></a>CallUDF

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
在高性能计算环境中调用用户定义函数。
  
```cpp
int CallUDF(int SessionId, WCHAR *XllName, WCHAR *UDFName, LPXLOPER12 pxAsyncHandle, int (*CallBackAddr)(), int ArgCount, LPXLOPER12 Parameter1, ...)
```

## <a name="parameters"></a>参数

_SessionId_
  
> 要在其中进行呼叫的会话 ID。
    
_XLLName_
  
> 包含用户定义函数的 XLL 的名称。
    
_UDFName_
  
> 用户定义函数的名称。
    
_CallBackAddr_
  
> 连接器应调用用户定义函数完成函数。
    
_pxAsyncHandle_
  
> 使用 Excel 和连接器以跟踪待处理的用户定义的函数调用异步句柄。 连接器稍后使用完成呼叫后，当它回拨入 Excel 使用函数指针_CallBackAddr_参数中传递。 
    
_ArgCount_
  
> 要传递给的用户定义的函数的参数数目。 允许的最大值是 255。
    
_Parameter1_
  
> 要传递给的用户定义的函数值。 重复的每个参数由_ArgCount_此参数。
    
## <a name="return-value"></a>返回值

**xlHpcRetSuccess** UDF 调用成功启动; 如果**xlHpcRetInvalidSessionId** _SessionId_参数无效; 如果在其他失败时，包括超时**xlHpcRetCallFailed** 。如果调用返回任何错误代码 （任何**xlHpcRetSuccess**除外），然后 Excel 认为已失败的 UDF 调用，使无效_pxAsyncHandle_，并不需要执行的回调。
  
## <a name="remarks"></a>备注

此函数异步执行。
  
## <a name="see-also"></a>另请参阅

- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

