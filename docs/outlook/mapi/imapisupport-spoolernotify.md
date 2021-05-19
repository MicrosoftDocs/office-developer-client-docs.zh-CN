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
  
通知 MAPI 后台处理程序状态更改或服务请求。 
  
```cpp
HRESULT SpoolerNotify(
ULONG ulFlags,
LPVOID lpvData
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]指示通知类型的标志位掩码。 传输提供程序可以设置除其他所有标志NOTIFY_NEWMAIL_RECEIVED;只有 NOTIFY_NEWMAIL_RECEIVED 和 NOTIFY_READTOSEND 对邮件存储提供程序有效。 以下标志对  _ulFlags_ 参数有效： 
    
NOTIFY_CONFIG_CHANGE 
  
> 注册更改传输提供程序配置的请求。 
    
NOTIFY_CRITICAL_ERROR 
  
> 传输提供程序发生了不可恢复的错误。 由于NOTIFY_SENTDEFERRED和NOTIFY_CRITICAL_ERROR都使用  _lpvData_ 参数进行传输提供程序调用，因此这些标志是互斥的。 
    
NOTIFY_CRITSEC 
  
> 请求传输提供程序的关键部分。 _lpvData_ 参数未定义，应为 NULL。 
    
NOTIFY_NEWMAIL 
  
> MAPI 后台处理程序应在下一个可用时间下载任何新收到的消息。 _lpvData_ 参数未定义，应设置为 NULL。 
    
NOTIFY_NEWMAIL_RECEIVED 
  
> 已在邮件存储中收到新邮件。 _lpvData_ 参数指向一 [个NEWMAIL_NOTIFICATION](newmail_notification.md)消息的变量结构。 此标志用于与传输提供程序紧密结合的邮件存储提供程序，如果存储提供程序使用设置的邮件存储MAPI_NO_MAIL忽略。 
    
NOTIFY_NONCRIT 
  
> 释放上一次调用 **SpoolerNotify** 时获取的关键节  _，ulFlags_ 设置为 NOTIFY_CRITSEC。 _lpvData_ 参数未定义，应设置为 NULL。 
    
NOTIFY_READYTOSEND 
  
> 传输或邮件存储提供程序已准备好发送邮件。 _lpvData_ 参数未定义，应设置为 NULL。 
    
NOTIFY_SENTDEFERRED 
  
> 现在应发送以前延迟的邮件，并且应在准备好使用 [IXPLogon：：SubmitMessage](ixplogon-submitmessage.md) 方法传递邮件时通知传输提供程序。 延迟邮件的条目标识符包含在 _lpvData_ 指向的 [SBinary](sbinary.md)结构中。 由于 NOTIFY_SENTDEFERRED 和 NOTIFY_CRITICAL_ERROR都使用  _lpvData_ 参数，因此这些标志是互斥的。 
    
 _lpvData_
  
> [in]指向适用于通知的关联数据的指针。 _只有在将 ulFlags_ 设置为其他通知类型时，lpvData 参数才 (设置为 NULL 时 _，lpvData_ 参数才指向有效) ：  
    
|**_ulFlags_ 设置**|**_lpvData_ 值**|
|:-----|:-----|
|NOTIFY_CRITICAL_ERROR  <br/> |有关错误的信息。  <br/> |
|NOTIFY_NEWMAIL_RECEIVED  <br/> |一 **NEWMAIL_NOTIFICATION** 包含有关新传递的邮件的信息的一个安全结构。  <br/> |
|NOTIFY_SENTDEFERRED  <br/> |包含延迟邮件的条目标识符的 **SBinary** 结构。  <br/> |
   
## <a name="return-value"></a>返回值

S_OK 
  
> 通知成功。
    
## <a name="remarks"></a>备注

**IMAPISupport：：SpoolerNotify** 方法为邮件存储和传输提供程序支持对象实现。 这些提供程序调用 **SpoolerNotify** 以通知 MAPI 后台处理程序状态更改或服务请求。 **SpoolerNotify** 主要由传输提供程序调用，并且可能在会话期间随时调用。 
  
## <a name="notes-to-transport-providers"></a>对传输提供程序的注释

如果已更改传输提供程序配置，请调用 **SpoolerNotify，** 将  _ulFlags_ 设置为 NOTIFY_CONFIG_CHANGED。 **SpoolerNotify** 通过调用 [IXPLogon：：AddressTypes](ixplogon-addresstypes.md) 方法来查询受支持的地址类型中的更改来做出响应。 
  
如果需要一个关键部分以确保不中断处理，请调用 **SpoolerNotify，** 将  _ulFlags_ 设置为 NOTIFY_CRITSEC。 设置此标志将通知 MAPI 后台处理程序不应调用 [IXPLogon：：Idle](ixplogon-idle.md) 和 [IXPLogon：:P oll](ixplogon-poll.md) 方法。 在打开关键节时，每当MAPI_E_BUSY [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法时，都会返回一个返回值。 完成关键部分后，请再次调用 **SpoolerNotify，** 将  _ulFlags_ 设置为 NOTIFY_NONCRIT。 
  
例如，如果您的远程传输提供商正在上载邮件，您可能需要允许用户输入电话号码以建立远程连接。 在循环访问对话框过程之前，应声明一个关键部分。 当用户关闭对话框并终止对话框过程时，应释放关键部分。
  
将  _ulFlags_ 设置为 NOTIFY_CRITICAL_ERROR时，MAPI 后台处理程序不会进一步调用提供程序，除非释放它。 如果使用 [IXPLogon：：StartMessage](ixplogon-startmessage.md)或 [IXPLogon：：SubmitMessage](ixplogon-submitmessage.md)方法中设置的 NOTIFY_CRITICAL_ERROR 调用 **SpoolerNotify，** 则返回 **SpoolerNotify** 调用后立即 **从 StartMessage** 或 ** SubmitMessage ** 调用中返回相应的错误值。 
  
如果传输提供程序从之前导致其失败的条件中恢复，请调用 **spoolerNotify，** 将  _ulFlags_ 设置为 NOTIFY_READYTOSEND。 此标志指示提供程序已再次准备好处理邮件。 
  
## <a name="notes-to-message-store-providers"></a>邮件存储提供程序说明

调用 **SpoolerNotify**，在 _ulFlags_ 中传递 NOTIFY_READYTOSEND 标志，然后再在 **IMessage：：SubmitMessage** 中首次调用 [IMAPISupport：:P repareSubmit。](imapisupport-preparesubmit.md) 每个会话 **只需调用一次 SpoolerNotify。** 
  
如果邮件存储提供程序与传输提供程序紧密结合，并且调用 **SpoolerNotify** 且  _ulFlags_ 设置为 NOTIFY_NEWMAIL_RECEIVED，则 MAPI 后台处理程序将打开新邮件并开始处理新邮件挂钩函数。 处理完成后，MAPI 后台处理程序将调用 [IMsgStore：：NotifyNewMail](imsgstore-notifynewmail.md) 方法，以通知您自己的新邮件。 
  
有关调用 **SpoolerNotify 的信息，** 请参阅以下任何主题：
  
- [实现 FlushQueues 方法](implementing-the-flushqueues-method.md)
    
- [与 MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)
    
- [邮件接收模型](message-reception-model.md)
    
## <a name="see-also"></a>另请参阅



[IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)
  
[IXPLogon::StartMessage](ixplogon-startmessage.md)
  
[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

