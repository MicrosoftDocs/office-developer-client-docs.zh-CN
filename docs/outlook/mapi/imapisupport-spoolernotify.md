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
ms.openlocfilehash: 99377d63b4b5cf8731809446b70770f0c24231ed
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423767"
---
# <a name="imapisupportspoolernotify"></a>IMAPISupport::SpoolerNotify

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知 MAPI 后台处理程序的状态更改或服务请求。 
  
```cpp
HRESULT SpoolerNotify(
ULONG ulFlags,
LPVOID lpvData
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时指示通知类型的标志的位掩码。 传输提供程序可以设置除 NOTIFY_NEWMAIL_RECEIVED 之外的所有标志;只有 NOTIFY_NEWMAIL_RECEIVED 和 NOTIFY_READTOSEND 对邮件存储提供程序有效。 以下标志对_ulFlags_参数有效: 
    
NOTIFY_CONFIG_CHANGE 
  
> 注册更改传输提供程序配置的请求。 
    
NOTIFY_CRITICAL_ERROR 
  
> 传输提供程序发生不可恢复的错误。 由于 NOTIFY_SENTDEFERRED 和 NOTIFY_CRITICAL_ERROR 将_lpvData_参数用于传输提供程序调用, 因此这些标志是互斥的。 
    
NOTIFY_CRITSEC 
  
> 请求传输提供程序的临界区。 _lpvData_参数未定义, 应为 NULL。 
    
NOTIFY_NEWMAIL 
  
> MAPI 后台处理程序应在下一个可用时间下载所有新近收到的邮件。 _lpvData_参数未定义, 应设置为 NULL。 
    
NOTIFY_NEWMAIL_RECEIVED 
  
> 邮件存储区中已收到新邮件。 _lpvData_参数指向描述邮件的[NEWMAIL_NOTIFICATION](newmail_notification.md)结构。 此标志用于与传输提供程序紧密结合的邮件存储提供程序, 如果存储提供程序使用 MAPI_NO_MAIL 标志集登录, 则将被忽略。 
    
NOTIFY_NONCRIT 
  
> 释放以前调用**SpoolerNotify**时获取的临界区, _ulFlags_设置为 NOTIFY_CRITSEC。 _lpvData_参数未定义, 应设置为 NULL。 
    
NOTIFY_READYTOSEND 
  
> 传输或邮件存储提供程序已准备好发送邮件。 _lpvData_参数未定义, 应设置为 NULL。 
    
NOTIFY_SENTDEFERRED 
  
> 应立即发送以前延迟的邮件, 并在可以通过调用[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md)方法来传递邮件时, 应通知传输提供程序。 延迟邮件的条目标识符包含在由_lpvData_指向的[SBinary](sbinary.md)结构中。 由于 NOTIFY_SENTDEFERRED 和 NOTIFY_CRITICAL_ERROR 都使用_lpvData_参数, 因此这些标志是互斥的。 
    
 _lpvData_
  
> 实时指向适用于通知的关联数据的指针。 仅当设置了以下标志时, _lpvData_参数才指向有效数据 (当_ulFlags_设置为其他通知类型时,_lpvData_为 NULL): 
    
|**_ulFlags_设置**|**_lpvData_值**|
|:-----|:-----|
|NOTIFY_CRITICAL_ERROR  <br/> |有关错误的信息。  <br/> |
|NOTIFY_NEWMAIL_RECEIVED  <br/> |包含有关新传递的邮件的信息的**NEWMAIL_NOTIFICATION**结构。  <br/> |
|NOTIFY_SENTDEFERRED  <br/> |包含延迟邮件的条目标识符的**SBinary**结构。  <br/> |
   
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
## <a name="remarks"></a>说明

为邮件存储和传输提供程序支持对象实现了**IMAPISupport:: SpoolerNotify**方法。 这些提供程序调用**SpoolerNotify**以通知 MAPI 后台处理程序的状态更改或服务请求。 **SpoolerNotify**主要由传输提供程序调用, 并可在会话期间的任何时间调用。 
  
## <a name="notes-to-transport-providers"></a>传输提供程序注意事项

如果你更改了传输提供程序配置, 请调用**SpoolerNotify**并将_ulFlags_设置为 NOTIFY_CONFIG_CHANGED。 **SpoolerNotify**通过调用[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法来查询受支持的地址类型中的更改, 从而做出响应。 
  
如果您需要一个临界区来确保不间断地进行处理, 请调用**SpoolerNotify** , 并将_ulFlags_设置为 NOTIFY_CRITSEC。 设置此标志将通知 MAPI 后台处理程序不应调用[IXPLogon:: Idle](ixplogon-idle.md) and [IXPLogon::P oll](ixplogon-poll.md)方法。 当您打开一个关键部分时, 请在调用[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法时返回 MAPI_E_BUSY。 完成 "临界" 部分后, 再次调用**SpoolerNotify** , 将_ulFlags_设置为 NOTIFY_NONCRIT。 
  
例如, 如果您的远程传输提供程序正在上载邮件, 则可能需要允许用户输入电话号码以建立远程连接。 在对话框过程中循环之前, 应声明一个临界区。 当用户关闭对话框时, 终止对话框过程, 应释放临界区。
  
当您将_ulFlags_设置为 NOTIFY_CRITICAL_ERROR 时, MAPI 后台处理程序将不会再对提供程序进行任何调用, 除非将其释放。 如果使用 NOTIFY_CRITICAL_ERROR ( [IXPLogon:: StartMessage](ixplogon-startmessage.md)或[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md)方法) 中的设置调用**SpoolerNotify** , 则会从**StartMessage**或 * * SubmitMessage * * 调用中返回适当的错误值紧跟在**SpoolerNotify**调用之后。 
  
如果您的传输提供程序从以前导致它失败的条件中恢复, 请调用**SpoolerNotify** with _ulFlags_设置为 NOTIFY_READYTOSEND。 此标志指示提供程序可再次准备好处理邮件。 
  
## <a name="notes-to-message-store-providers"></a>邮件存储提供程序注意事项

先调用**SpoolerNotify**, 在_ulFlags_中传递 NOTIFY_READYTOSEND 标志, 然后再调用 IMAPISupport: reparesubmit **:: IMessage**中的[:P SubmitMessage](imapisupport-preparesubmit.md) 。 对**SpoolerNotify**的此调用在每次会话中需要进行一次。 
  
如果您的邮件存储提供程序与传输提供程序紧密结合, 并且您调用**SpoolerNotify** _ulFlags_设置为 NOTIFY_NEWMAIL_RECEIVED, MAPI 后台处理程序将打开新邮件并开始处理新的邮件挂钩函数。 处理完成后, MAPI 后台处理程序将调用[IMsgStore:: NotifyNewMail](imsgstore-notifynewmail.md)方法来通知您自己的新邮件。 
  
有关调用**SpoolerNotify**的详细信息, 请参阅以下任一主题:
  
- [实现 FlushQueues 方法](implementing-the-flushqueues-method.md)
    
- [与 MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)
    
- [邮件接收模型](message-reception-model.md)
    
## <a name="see-also"></a>另请参阅



[IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)
  
[IXPLogon::StartMessage](ixplogon-startmessage.md)
  
[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

