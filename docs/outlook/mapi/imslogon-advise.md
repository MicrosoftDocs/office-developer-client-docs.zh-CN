---
title: IMSLogonAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.Advise
api_type:
- COM
ms.assetid: a3c5d937-642b-463b-b5a0-5d099e651895
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: abe4867b965f05e781f931d2e72920474d007d78
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317309"
---
# <a name="imslogonadvise"></a>IMSLogon::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
向邮件存储提供程序注册对象，以接收有关邮件存储中更改的通知。 然后，邮件存储将发送有关已注册对象的更改的通知。
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符的大小（以字节为单位）。 
    
 _lpEntryID_
  
> [in]指向应生成通知的对象的条目标识符的指针。 此对象可以是邮件存储中的文件夹、邮件或其他任何对象。 或者，如果 MAPI _将 cbEntryID_ 参数设置为 0，并传递 _lpEntryID_ 的 **null，** 则通知接收器提供有关整个邮件存储更改的通知。
    
 _ulEventMask_
  
> [in]针对将生成通知的对象发生的通知类型的事件掩码。 掩码筛选特定的情况。 每个事件类型都有一个与之关联的结构，其中包含有关事件的其他信息。 下表列出了可能的事件类型及其相应的结构。
    
|**通知事件类型**|**相应的结构**|
|:-----|:-----|
|fnevCriticalError  <br/> |[ERROR_NOTIFICATION](error_notification.md) <br/> |
|fnevNewMail  <br/> |[NEWMAIL_NOTIFICATION](newmail_notification.md) <br/> |
|fnevObjectCreated  <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|fnevObjectDeleted  <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|fnevObjectModified  <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|fnevObjectCopied  <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|fnevObjectMoved  <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|fnevSearchComplete  <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|fnevStatusObjectModified  <br/> |[STATUS_OBJECT_NOTIFICATION](status_object_notification.md) <br/> |
   
 _lpAdviseSink_
  
> [in]指向通知接收器对象的指针，当会话对象发生有关已请求通知的事件时，将调用该对象。 此通知接收器对象必须已经存在。
    
 _lpulConnection_
  
> [out]指向成功返回时保留通知注册的连接号的变量的指针。 连接号必须为非零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_NO_SUPPORT 
  
> MAPI 或一个或多个服务提供商不支持该操作。
    
## <a name="remarks"></a>备注

消息存储提供程序实现 **IMSLogon：：Advise** 方法以注册用于通知回调的对象。 只要对指示的对象发生了更改，提供程序就会检查在  _ulEventMask_ 参数中设置了哪些事件掩码位，因此还检查发生了哪种类型的更改。 如果设置了位，提供程序将调用 _由 lpAdviseSink_ 参数指示的建议接收器对象的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法以报告事件。 在通知结构中传递给 **OnNotify** 例程的数据描述事件。 
  
调用 **OnNotify** 可能会发生在更改对象的调用过程中，或稍后的任何时间。 在支持多个执行线程的系统上，对 **OnNotify** 的调用可以在任何线程上发生。 为了安全地处理在不及时发生的 **OnNotify** 调用，客户端应用程序应该使用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数。 
  
若要提供通知，实现 **Advise** 的邮件存储提供程序需要保留指向  _lpAdviseSink_ advise 接收器对象的指针的副本;为此，提供程序调用通知接收器的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) 方法，以维护其对象指针，直到通过调用 [IMSLogon：：Unadvise](imslogon-unadvise.md) 方法取消通知注册。 Advise 实现应为通知注册分配一个连接号码，并在此连接号码上调用 **AddRef，** 然后再在 _lpulConnection_ 参数中返回它。 服务提供商可以在取消注册之前释放通知接收器对象，但在调用 **Unadvise** 之前，它们不得释放连接号。 
  
在成功调用 **Advise** 之后，在调用 **Unadvise** 之前，必须为通知接收器对象发布做好准备。 因此，提供程序应在 Advise 返回后释放其 **advise** sink 对象，除非它具有特定的长期用途。 
  
有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMSLogon::Unadvise](imslogon-unadvise.md)
  
[NOTIFICATION](notification.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

