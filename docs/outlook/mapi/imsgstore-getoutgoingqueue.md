---
title: IMsgStoreGetOutgoingQueue
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.GetOutgoingQueue
api_type:
- COM
ms.assetid: 8316ff89-104d-43fd-902b-476fe567e23b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1b59071758aad9c71939eb9efc029005806b2a37
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775878"
---
# <a name="imsgstoregetoutgoingqueue"></a>IMsgStore::GetOutgoingQueue

  
  
**适用于**： Outlook 
  
提供对传出队列表，具有信息的所有邮件的邮件存储传出队列中的表的访问。 只能通过 MAPI 后台处理程序调用此方法。
  
```cpp
HRESULT GetOutgoingQueue(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _lppTable_
  
> [输出]指向与传出队列表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回传出队列表。
    
## <a name="remarks"></a>说明

**IMsgStore::GetOutgoingQueue**方法提供了有权访问表的显示的消息存储队列的传出消息的 MAPI 后台处理程序。 通常情况下，消息发出传出队列表中调用其[IMessage::SubmitMessage](imessage-submitmessage.md)方法之后。 但是，由于提交的顺序将影响预处理和提交到传输提供程序的顺序，某些被标记为发送的消息可能未显示在传出队列表立即。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

必须为传出队列数据表中的列包含的属性的列表，请参阅[传出队列表](outgoing-queue-tables.md)。 
  
由于设计 MAPI 后台处理程序是要接受来自提交时间的升序的消息存储的邮件，也允许 MAPI 后台处理程序传出的队列表格，以匹配以下顺序或建立作为默认排序顺序进行排序。
  
传出消息队列表，必须支持通知确保队列的内容更改时 MAPI 后台处理程序将收到通知。 
  
## <a name="see-also"></a>另请参阅



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

