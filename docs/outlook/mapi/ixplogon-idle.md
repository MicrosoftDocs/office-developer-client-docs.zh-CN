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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32298479"
---
# <a name="ixplogonidle"></a>IXPLogon::Idle

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示系统处于空闲状态, 使传输提供程序能够执行低优先级操作。
  
```cpp
HRESULT Idle(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>注解

在系统空闲时, MAPI 后台处理程序定期调用**IXPLogon:: idle**方法 (如果请求), 通过在调用[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)方法时传递对打开当前会话的 XP_LOGON_SP 标志。 在系统处于空闲状态时, 传输提供程序可以执行在其他呼叫过程中不适合或定期发生的后台操作。 
  
## <a name="see-also"></a>另请参阅



[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

