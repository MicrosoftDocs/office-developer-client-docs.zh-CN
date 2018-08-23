---
title: IMAPISessionAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.Advise
api_type:
- COM
ms.assetid: a6a6b6b1-31e2-4899-a5fe-74d5d1c2ccfc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 704a556b97f5fd90989641a17afe5a11d127e51b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577168"
---
# <a name="imapisessionadvise"></a>IMAPISession::Advise

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
注册接收影响会话的指定事件的通知。
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向通讯簿有关哪些应生成通知，消息存储对象或空值，指示客户端注册接收有关影响只对会话的事件通知的项标识符的指针。 
    
 _ulEventMask_
  
> [in]指示在客户端有兴趣和应包含在注册的通知事件的类型的值的掩码。 如果_lpEntryID_为 NULL，则 MAPI 自动注册影响只对会话的严重错误事件的客户端。 当_lpEntryID_指向条目标识符时，以下是有效值_ulEventMask_参数： 
    
fnevCriticalError 
  
> 有关严重错误，例如内存不足通知注册。
    
fnevExtended 
  
> 有关特定于特定的通讯簿或消息的事件通知的 register 存储提供程序和有关会话关闭。
    
fnevNewMail 
  
> 有关新邮件的到达通知注册。 
    
fnevObjectCreated 
  
> 有关创建新对象的通知的注册。
    
fnevObjectCopied
  
> 有关要复制的对象的通知的注册。
    
fnevObjectDeleted
  
> 有关对象正在删除通知的注册。
    
fnevObjectModified
  
> 有关修改对象的通知的注册。
    
fnevObjectMoved
  
> 有关被移动对象通知注册。
    
fnevSearchComplete
  
> 有关搜索操作完成通知注册。
    
 _lpAdviseSink_
  
> [in]指向要接收随后进行通知 advise 接收器对象的指针。 此 advise 接收器对象必须具有已分配。
    
 _lpulConnection_
  
> [输出]为非零值，该值代表呼叫者之间的连接数的指针建议接收器对象和会话。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注册成功。
    
MAPI_E_INVALID_ENTRYID 
  
> 由_lpEntryID_指向的项标识符不代表一个有效项标识符。 
    
MAPI_E_NO_SUPPORT 
  
> 负责所指的_lpEntryID_的项标识符的服务提供程序不支持的_ulEventMask_参数中指定的事件类型，或不支持通知。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 配置文件中的服务提供程序的任何无法处理由_lpEntryID_指向的项标识符。 
    
## <a name="remarks"></a>注解

**IMAPISession::Advise**方法建立呼叫者之间的连接的建议接收器对象，该会话和 （可选） 服务提供商。 此连接用于将通知发送到通知接收器一种或_ulEventMask_参数中指定的多个事件发生指向_lpEntryID_对象。 如果_lpEntryID_为 NULL，目标对象为会话，并仅为严重错误和扩展的事件发送通知。 
  
当_lpEntryID_指向有效项标识符时，MAPI 调用登录对象属于负责服务提供商的**Advise**方法。 例如，如果_lpEntryID_指向通讯组列表的项标识符，MAPI 将调用相应的通讯簿提供程序的[IABLogon::Advise](iablogon-advise.md)方法。 
  
发送通知，服务提供商或 MAPI 调用注册的通知接收器的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。 向**OnNotify**，通知结构参数之一包含介绍特定事件的信息。
  
## <a name="notes-to-callers"></a>给调用方的说明

支持多个线程的执行系统，在调用**OnNotify**也会发生任何线程上随时。 如果您需要保证通知会发生仅在特定时间上特定线程，调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数生成 advise 接收器对象传递给**Advise**方法。 
  
若要确定客户端已注销时，请通过_lpEntryID_设置为 NULL 和_cbEntryID_设置为 0 与调用**Advise**注册中服务提供商的通知。 注销发生时，您将收到 fnevExtended 通知。 
  
调用**Advise**已成功完成后，在调用[IMAPISession::Unadvise](imapisession-unadvise.md)取消注册之前，释放 advise 接收器对象，除非您有特定的长期使用它。 
  
通知过程的概述，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
有关处理通知的详细信息，请参阅[处理通知](handling-notifications.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|BaseDialog.cpp  <br/> |CBaseDialog::OnNotificationsOn  <br/> |MFCMAPI 使用**IMAPISession::Advise**方法注册针对会话的通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IABLogon::Advise](iablogon-advise.md)
  
[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISession::Unadvise](imapisession-unadvise.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 中的事件通知](event-notification-in-mapi.md)

