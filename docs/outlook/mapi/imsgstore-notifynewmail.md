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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348753"
---
# <a name="imsgstorenotifynewmail"></a>IMsgStore::NotifyNewMail

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知邮件存储区新邮件已到达。 此方法仅由 MAPI 后台处理程序调用。
  
```cpp
HRESULT NotifyNewMail(
  LPNOTIFICATION lpNotification
);
```

## <a name="parameters"></a>参数

 _lpNotification_
  
> 实时指向描述新邮件通知的[通知](notification.md)结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功通知邮件存储区。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IMsgStore:: NotifyNewMail**方法, 以通知邮件存储区邮件已准备好传递。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

调用**NotifyNewMail**时, 向所有已注册的客户端发送新邮件通知。 如果选择使用支持对象方法, 或使用自己的实现, 则可以通过调用[IMAPISupport:: Notify](imapisupport-notify.md)来发送通知。 已注册的客户端是已调用[IMsgStore:: 建议](imsgstore-advise.md), 并将_lpEntryID_参数设置为 NULL, 并将_ulEventMask_参数设置为_fnevNewMail_。 
  
请勿修改或释放描述新邮件通知的[通知](notification.md)结构的内存。 通过调用实用工具函数[ScCopyNotifications](sccopynotifications.md)来复制**通知**结构, 以使用其成员中的信息。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::Subscribe](imapisupport-subscribe.md)
  
[IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)
  
[NOTIFICATION](notification.md)
  
[ScCopyNotifications](sccopynotifications.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

