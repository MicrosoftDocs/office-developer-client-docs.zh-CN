---
title: CheckParms
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.CheckParms
api_type:
- COM
ms.assetid: 328f12f0-e4e7-407f-8eb8-0d4bf543962d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ffa1b596b2f60bce35f24df8a20326502be8165a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422276"
---
# <a name="checkparms"></a>CheckParms

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
调用内部函数来验证 MAPI 调用的服务提供程序方法的调试参数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
HRESULT CheckParms(
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
  
> 调用成功。
    
## <a name="remarks"></a>说明

与[ValidateParms](validateparms.md)和[UlValidateParms](ulvalidateparms.md)宏相反, **CheckParms**宏不执行完整参数验证。 假定在 MAPI 和服务提供程序之间传递的参数是正确的, 因此**CheckParms**仅执行调试验证。 
  

