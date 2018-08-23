---
title: IMAPISupportSpoolerNotify
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.SpoolerNotify
api_type:
- COM
ms.assetid: d4f153b2-939f-4153-85fb-dc510193848c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a2837e5470729ae3cdd0b83e17d0342620c986e8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592113"
---
# <a name="imapisupportspoolernotify"></a>IMAPISupport::SpoolerNotify

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
通知状态或服务的请求中的更改 MAPI 后台处理程序。 
  
```cpp
HRESULT SpoolerNotify(
ULONG ulFlags,
LPVOID lpvData
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，指示通知的类型。 传输提供程序可以设置的所有除外 NOTIFY_NEWMAIL_RECEIVED; 标志只有 NOTIFY_NEWMAIL_RECEIVED 和 NOTIFY_READTOSEND 是有效的消息存储提供程序。 以下标志可用于_ulFlags_参数： 
    
NOTIFY_CONFIG_CHANGE 
  
> 注册请求更改传输提供程序的配置。 
    
NOTIFY_CRITICAL_ERROR 
  
> 传输提供程序已发生不可恢复的错误。 因为 NOTIFY_SENTDEFERRED 和 NOTIFY_CRITICAL_ERROR 用于传输提供程序调用_lpvData_参数，这些标志是互斥的。 
    
NOTIFY_CRITSEC 
  
> 传输提供程序请求的关键部分。 _LpvData_参数未定义，并且应为 NULL。 
    
NOTIFY_NEWMAIL 
  
> MAPI 后台处理程序应在下一可用时间下载任何新接收的消息。 _LpvData_参数不确定，应设置为 NULL。 
    
NOTIFY_NEWMAIL_RECEIVED 
  
> 消息存储库中已收到新消息。 _LpvData_参数指向介绍邮件[NEWMAIL_NOTIFICATION](newmail_notification.md)结构。 此标志用于与传输提供程序紧密耦合的消息存储提供程序，并且如果设置了 MAPI_NO_MAIL 标志登录的存储提供程序，则忽略。 
    
NOTIFY_NONCRIT 
  
> 释放与_ulFlags_设置为 NOTIFY_CRITSEC 获取与以前调用**SpoolerNotify**关键部分。 _LpvData_参数不确定，应设置为 NULL。 
    
NOTIFY_READYTOSEND 
  
> 传输或消息存储提供程序已准备好发送消息。 _LpvData_参数不确定，应设置为 NULL。 
    
NOTIFY_SENTDEFERRED 
  
> 现在应发送之前延迟的邮件，并已准备好使用[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)方法调用传递邮件时，应通知传输提供程序。 延迟的邮件的项标识符包含在由_lpvData_指向[SBinary](sbinary.md)结构。 因为 NOTIFY_SENTDEFERRED 和 NOTIFY_CRITICAL_ERROR 使用_lpvData_参数，这些标志是互斥的。 
    
 _lpvData_
  
> [in]指向适用于通知关联的数据的指针。 _LpvData_参数仅在设置了以下标志时指向有效的数据 （_lpvData_ _ulFlags_设置为其他通知类型时为 NULL）： 
    
|**_ulFlags_设置**|**_lpvData_值**|
|:-----|:-----|
|NOTIFY_CRITICAL_ERROR  <br/> |有关错误的信息。  <br/> |
|NOTIFY_NEWMAIL_RECEIVED  <br/> |**NEWMAIL_NOTIFICATION**结构，其中包含有关在新的已发送邮件的信息。  <br/> |
|NOTIFY_SENTDEFERRED  <br/> |**SBinary**结构，其中包含延迟消息的项标识符。  <br/> |
   
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
## <a name="remarks"></a>注解

**IMAPISupport::SpoolerNotify**方法已实现的消息存储和传输提供程序支持对象。 这些提供程序调用**SpoolerNotify**以通知状态或服务的请求中的更改 MAPI 后台处理程序。 **SpoolerNotify**主要由传输提供程序，可能在会话期间随时调用。 
  
## <a name="notes-to-transport-providers"></a>Notes 传输提供程序

如果更改了传输提供程序配置后，调用**SpoolerNotify**并设置_ulFlags_为 NOTIFY_CONFIG_CHANGED。 **SpoolerNotify**响应通过调用[IXPLogon::AddressTypes](ixplogon-addresstypes.md)查询中支持的地址类型的更改。 
  
如果您需要以确保不中断的处理的关键部分，设置为 NOTIFY_CRITSEC _ulFlags_呼叫**SpoolerNotify** 。 设置此标志通知 MAPI 后台处理程序，它不应调用的[IXPLogon::Idle](ixplogon-idle.md)和[IXPLogon::Poll](ixplogon-poll.md)方法。 在您已经打开，只要调用[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法返回 MAPI_E_BUSY 的关键部分。 当您已完成关键部分时，进行_ulFlags_设置为 NOTIFY_NONCRIT **SpoolerNotify**到另一个呼叫。 
  
例如，如果您的远程传输提供程序的过程中上载邮件，您可能需要允许用户输入要建立远程连接的电话号码。 循环访问的对话框过程之前，您应声明的关键部分。 当用户关闭对话框时，终止的对话框过程，您应释放关键部分。
  
当到 NOTIFY_CRITICAL_ERROR 设置_ulFlags_时，MAPI 后台处理程序调用没有进一步除若要释放其提供程序。 如果您调用**SpoolerNotify**与 NOTIFY_CRITICAL_ERROR 设置从[IXPLogon::StartMessage](ixplogon-startmessage.md)或[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)方法，返回与相应的错误值从**StartMessage**或 * * SubmitMessage * * 呼叫紧接着**SpoolerNotify**呼叫。 
  
如果您传输提供程序恢复从先前导致失败的情况，呼叫将设置为 NOTIFY_READYTOSEND _ulFlags_ **SpoolerNotify** 。 此标志指示提供程序再次已准备好处理的消息。 
  
## <a name="notes-to-message-store-providers"></a>对消息存储提供程序的说明

调用**SpoolerNotify**之前在**IMessage::SubmitMessage**使[IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md)您首次调用, 中_ulFlags_，传递 NOTIFY_READYTOSEND 标志。 此呼叫到**SpoolerNotify**需要对每个会话仅执行一次进行。 
  
如果紧密耦合消息存储提供程序与传输提供程序并调用**SpoolerNotify** _ulFlags_设置为 NOTIFY_NEWMAIL_RECEIVED，MAPI 后台处理程序中打开新的邮件并开始处理新消息挂钩函数。 处理完成后，MAPI 后台处理程序调用[IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)方法来通知您自己的新消息。 
  
有关调用**SpoolerNotify**的详细信息，请参阅以下主题中的任意：
  
- [实现 FlushQueues 方法](implementing-the-flushqueues-method.md)
    
- [与 MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)
    
- [邮件接收模型](message-reception-model.md)
    
## <a name="see-also"></a>另请参阅



[IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)
  
[IXPLogon::StartMessage](ixplogon-startmessage.md)
  
[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

