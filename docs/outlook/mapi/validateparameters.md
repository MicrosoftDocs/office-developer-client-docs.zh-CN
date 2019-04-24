---
title: ValidateParameters
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ValidateParameters
api_type:
- COM
ms.assetid: 80aadd11-5409-4636-8fad-fa2206336671
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3862ea539907bb0570a0e845b09a15e7bed0507
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329566"
---
# <a name="validateparameters"></a>ValidateParameters

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
调用内部函数以检查客户端应用程序已传递给服务提供程序的参数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
HRESULT ValidateParameters(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a>参数

 _eMethod_
  
> 实时通过枚举指定要验证的方法。 
    
 _第一_
  
> 实时指向堆栈上第一个参数的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 所有参数都有效。 
    
MAPI_E_CALL_FAILED 
  
> 一个或多个参数无效。
    
## <a name="remarks"></a>注解

**ValidateParameters**宏已被[ValidateParms](validateparms.md)宏取代。 **ValidateParameters**不能在 RISC 平台上正常运行, 现在无法在其上进行编译。 它仍可在 Intel 平台上正常编译和工作, 但建议在所有平台上使用**ValidateParms** 。 
  

