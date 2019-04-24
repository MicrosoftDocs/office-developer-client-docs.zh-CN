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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3e68c564357880b623e02081a228e881c084fa94
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351609"
---
# <a name="ixplogonpoll"></a>IXPLogon::Poll

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示传输提供程序是否已收到一个或多个入站邮件。
  
```cpp
HRESULT Poll(
  ULONG FAR * lpulIncoming
);
```

## <a name="parameters"></a>参数

 _lpulIncoming_
  
> 排除一个指示是否存在入站邮件的值。 非零值表示有入站邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序定期调用**IXPLogon::P oll**方法如果传输提供程序指示它必须通过将 LOGON_SP_POLL 标志传递给[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)的新邮件进行轮询::会话开始时的方法。 如果传输提供程序指示有一个或多个可供其处理的入站邮件的**轮询**呼叫响应, MAPI 后台处理程序将调用[IXPLogon:: StartMessage](ixplogon-startmessage.md)方法, 以允许提供程序处理第一个入站消息。 传输提供程序通过将_lpulIncoming_参数中的值设置为非零值来指示入站邮件。 
  
## <a name="see-also"></a>另请参阅



[IXPLogon::StartMessage](ixplogon-startmessage.md)
  
[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

