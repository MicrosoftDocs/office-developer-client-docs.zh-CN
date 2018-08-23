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
ms.openlocfilehash: d052e7590ee502b55f2076d698587ab68820ca56
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576699"
---
# <a name="imapiadvisesinkonnotify"></a>IMAPIAdviseSink::OnNotify

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
通过执行一个或多个任务响应通知。 执行的任务取决于事件以及生成通知的对象类型。 
  
```cpp
ULONG OnNotify(
  ULONG cNotif,
  LPNOTIFICATION lpNotifications
);
```

## <a name="parameters"></a>参数

 _cNotif_
  
> [in][通知](notification.md)结构_lpNotifications_参数指向的计数。 
    
 _lpNotifications_
  
> [in]一个指向一个或多个**通知**结构，并提供有关发生的事件的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功处理。
    
## <a name="remarks"></a>注解

当客户端或 MAPI 服务提供商的**Advise**方法的调用，以注册，以接收通知的特定对象的特定类型时，将启动通知过程。 **Advise**方法的参数之一是指向实现[IMAPIAdviseSink](imapiadvisesinkiunknown.md)接口 advise 接收器对象的指针。 对目标对象对应于已注册的通知中，服务提供商，直接或间接通过 MAPI，事件发生时调用通知接收器**OnNotify**方法。 
  
MAPI 呼叫导致该事件期间，也可以在某些更高版本时，会发生**OnNotify**调用。 在系统上支持多个线程的执行， **OnNotify**可在同一线程了用于注册或在不同线程上调用。 客户端可以确保**OnNotify**呼叫由用于通过创建它们与[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数传递给**Advise**通知接收器调用**Advise**对同一线程。 
  
_LpNotifications_参数指向介绍事件过程中更改内容的一个或多个**通知**结构。 没有其他类型的每种类型的事件**通知**结构。 
  
下表列出了用于表示可能的事件和与每个值的结构类型的值：
  
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
   
有关如何设置和停止通知的详细信息，请参阅以下接口的任何**Advise**和**Unadvise**方法的参考条目： [IABLogon](iablogoniunknown.md) [IAddrBook](iaddrbookimapiprop.md)、 [IMAPIForm](imapiformiunknown.md)、 [IMAPISession](imapisessioniunknown.md)， [IMAPITable](imapitableiunknown.md)、 [IMsgStore](imsgstoreimapiprop.md)和[IMSLogon](imslogoniunknown.md)。 
  
有关通知过程的一般信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

**OnNotify**实现通常包含一个或多个您希望接收的通知的每种类型的代码块。 这些的代码块内, 执行考虑作为对通知的响应所需的任何任务。 例如，假设您注册，以接收**fnevObjectModified**通知中显示一个对话框，包含的文件夹。 在包含在**OnNotify**方法来处理**fnevObjectModified**通知中的代码块中，您可能向对话框以请求更新的显示发送 Windows 消息。 
  
无法修改或释放传递给**OnNotify****通知**结构。 仅**OnNotify**返回之前，结构中的数据有效。 
  
## <a name="notes-to-callers"></a>给调用方的说明

与多个对象更改时，您可以通知或多个呼叫，具体取决于内存限制对**OnNotify**的单个调用中注册的通知接收器。 这种情况而不考虑所做的更改是否是一个方法调用或多个结果。 例如，对[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)调用可影响多个邮件和文件夹。 为消息存储提供程序，您可以一次调用**OnNotify**与**fnevObjectModified**事件类型的目标文件夹或多次调用，一个用于每个影响消息。 同样，如果客户端发出[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)重复的调用，这些呼叫可以组合到一个**fnevObjectModified**事件文件夹或划分为单个**fnevObjectCreated**事件为每个新消息。 
  
有关详细了解如何以及何时生成通知，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[支持事件通知](supporting-event-notification.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|AdviseSink.h 和 AdviseSink.cpp  <br/> |CAdviseSink::OnNotifyDesc  <br/> |CAdviseSink 类实现处理 MFCMAPI 中的所有通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[HrAllocAdviseSink](hrallocadvisesink.md)
  
[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPISupport::Notify](imapisupport-notify.md)
  
[通知](notification.md)
  
[IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

