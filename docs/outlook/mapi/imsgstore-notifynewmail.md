---
title: IMsgStoreNotifyNewMail
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.NotifyNewMail
api_type:
- COM
ms.assetid: d0d003b0-f12f-4422-b71f-26886169461f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bdda950cd1fab66db46590e0b9141bb3d2a75221
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775870"
---
# <a name="imsgstorenotifynewmail"></a>IMsgStore::NotifyNewMail

  
  
**适用于**： Outlook 
  
通知新消息已到达的消息存储。 只能通过 MAPI 后台处理程序调用此方法。
  
```cpp
HRESULT NotifyNewMail(
  LPNOTIFICATION lpNotification
);
```

## <a name="parameters"></a>参数

 _lpNotification_
  
> [in]指向描述新邮件通知的[通知](notification.md)结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功通知消息存储库。
    
## <a name="remarks"></a>说明

MAPI 后台处理程序通知消息存储一条消息准备好交付调用**IMsgStore::NotifyNewMail**方法。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

调用**NotifyNewMail**时，向所有已注册的客户端发送新邮件通知。 如果您选择使用支持对象方法，调用[IMAPISupport::Notify](imapisupport-notify.md)，或使用您自己的实现，您可以发送通知。 注册的客户端是指已调用[IMsgStore::Advise](imsgstore-advise.md)和_lpEntryID_参数设置为 NULL 和_fnevNewMail_ _ulEventMask_参数。 
  
无法修改或释放介绍新邮件通知的[通知](notification.md)结构的内存。 通过调用实用工具函数[ScCopyNotifications](sccopynotifications.md)进行复制的**通知**结构中其成员的信息的使用。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::Subscribe](imapisupport-subscribe.md)
  
[IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)
  
[NOTIFICATION](notification.md)
  
[ScCopyNotifications](sccopynotifications.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

