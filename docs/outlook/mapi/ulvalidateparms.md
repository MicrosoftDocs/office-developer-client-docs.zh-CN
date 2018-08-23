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
ms.openlocfilehash: b71d1f477435b4a9327b4156560d1aa2e6079536
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578701"
---
# <a name="ulvalidateparms"></a>UlValidateParms

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
调用检查参数客户端应用程序已传递给服务提供商和 MAPI 内部函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
HRESULT UlValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a>参数

 _eMethod_
  
> [in]通过枚举，指定要验证的方法。 
    
 _第一_
  
> [in]堆栈上第一个参数的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_CALL_FAILED 
  
> 出现错误，无法完成操作。
    
## <a name="remarks"></a>注解

MAPI 和服务之间传递参数提供程序将假定它们正确，且经过仅调试验证与[CheckParms](checkparms.md)宏。 提供程序应检查所有参数中传递的客户端应用程序，但客户端应假定 MAPI 和提供程序参数正确。 使用**HR_FAILED**宏来测试返回值。 
  
根据调用的代码是否为 C 或 c + + 不同调用**UlValidateParms**宏。 使用此宏来验证返回 ULONG 而不是 HRESULT 值; 几**IUnknown**和 MAPI 方法的参数[ValidateParms](validateparms.md)宏适用于所有其他人。 
  

