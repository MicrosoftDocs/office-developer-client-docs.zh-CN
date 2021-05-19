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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8ccb732dd587b2e5107290b2db7c48e85d0145d4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434149"
---
# <a name="imsgstoregetoutgoingqueue"></a>IMsgStore::GetOutgoingQueue

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对传出队列表的访问，该表包含有关邮件存储的传出队列中所有邮件的信息。 此方法仅由 MAPI 后台处理程序调用。
  
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
  
> [out]指向传出队列表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回传出队列表。
    
## <a name="remarks"></a>备注

**IMsgStore：：GetOutgoingQueue** 方法为 MAPI 后台处理程序提供了对显示邮件存储的传出邮件队列的表的访问权限。 通常，在调用邮件 [的 IMessage：：SubmitMessage](imessage-submitmessage.md) 方法后，邮件会放置在传出队列表中。 但是，由于提交顺序会影响预处理的顺序以及提交到传输提供程序的顺序，因此一些标记为发送的邮件可能不会立即显示在传出队列表中。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

有关必须作为列包含在传出队列表中的属性的列表，请参阅 Outgoing [Queue Tables。](outgoing-queue-tables.md) 
  
由于 MAPI 后台处理程序旨在以提交时间升序接受来自邮件存储的邮件，因此，请允许 MAPI 后台处理程序对传出队列表进行排序以匹配此顺序，或建立该表作为默认排序顺序。
  
必须支持传出邮件队列表的通知，以确保在队列内容更改时通知 MAPI 后台处理程序。 
  
## <a name="see-also"></a>另请参阅



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

