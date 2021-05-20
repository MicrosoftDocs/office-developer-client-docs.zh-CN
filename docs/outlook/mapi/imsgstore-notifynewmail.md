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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a8ec06fd0401a129e08a06acdb1c18785f90d4a0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431776"
---
# <a name="imsgstorenotifynewmail"></a>IMsgStore::NotifyNewMail

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知邮件存储新邮件已到达。 此方法仅由 MAPI 后台处理程序调用。
  
```cpp
HRESULT NotifyNewMail(
  LPNOTIFICATION lpNotification
);
```

## <a name="parameters"></a>参数

 _lpNotification_
  
> [in]指向描述新邮件通知的 [NOTIFICATION](notification.md) 结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功通知邮件存储。
    
## <a name="remarks"></a>备注

MAPI 后台处理程序调用 **IMsgStore：：NotifyNewMail** 方法，以通知邮件存储邮件已准备好进行传递。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

调用 **NotifyNewMail** 时，将新邮件通知发送给所有注册的客户端。 如果选择使用支持对象方法，或者使用自己的实现，可以通过调用 [IMAPISupport：：Notify](imapisupport-notify.md)发送通知。 注册的客户端是一个已调用 [IMsgStore：：Advise](imsgstore-advise.md) 的客户端，并且将  _lpEntryID_ 参数设置为 NULL，将  _ulEventMask_ 参数设置为  _fnevNewMail_。 
  
不要修改或释放描述新邮件通知的 [NOTIFICATION](notification.md) 结构的内存。 通过调用 **实用程序** 函数 [ScCopyNotifications](sccopynotifications.md) 以利用其成员中的信息来复制 NOTIFICATION 结构。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::Subscribe](imapisupport-subscribe.md)
  
[IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)
  
[NOTIFICATION](notification.md)
  
[ScCopyNotifications](sccopynotifications.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

