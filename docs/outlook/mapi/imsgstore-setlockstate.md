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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9eeede2a430f5186daf429dd6ed59f312ae334be
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423627"
---
# <a name="imsgstoresetlockstate"></a>IMsgStore::SetLockState

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
锁定或解除锁定邮件。 此方法仅由 MAPI 后台处理程序调用。
  
```cpp
HRESULT SetLockState(
  LPMESSAGE lpMessage,
  ULONG ulLockState  
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> 实时指向要锁定或解锁的邮件的指针。
    
 _ulLockState_
  
> 实时一个值, 指示是否应锁定或解除锁定邮件。 以下值之一是有效的:
    
MSG_LOCKED 
  
> 应锁定邮件。 
    
MSG_UNLOCKED 
  
> 应解锁邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置邮件的锁定状态。
    
## <a name="remarks"></a>说明

**IMsgStore:: SetLockState**方法锁定或解除锁定邮件。 在发送邮件时, **SetLockState**只能由 MAPI 后台处理程序调用。 
  
通常情况下, 当 MAPI 后台处理程序调用**SetLockState**以锁定邮件时, 它将仅锁定最旧的邮件 (即, 在排队等待 MAPI 后台处理程序发送的下一封邮件)。 如果队列中的最旧邮件等待暂时不可用的传输提供程序, 并且队列中的下一封邮件使用不同的传输提供程序, 则 MAPI 后台处理程序可以开始处理后续邮件。 它通过使用**SetLockState**锁定邮件来开始处理。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

MAPI 后台处理程序在将_ulLockState_参数设置为 MSG_LOCKED 的情况下调用**SetLockState**后, 调用[IMsgStore:: AbortSubmit](imsgstore-abortsubmit.md)方法以取消邮件的传输必须失败。 
  
在**SetLockState**实现中调用邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法, 以便在收到**SetLockState**调用之前对邮件所做的任何更改都将被保存。 
  
## <a name="see-also"></a>另请参阅



[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)
  
[IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

