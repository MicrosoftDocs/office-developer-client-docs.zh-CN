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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382755"
---
# <a name="imslogonadvise"></a>IMSLogon::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用有关邮件存储区中的更改的通知的消息存储提供程序注册的对象。 消息存储然后将对注册对象发送有关更改的通知。
  
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
  
> [in]以字节为单位_lpEntryID_参数指向的项标识符的大小。 
    
 _lpEntryID_
  
> [in]指向有关哪些应生成通知的对象的项标识符的指针。 此对象可以是一个文件夹、 一条消息或消息存储库中的任何其他对象。 此外，如果 MAPI 将_cbEntryID_参数设置为 0，并传递**null** _lpEntryID_，通知接收器提供了有关对整个邮件存储的更改的通知。
    
 _ulEventMask_
  
> [in]有关哪些 MAPI 会生成通知的对象出现通知事件的类型的事件掩码。 掩码筛选特定情况。 每个事件类型都有与之关联的结构，其中包含有关事件的其他信息。 下表列出了可能的事件类型以及它们对应的结构。
    
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
  
> [in]指向有关哪些请求通知会话对象发生事件时调用 advise 接收器对象的指针。 此 advise 接收器对象必须已经存在。
    
 _lpulConnection_
  
> [输出]指向的成功返回时保留通知注册的连接数变量的指针。 连接数必须非零值。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NO_SUPPORT 
  
> 通过 MAPI 或一个或多个服务提供程序不支持此操作。
    
## <a name="remarks"></a>说明

消息存储提供程序实现**IMSLogon::Advise**方法注册通知回调对象。 当指定对象发生更改时，提供程序检查哪些事件掩码位设置_ulEventMask_参数中，因此，发生更改的类型。 如果设置了位，提供程序由_lpAdviseSink_参数来报告事件 advise 接收器对象调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。 数据传递给**OnNotify**例程通知结构中介绍的事件。 
  
更改该对象，该调用期间或任何更高版本时，可能会发生**OnNotify**调用。 支持多个线程的执行系统，在调用**OnNotify**可以发生任何线程上。 若要安全地处理**OnNotify**可能发生在时机的调用，客户端应用程序应使用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数。 
  
若要提供通知，实现**Advise**需要保持_lpAdviseSink_指针的副本的消息存储提供程序告知接收器对象;为此，请提供程序，请调用通知接收器来维护其对象的指针，直到[IMSLogon::Unadvise](imslogon-unadvise.md)方法的调用被取消通知注册的[IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法。 **Advise**实现应分配的通知注册的连接数并返回_lpulConnection_参数中之前调用此连接号码**AddRef** 。 服务提供商可以释放 advise 接收器对象之前注册被取消，但他们必须在被调用**Unadvise**之前不释放连接数。 
  
调用**Advise**已成功完成后，在调用**Unadvise**之前，必须先为 advise 接收器对象，必须释放准备提供程序。 因此，提供程序应释放其 advise 接收器对象后**Advise**返回，除非它具有特定的长期使用它。 
  
有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMSLogon::Unadvise](imslogon-unadvise.md)
  
[NOTIFICATION](notification.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

