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
ms.openlocfilehash: 3b4abef731541e308b2c2ebc6f4aaddf4458e257
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317323"
---
# <a name="imsgstoreadvise"></a>IMsgStore::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册以接收影响邮件存储的指定事件的通知。
  
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
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向有关应生成通知的文件夹或邮件的条目标识符的指针，或 **null**。 如果  _lpEntryID_ 设置为 NULL， **则 Advise** 将注册整个邮件存储上的通知。 
    
 _ulEventMask_
  
> [in]指示调用方感兴趣的通知事件类型且应包含在注册中的值的掩码。 有一个与 [每种](notification.md) 事件类型关联的相应 NOTIFICATION 结构，用于保存有关事件的信息。 以下是  _ulEventMask_ 参数的有效值： 
    
 _fnevCriticalError_
  
> 注册有关严重错误（如内存不足）的通知。
    
 _fnevExtended_
  
> 注册有关特定于特定邮件存储提供程序的事件的通知。
    
 _fnevNewMail_
  
> 注册有关新邮件到达的通知。 
    
 _fnevObjectCreated_
  
> 注册有关新建文件夹或邮件的通知。
    
 _fnevObjectCopied_
  
> 注册有关要复制的文件夹或邮件的通知。
    
 _fnevObjectDeleted_
  
> 注册有关要删除的文件夹或邮件的通知。
    
 _fnevObjectModified_
  
> 注册有关要修改的文件夹或邮件的通知。
    
 _fnevObjectMoved_
  
> 注册有关要移动的文件夹或邮件的通知。
    
 _fnevSearchComplete_
  
> 注册有关搜索操作完成的通知。
    
 _lpAdviseSink_
  
> [in]指向通知接收接收对象以接收后续通知的指针。 此通知接收器对象必须已分配。
    
 _lpulConnection_
  
> [out]指向非零数字的指针，该数字代表呼叫者的建议接收对象和会话之间的连接。 
    
 _lpAdviseSink_
  
> [in]指向通知接收接收对象以接收后续通知的指针。 此通知接收器对象必须已分配。 
    
 _lpulConnection_
  
> [out]指向非零连接号的指针，该连接号代表呼叫者的建议接收对象与消息存储之间的连接。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注册成功。
    
MAPI_E_NO_SUPPORT 
  
> 邮件存储提供程序不支持通过邮件存储注册通知。
    
## <a name="remarks"></a>备注

**IMsgStore：：Advise** 方法在调用方的 advise 接收器对象与邮件存储或邮件存储中的对象之间建立连接。 当通知源对象发生  _ulEventMask_ 参数中指定的一个或多个事件时，此连接用于向通知接收器发送通知。 当  _lpEntryID_ 参数指向有效的条目标识符时，建议源是此条目标识符标识的对象。 当  _lpEntryID 为_ NULL 时，建议源是邮件存储。 
  
若要发送通知，消息存储提供程序或 MAPI 调用注册的通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法。 通知结构 **OnNotify** 的参数之一包含描述特定事件的信息。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在 MAPI 的帮助下，你都可以支持通知，也可以不提供帮助。 MAPI 具有三种支持对象方法，用于帮助服务提供商实现通知[：IMAPISupport：：Subscribe、IMAPISupport：：Unsubscribe](imapisupport-subscribe.md)和[IMAPISupport：：Notify](imapisupport-notify.md)。 [](imapisupport-unsubscribe.md) 如果选择使用 MAPI 支持方法，在 **调用 Advise** 方法时调用 **Subscribe** 并释放 _lpAdviseSink_ 指针。 
  
如果选择自己支持通知，请调用 _由 lpAdviseSink_ 参数表示的建议接收器的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法，以保留此指针的副本。 保留此副本，直到 [调用 IMsgStore：：Unadvise](imsgstore-unadvise.md) 方法来取消注册。 
  
无论您如何支持通知，都将非零连接号分配给通知注册，并将其返回到  _lpulConnection_ 参数中。 在调用 **Unadvise** 并完成之前，不要释放此连接号。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在支持多个执行线程的系统上， **对 OnNotify** 的调用也随时可以在任何线程上发生。 如果必须确保通知仅在特定线程上的某个特定时间发生，请调用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数以生成传递给 Advise 的建议接收器 **对象**。 
  
在成功调用 **Advise** 之后，在调用 **Unadvise** 以取消注册之前，请准备通知接收器对象以释放。 在 Advise 返回后，您应释放通知接收器对象，除非您具有特定的长期用途。 
  
有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
有关处理通知的信息，请参阅处理 [通知](handling-notifications.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|BaseDialog.cpp  <br/> |CBaseDialog：：OnNotificationsOn  <br/> |MFCMAPI 使用 **IMsgStore：：Advise** 方法注册整个邮件存储上的通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMsgStore::Unadvise](imsgstore-unadvise.md)
  
[NOTIFICATION](notification.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

