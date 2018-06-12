---
title: UlValidateParameters
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlValidateParameters
api_type:
- COM
ms.assetid: fb9050c9-5797-44f0-8bf5-6264f4e6d7c3
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 42b2f8e9695b1dbdc5ea02db5a4e8a0eaba6099c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779046"
---
# <a name="ulvalidateparameters"></a>UlValidateParameters

  
  
**适用于**： Outlook 
  
调用检查参数客户端应用程序已传递给服务提供商和 MAPI 内部函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
HRESULT UlValidateParameters(
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
  
> 意外或未知的原点出现错误，无法完成操作。
    
## <a name="remarks"></a>备注

已由[UlValidateParms](ulvalidateparms.md)宏取代**UlValidateParameters**宏。 **UlValidateParameters** RISC 平台上不会无法正常工作，现在将会阻止对它们进行编译。 仍编译，并能够正常运行 Intel 平台上，但**UlValidateParms**建议所有平台上。 
  

