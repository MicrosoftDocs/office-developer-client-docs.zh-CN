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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 12aa8b79e38320d9767a6c333cb0197ea5669862
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578009"
---
# <a name="ixplogonidle"></a>IXPLogon::Idle

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示系统空闲，启用传输提供程序执行低优先级操作。
  
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
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序定期调用**IXPLogon::Idle**方法中，如果请求，期间系统时通过对打开当前会话的[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)方法的调用中传递 XP_LOGON_SP 标志处于空闲状态的时间。 有时系统空闲时，传输提供程序可以执行后台操作的链接不适当期间其他呼叫，或需要定期发生。 
  
## <a name="see-also"></a>另请参阅



[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

