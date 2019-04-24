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
  
向邮件存储提供程序注册对象, 以获取有关邮件存储区中的更改的通知。 然后, 邮件存储将发送有关已注册对象的更改的通知。
  
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
  
> 实时由_lpEntryID_参数指向的条目标识符的大小 (以字节为单位)。 
    
 _lpEntryID_
  
> 实时一个指针, 指向有关应生成其通知的对象的条目标识符。 该对象可以是文件夹、邮件或邮件存储区中的任何其他对象。 或者, 如果 MAPI 将_cbEntryID_参数设置为0并为_lpEntryID_传递**null** , 则建议接收器提供有关对整个邮件存储区所做更改的通知。
    
 _ulEventMask_
  
> 实时关于 MAPI 将生成通知的对象发生的通知事件类型的事件掩码。 掩码筛选特定事例。 每个事件类型都有一个与之相关联的结构, 其中包含有关事件的其他信息。 下表列出了可能的事件类型及其对应的结构。
    
|**通知事件类型**|**对应的结构**|
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
  
> 实时一个指针, 指向有关已请求其通知的 session 对象发生事件时要调用的通知接收器对象。 此建议接收器对象必须已经存在。
    
 _lpulConnection_
  
> 排除一个指向成功返回的变量的指针, 其中包含通知注册的连接号。 连接号码必须为非零值。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NO_SUPPORT 
  
> MAPI 或一个或多个服务提供商不支持该操作。
    
## <a name="remarks"></a>注解

邮件存储提供程序实现**IMSLogon:: Advise**方法, 以注册用于通知回调的对象。 每当指定的对象发生更改时, 提供程序都会检查在_ulEventMask_参数中设置了什么事件掩码位, 因此会发生更改的类型。 如果设置了一个位, 则提供程序将调用由_lpAdviseSink_参数指示的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 以报告事件。 通知结构中传递给**OnNotify**例程的数据描述了该事件。 
  
对**OnNotify**的调用可以在更改对象的调用过程中发生, 也可以在以后的任何时间进行。 在支持多个执行线程的系统上, 对**OnNotify**的调用可以出现在任何线程上。 若要安全地处理对可能在 inopportune 时可能发生的**OnNotify**的调用, 客户端应用程序应使用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数。 
  
若要提供通知, 实现**建议**的邮件存储提供程序需要将指针的副本保存到_lpAdviseSink_建议接收器对象;为执行此操作, 提供程序调用了通知接收器的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来维护其对象指针, 直到通过调用[IMSLogon:: Unadvise](imslogon-unadvise.md)方法取消通知注册。 **建议**实现应为通知注册分配一个连接号码, 并在此连接号码上调用**AddRef** , 然后再将其返回到_lpulConnection_参数中。 服务提供程序可以在取消注册之前释放通知接收器对象, 但在调用**Unadvise**之前, 服务提供程序不能释放连接号码。 
  
在对**建议**的调用成功之后和**Unadvise**调用之前, 必须为通知接收器对象准备好提供程序来释放通知。 因此, 提供程序应在**建议**返回后释放其建议接收器对象, 除非它对其具有特定的长期使用。 
  
有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMSLogon::Unadvise](imslogon-unadvise.md)
  
[NOTIFICATION](notification.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

