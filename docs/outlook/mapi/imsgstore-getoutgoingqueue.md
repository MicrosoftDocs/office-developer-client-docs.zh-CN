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
  
提供对传出队列表的访问权限, 该表包含有关邮件存储的传出队列中的所有邮件的信息。 此方法仅由 MAPI 后台处理程序调用。
  
```cpp
HRESULT GetOutgoingQueue(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _lppTable_
  
> 排除指向传出队列表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回传出队列表。
    
## <a name="remarks"></a>说明

**IMsgStore:: GetOutgoingQueue**方法为 MAPI 后台处理程序提供对显示邮件存储的传出邮件队列的表的访问权限。 通常情况下, 在调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法后, 邮件将放入传出队列表中。 但是, 由于提交顺序影响了预处理和提交到传输提供程序的顺序, 因此一些已标记为发送的邮件可能不会立即显示在传出队列表中。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

有关必须作为传出队列表中的列包含的属性的列表, 请参阅[传出队列表](outgoing-queue-tables.md)。 
  
由于 mapi 后台处理程序旨在按提交时间的升序顺序从邮件存储区接受邮件, 因此允许 MAPI 后台处理程序对传出队列表进行排序以匹配此顺序, 或将其设置为默认的排序顺序。
  
您必须支持传出邮件队列表的通知, 以确保在队列的内容发生更改时通知 MAPI 后台处理程序。 
  
## <a name="see-also"></a>另请参阅



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

