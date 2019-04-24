---
title: IPersistMessageLoad
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.Load
api_type:
- COM
ms.assetid: bd4646d2-8229-499d-91aa-3cbec72b9445
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5024c2f8b88b54051e4b8400f4b3f14374b10c23
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317127"
---
# <a name="ipersistmessageload"></a>IPersistMessage::Load

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为指定的邮件加载窗体。
  
```cpp
HRESULT Load(
  LPMESSAGESITE pMessageSite,
  LPMESSAGE pMessage,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags
);
```

## <a name="parameters"></a>参数

 _pMessageSite_
  
> 实时指向要加载的表单的邮件网站的指针。
    
 _pMessage_
  
> 实时指向应为其加载表单的邮件的指针。
    
 _ulMessageStatus_
  
> 实时客户端定义或提供程序定义的标志的位掩码, 从邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中进行复制, 这些标志提供有关邮件状态的信息。
    
 _ulMessageFlags_
  
> 实时从邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中复制的标志的位掩码, 可提供有关邮件状态的进一步信息。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单已成功加载。
    
## <a name="remarks"></a>注解

表单查看者调用**IPersistMessage:: load**方法以加载现有邮件的表单。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

 仅当窗体处于以下状态之一时, 才会调用**Load** : 
  
- [即](uninitialized-state.md)
    
- [HandsOffAfterSave](handsoffaftersave-state.md)
    
- [HandsOffFromNormal](handsofffromnormal-state.md)
    
如果表单查看器在窗体处于任何其他状态时调用**Load** , 则该方法返回 E_UNEXPECTED。 
  
如果您的表单具有对传递给**负载**的活动邮件网站的引用, 请释放原始网站, 因为它将不再使用。 将指针存储到邮件网站和来自_pMessageSite_和_pMessage_参数的消息, 并调用两个对象的[IUnknown:: AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法以增加其引用计数。 
  
完成**AddRef**后, 将_ulMessageStatus_和_ulMessageFlags_参数中的属性存储到窗体中。 在显示窗体之前将其转换为[正常](normal-state.md)状态, 并通过调用其[IMAPIViewAdviseSink:: OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法来通知注册的查看者。 
  
如果没有出现任何错误, 则返回 S_OK。 
  
## <a name="see-also"></a>另请参阅



[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)


[未初始化状态](uninitialized-state.md)
  
[HandsOffAfterSave 状态](handsoffaftersave-state.md)
  
[HandsOffFromNormal 状态](handsofffromnormal-state.md)
  
[表单状态](form-states.md)


[IPersistStorage:: Load](https://msdn.microsoft.com/library/34379b8d-4e00-49cd-9fd1-65f88746c61a.aspx)
  
[IPersistStream:: Load](https://msdn.microsoft.com/library/351e1187-9959-4542-8778-925457c3b8e3.aspx)
  
[IPersistFile:: Load](https://msdn.microsoft.com/library/8391aa5c-fe6e-4b03-9eef-7958f75910a5.aspx)

