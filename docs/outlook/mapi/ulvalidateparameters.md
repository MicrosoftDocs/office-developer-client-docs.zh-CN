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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 465069f08e2026dcbf98e24f0f5f59e12ed17eca
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431272"
---
# <a name="ulvalidateparameters"></a>UlValidateParameters

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
调用内部函数以检查客户端应用程序已传递给服务提供商和 MAPI 的参数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
HRESULT UlValidateParameters(
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
  
> 意外或未知来源的错误阻止了操作完成。
    
## <a name="remarks"></a>备注

**UlValidateParameters** 宏已被 [UlValidateParms](ulvalidateparms.md)宏取代。 **UlValidateParameters** 在 RISC 平台上无法正常工作，现在无法对它们进行编译。 它仍然可以在 Intel 平台上编译并正常运行，但建议在所有平台上使用 **UlValidateParms。** 
  

