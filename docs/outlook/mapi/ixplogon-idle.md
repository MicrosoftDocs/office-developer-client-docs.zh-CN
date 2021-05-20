---
title: IXPLogonIdle
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.Idle
api_type:
- COM
ms.assetid: 8f600db6-f6a6-44f9-aef7-c1309f61eb12
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ceca6a2dbe5f80f8a3499e509db8d5e6c35d72d0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436046"
---
# <a name="ixplogonidle"></a>IXPLogon::Idle

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示系统处于空闲状态，使传输提供程序能够执行低优先级操作。
  
```cpp
HRESULT Idle(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
## <a name="remarks"></a>备注

如果请求，MAPI 后台处理程序在系统空闲时定期调用 **IXPLogon：：Idle** 方法，方法是在调用中将 XP_LOGON_SP 标志传递给打开当前会话的 [IXPProvider：：TransportLogon](ixpprovider-transportlogon.md) 方法。 当系统处于空闲状态时，传输提供程序可以执行其他调用期间不适合的后台操作，或者需要定期执行这些后台操作。 
  
## <a name="see-also"></a>另请参阅



[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

