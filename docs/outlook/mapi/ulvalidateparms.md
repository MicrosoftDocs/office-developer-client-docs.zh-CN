---
title: UlValidateParms
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlValidateParms
api_type:
- COM
ms.assetid: 02c66b46-1f01-43fb-832c-bac27aaae19f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e0cdcb92238dd4dffbcd6514e698e5511b05bf45
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419609"
---
# <a name="ulvalidateparms"></a>UlValidateParms

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
调用内部函数以检查客户端应用程序已传递给服务提供商和 MAPI 的参数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
HRESULT UlValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a>参数

 _eMethod_
  
> [in]通过枚举指定要验证的方法。 
    
 _第一_
  
> [in]指向堆栈上第一个参数的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。 
    
MAPI_E_CALL_FAILED 
  
> 错误阻止了操作完成。
    
## <a name="remarks"></a>备注

在 MAPI 和服务提供商之间传递的参数被认为是正确的，并且只接受 [CheckParms 宏的调试](checkparms.md) 验证。 提供程序应检查客户端应用程序传入的所有参数，但客户端应假定 MAPI 和提供程序参数正确。 使用 **HR_FAILED** 宏测试返回值。 
  
根据调用代码是 C 还是 C++，调用 **UlValidateParms** 宏的方式不同。 此宏用于验证返回 ULONG（而不是 HRESULT 值）的一些 **IUnknown** 和 MAPI 方法的参数; [ValidateParms](validateparms.md) 宏适用于所有其他宏。 
  

