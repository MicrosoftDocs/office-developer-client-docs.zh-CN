---
title: IMAPIAdviseSinkOnNotify
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIAdviseSink.OnNotify
api_type:
- COM
ms.assetid: 9eec90d3-2369-4340-86ed-0efa58918ed5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5983ed3229f6b0053f15a614116cf5680e942587
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351441"
---
# <a name="imapiadvisesinkonnotify"></a>IMAPIAdviseSink::OnNotify

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过执行一个或多个任务来响应通知。 执行的任务取决于事件的类型和生成通知的对象。 
  
```cpp
ULONG OnNotify(
  ULONG cNotif,
  LPNOTIFICATION lpNotifications
);
```

## <a name="parameters"></a>参数

 _cNotif_
  
> 实时由_lpNotifications_参数指向的[通知](notification.md)结构的计数。 
    
 _lpNotifications_
  
> 实时指向一个或多个通知结构的指针, 这些**通知**结构提供有关已发生事件的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功处理通知。
    
## <a name="remarks"></a>注解

当客户端或 MAPI 对服务提供商的**建议**方法进行注册以接收特定对象的特定类型通知时, 将启动通知过程。 **advise**方法的一个参数是指向实现[IMAPIAdviseSink](imapiadvisesinkiunknown.md)接口的通知接收器对象的指针。 当与已注册的通知相对应的目标对象发生事件时, 服务提供程序可以通过 MAPI 直接或间接地调用通知接收器的**OnNotify**方法。 
  
对**OnNotify**的调用可能发生在导致事件的 MAPI 调用过程中或稍后某个时候。 在支持多个执行线程的系统上, 可以在用于注册的同一线程或在不同的线程上调用**OnNotify** 。 客户端可以通过创建其传递给**建议**使用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数的通知接收器来确保对用于呼叫**通知**的同一线程进行**OnNotify**调用。 
  
_lpNotifications_参数指向一个或多个**通知**结构, 用于描述事件过程中发生了更改的内容。 每种类型的事件都有不同类型的**通知**结构。 
  
下表列出了用于表示可能的事件类型的值, 以及与每个值关联的结构:
  
|**通知事件类型**|**对应的结构**|
|:-----|:-----|
|**fnevCriticalError** <br/> |[ERROR_NOTIFICATION](error_notification.md) <br/> |
|**fnevNewMail** <br/> |[NEWMAIL_NOTIFICATION](newmail_notification.md) <br/> |
|**fnevObjectCreated** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectDeleted** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectModified** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectCopied** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevSearchComplete** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevTableModified** <br/> |[TABLE_NOTIFICATION](table_notification.md) <br/> |
|**fnevStatusObjectModified** <br/> |[STATUS_OBJECT_NOTIFICATION](status_object_notification.md) <br/> |
|**fnevExtended** <br/> |[EXTENDED_NOTIFICATION](extended_notification.md) <br/> |
   
有关如何设置和停止通知的详细信息, 请参阅适用于以下任何接口的**Advise**和**Unadvise**方法的引用条目: [IABLogon](iablogoniunknown.md)、 [IAddrBook](iaddrbookimapiprop.md)、 [IMAPIForm](imapiformiunknown.md)、 [IMAPISession](imapisessioniunknown.md)、 [IMAPITable](imapitableiunknown.md)、 [IMsgStore](imsgstoreimapiprop.md)和[IMSLogon](imslogoniunknown.md)。 
  
有关通知过程的一般信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您的**OnNotify**实现通常由您预期收到的每种类型的通知的一个或多个代码块组成。 在这些代码块中, 执行您认为是对通知的响应所需的任何任务。 例如, 假设您注册接收在对话框显示中包含的文件夹上的**fnevObjectModified**通知。 在**OnNotify**方法中包含的代码块中, 若要处理**fnevObjectModified**通知, 您可能会将 Windows 消息发送到对话框, 以请求更新的显示。 
  
请勿修改或释放传递给**OnNotify**的**通知**结构。 结构中的数据仅在**OnNotify**返回之前有效。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当多个对象发生更改时, 您可以在对**OnNotify**或多个调用中的一次调用中通知已注册的通知接收器, 具体取决于内存约束。 无论更改是一个方法调用的结果还是多个, 都是如此。 例如, 对[IMAPIFolder:: CopyMessages](imapifolder-copymessages.md)的调用可能会影响多个邮件和文件夹。 作为邮件存储提供程序, 您可以使用目标文件夹的**fnevObjectModified**事件类型或多个调用 (一个针对每个邮件的影响) 对**OnNotify**调用一个调用。 同样, 如果客户端再次调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md), 则这些调用可以合并到文件夹的一个**fnevObjectModified**事件中, 也可以分隔到每个新邮件的单个**fnevObjectCreated**事件中。 
  
有关如何以及何时生成通知的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[支持事件通知](supporting-event-notification.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|AdviseSink 和 AdviseSink  <br/> |CAdviseSink:: OnNotifyDesc  <br/> |实现 CAdviseSink 类以处理 MFCMAPI 中的所有通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[HrAllocAdviseSink](hrallocadvisesink.md)
  
[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPISupport::Notify](imapisupport-notify.md)
  
[NOTIFICATION](notification.md)
  
[IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

