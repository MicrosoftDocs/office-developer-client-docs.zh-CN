---
title: IMsgStoreAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.Advise
api_type:
- COM
ms.assetid: 8c57e743-a798-4e39-a61a-46dff8b1ac7c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ddd9d3c0a61a3a2a585edd6c370285b2f6d424e3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593716"
---
# <a name="imsgstoreadvise"></a>IMsgStore::Advise

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
注册接收影响消息存储库的指定事件的通知。
  
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
  
> [in]指向有关应生成的通知，则为**null**的邮件的文件夹的项标识符的指针。 如果_lpEntryID_设置为 NULL， **Advise**注册整个邮件存储区上的通知。 
    
 _ulEventMask_
  
> [in]指示呼叫者感兴趣，并应包含在注册通知事件的类型的值的掩码。 没有相应的[通知](notification.md)结构，每种类型的包含有关事件的信息的事件相关联。 _UlEventMask_参数的有效值如下： 
    
 _fnevCriticalError_
  
> 有关严重错误，例如内存不足通知注册。
    
 _fnevExtended_
  
> 有关特定于特定邮件的事件通知的 register 存储提供程序。
    
 _fnevNewMail_
  
> 有关新邮件的到达通知注册。 
    
 _fnevObjectCreated_
  
> 有关创建新文件夹或消息的通知的注册。
    
 _fnevObjectCopied_
  
> 有关文件夹或复制的消息的通知的注册。
    
 _fnevObjectDeleted_
  
> 有关文件夹或正在删除的消息的通知的注册。
    
 _fnevObjectModified_
  
> 有关文件夹或要修改的消息的通知的注册。
    
 _fnevObjectMoved_
  
> 有关文件夹或要移动的消息的通知的注册。
    
 _fnevSearchComplete_
  
> 有关搜索操作完成通知注册。
    
 _lpAdviseSink_
  
> [in]指向要接收随后进行通知 advise 接收器对象的指针。 此 advise 接收器对象必须具有已分配。
    
 _lpulConnection_
  
> [输出]为非零值，该值代表呼叫者之间的连接数的指针建议接收器对象和会话。 
    
 _lpAdviseSink_
  
> [in]指向要接收随后进行通知 advise 接收器对象的指针。 此 advise 接收器对象必须具有已分配。 
    
 _lpulConnection_
  
> [输出]为非零值的连接数表示呼叫者之间的连接的指针建议接收器对象和消息存储。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注册成功。
    
MAPI_E_NO_SUPPORT 
  
> 消息存储提供程序不支持的通知消息存储通过注册。
    
## <a name="remarks"></a>注解

**IMsgStore::Advise**方法建立呼叫者之间的连接的建议接收器对象和消息存储库或消息存储库中的对象。 此连接用于将通知发送到通知接收器当一个或多个事件， _ulEventMask_参数中指定发生 advise 源对象。 当_lpEntryID_参数指向的有效条目标识符，advise 源是由此条目标识符标识的对象。 _LpEntryID_为 NULL，advise 源时消息存储库。 
  
发送通知，消息存储提供程序或 MAPI 调用注册的通知接收器的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。 向**OnNotify**，通知结构参数之一包含介绍特定事件的信息。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

您可以支持使用或不从 MAPI 帮助的通知。 MAPI 具有三个帮助服务提供商实现通知的支持对象方法： [IMAPISupport::Subscribe](imapisupport-subscribe.md)、 [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)和[IMAPISupport::Notify](imapisupport-notify.md)。 如果您选择使用 MAPI 支持方法，调用**Advise**方法时调用**Subscribe**和释放_lpAdviseSink_指针。 
  
如果您选择自己支持通知，呼叫通知接收器由_lpAdviseSink_参数保留一份此指针的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)方法。 维护此副本，直到您[IMsgStore::Unadvise](imsgstore-unadvise.md)方法调用取消注册。 
  
无论如何支持通知，分配给通知注册的非零值的连接数并返回_lpulConnection_参数中。 直到**Unadvise**已调用，并且已完成，则不释放此连接数。 
  
## <a name="notes-to-callers"></a>给调用方的说明

支持多个线程的执行系统，在调用**OnNotify**也会发生任何线程上随时。 如果您必须确保仅在特定时间在特定的线程上发生通知，调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数生成传递给**Advise**advise 接收器对象。 
  
后调用**Advise**已经完成并且在调用**Unadvise**取消注册之前，先为 advise 接收器对象，必须释放准备。 **Advise**返回除非您有特定的长期使用为其后，您应释放 advise 接收器对象。 
  
有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
有关处理通知的详细信息，请参阅[处理通知](handling-notifications.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|BaseDialog.cpp  <br/> |CBaseDialog::OnNotificationsOn  <br/> |MFCMAPI 使用**IMsgStore::Advise**方法注册整个邮件存储区上的通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMsgStore::Unadvise](imsgstore-unadvise.md)
  
[通知](notification.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

