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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407359"
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
  
> [in]_lpNotifications_ 参数指向的 [NOTIFICATION](notification.md)结构计数。 
    
 _lpNotifications_
  
> [in]指向一个或多个 **NOTIFICATION** 结构的指针，该结构提供有关已发生事件的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功处理。
    
## <a name="remarks"></a>备注

当客户端或 MAPI 调用服务提供商的 **Advise** 方法以注册以接收特定对象的特定类型通知时，通知过程将启动。 **Advise** 方法的参数之一是指向实现 [IMAPIAdviseSink](imapiadvisesinkiunknown.md)接口的 advise 接收器对象的指针。 当对应于已注册的通知的目标对象发生事件时，服务提供商会直接或间接通过 MAPI 调用通知接收器 **的 OnNotify** 方法。 
  
对 **OnNotify** 的调用可以在导致事件的 MAPI 调用期间或稍后发生。 在支持多个执行线程的系统上，可以在用于注册的同一线程上或其他线程上调用 **OnNotify。** 客户端可以通过创建使用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数传递给 **Advise** 的建议接收器，确保在用于调用 **Advise** 的同一线程上执行 **OnNotify** 调用。 
  
_lpNotifications_ 参数指向一个或多个 **NOTIFICATION** 结构，用于描述事件期间发生了哪些变化。 每种事件类型都有不同类型的 **NOTIFICATION** 结构。 
  
下表列出了用于表示可能类型的事件的值以及与每个值关联的结构：
  
|**通知事件类型**|**相应的结构**|
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
   
若要详细了解如何设置和停止通知，请参阅以下任一接口的 **Advise** 和 **Unadvise** 方法的参考条目：IABLogon、IAddrBook、IMAPIForm、IMAPISession、IMAPITable、IMsgStore [](imsgstoreimapiprop.md)和 [](imapisessioniunknown.md)[](iaddrbookimapiprop.md)[IMSLogon。](imslogoniunknown.md) [](iablogoniunknown.md) [](imapiformiunknown.md) [](imapitableiunknown.md) 
  
有关通知过程的常规信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

**OnNotify** 实现通常包含预期接收的每种类型的通知的一个或多个代码块。 在这些代码块内，执行你认为作为通知响应所必需的任何任务。 例如，假设您注册以接收对话框显示中包括的文件夹上的 **fnevObjectModified** 通知。 在 **OnNotify** 方法中用于处理 **fnevObjectModified** 通知的代码块中，你可以向对话框发送 Windows 消息以请求更新的显示。 
  
不要修改或释放传递给 **OnNotify** 的 **NOTIFICATION** 结构。 结构中的数据仅在 **OnNotify 返回之前有效** 。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当对多个对象进行更改时，您可以通知注册的通知接收器，该通知接收在 **OnNotify** 的单个调用中或根据内存限制的多个调用中。 无论更改是一个方法调用还是多个方法调用的结果，都是如此。 例如，对 [IMAPIFolder：：CopyMessages](imapifolder-copymessages.md) 的调用可能会影响多个邮件和文件夹。 作为邮件存储提供程序，可以使用目标文件夹的 **fnevObjectModified** 事件类型对 **OnNotify** 进行一次调用，或多次调用，每个调用一个影响邮件。 同样，如果客户端对 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md)进行重复调用，这些调用可以组合到文件夹的一个 **fnevObjectModified** 事件，也可以分隔为每个新邮件的单个 **fnevObjectCreated** 事件。 
  
若要详细了解如何以及何时生成通知，请参阅 [MAPI](event-notification-in-mapi.md) 中的事件通知 [和支持事件通知](supporting-event-notification.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|AdviseSink.h 和 AdviseSink.cpp  <br/> |CAdviseSink：：OnNotifyDesc  <br/> |实现 CAdviseSink 类以处理 MFCMAPI 中的所有通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[HrAllocAdviseSink](hrallocadvisesink.md)
  
[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPISupport::Notify](imapisupport-notify.md)
  
[NOTIFICATION](notification.md)
  
[IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

