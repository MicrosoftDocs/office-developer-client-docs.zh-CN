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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 921417d8fc73ca9c1f126b2cb0add23f6625e3f4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779085"
---
# <a name="validateparameters"></a>ValidateParameters

  
  
**适用于**： Outlook 
  
调用检查参数客户端应用程序已传递给服务提供商的内部函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
HRESULT ValidateParameters(
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
  
> 所有参数都是有效的。 
    
MAPI_E_CALL_FAILED 
  
> 一个或多个参数不是有效的。
    
## <a name="remarks"></a>备注

已由[ValidateParms](validateparms.md)宏取代**ValidateParameters**宏。 **ValidateParameters** RISC 平台上不会无法正常工作，现在将会阻止对它们进行编译。 仍编译，并能够正常运行 Intel 平台上，但**ValidateParms**建议所有平台上。 
  

