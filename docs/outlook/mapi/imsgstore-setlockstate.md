---
title: IMsgStoreSetLockState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.SetLockState
api_type:
- COM
ms.assetid: 4b1176ec-4126-43f5-856d-cbab8d622825
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2efee531e277b6295b7d4bc299eefc789a805d34
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571085"
---
# <a name="imsgstoresetlockstate"></a>IMsgStore::SetLockState

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
锁定或解除锁定一条消息。 只能通过 MAPI 后台处理程序调用此方法。
  
```cpp
HRESULT SetLockState(
  LPMESSAGE lpMessage,
  ULONG ulLockState  
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> [in]指向要锁定或解锁的消息的指针。
    
 _ulLockState_
  
> [in]一个值，指示是否应在锁定或解锁邮件。 下列值之一是有效的：
    
MSG_LOCKED 
  
> 邮件应被锁定。 
    
MSG_UNLOCKED 
  
> 邮件应为解除锁定。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功设置消息的锁定状态。
    
## <a name="remarks"></a>注解

**IMsgStore::SetLockState**方法锁定或解除锁定一条消息。 可以通过 MAPI 后台处理程序调用**SetLockState** ，其发送邮件时。 
  
通常，当 MAPI 后台处理程序调用**SetLockState**锁定一条消息，其锁定只有最早邮件 （即下, 一条消息排队 MAPI 后台处理程序发送的）。 如果最早的消息队列中等待暂时不可用的传输提供程序，并在下一步消息队列中的使用不同的传输提供程序，MAPI 后台处理程序可以开始处理更高版本的消息。 通过使用**SetLockState**锁定邮件开始处理。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

MAPI 后台处理程序已与_ulLockState_参数设置为 MSG_LOCKED 调用**SetLockState**后，必须先对[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)方法的调用，以取消消息的传输。 
  
调用**SetLockState**实现中的消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，以便保存之前收到**SetLockState**呼叫到邮件所做的任何更改。 
  
## <a name="see-also"></a>另请参阅



[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)
  
[IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

