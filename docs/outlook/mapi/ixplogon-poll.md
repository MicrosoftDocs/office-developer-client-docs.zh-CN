---
title: IXPLogonPoll
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.Poll
api_type:
- COM
ms.assetid: 1524eb06-7492-42de-b455-e0982bda7ece
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 17470f9ff552eaa4908973c4f033db2b4e754d7c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776124"
---
# <a name="ixplogonpoll"></a>IXPLogon::Poll

  
  
**适用于**： Outlook 
  
指示的传输提供程序是否已接收到一个或多个入站的邮件。
  
```cpp
HRESULT Poll(
  ULONG FAR * lpulIncoming
);
```

## <a name="parameters"></a>参数

 _lpulIncoming_
  
> [输出]一个值，指示存在入站邮件。 为非零值指示存在入站的邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

如果传输提供程序指示它必须轮询新邮件，提供程序会通过传递 LOGON_SP_POLL 标记对[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)调用 MAPI 后台处理程序将定期调用**IXPLogon::Poll**方法会话开头的方法。 如果有一个**投票**呼叫的响应中指示的传输提供程序或入站的邮件更多可用的过程，MAPI 后台处理程序调用[IXPLogon::StartMessage](ixplogon-startmessage.md)方法，以允许对第一个过程的提供程序的入站邮件消息。 传输提供程序值设置为非零值_lpulIncoming_参数中指示入站的邮件。 
  
## <a name="see-also"></a>另请参阅



[IXPLogon::StartMessage](ixplogon-startmessage.md)
  
[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

