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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425272"
---
# <a name="ixplogonpoll"></a>IXPLogon::Poll

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示传输提供程序是否收到一个或多个入站邮件。
  
```cpp
HRESULT Poll(
  ULONG FAR * lpulIncoming
);
```

## <a name="parameters"></a>参数

 _lpulIncoming_
  
> [out]指示存在入站邮件的值。 非零值表示存在入站邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

如果传输提供程序指示必须轮询 **IXPLogon：:P oll** 方法，MAPI 后台处理程序会定期调用 IXPLogon：:P oll 方法，提供程序通过向会话开始时的 [IXPProvider：：TransportLogon](ixpprovider-transportlogon.md) 方法的调用传递 LOGON_SP_POLL 标志来轮询新邮件。 如果传输提供程序在响应 **轮询** 调用时指示有一个或多个入站邮件可供其处理，则 MAPI 后台处理程序将调用 [IXPLogon：：StartMessage](ixplogon-startmessage.md) 方法，以允许提供程序处理第一个入站邮件。 传输提供程序通过将  _lpulIncoming_ 参数中的值设置为非零值来指示入站邮件。 
  
## <a name="see-also"></a>另请参阅



[IXPLogon::StartMessage](ixplogon-startmessage.md)
  
[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

