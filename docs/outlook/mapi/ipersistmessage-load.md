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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: eff192b0d2b5cde51a2909452b19ffe1a47b2c04
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775983"
---
# <a name="ipersistmessageload"></a>IPersistMessage::Load

  
  
**适用于**： Outlook 
  
加载指定的消息的窗体。
  
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
  
> [in]指向要加载窗体的邮件网站的指针。
    
 _pMessage_
  
> [in]一个指向应为其加载窗体的邮件。
    
 _ulMessageStatus_
  
> [in]客户端或提供程序定义的标志，复制邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中的位掩码，提供有关邮件的状态信息。
    
 _ulMessageFlags_
  
> [in]标志，复制邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的位掩码的进一步提供有关邮件的状态信息。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功加载窗体。
    
## <a name="remarks"></a>备注

表单查看器调用**IPersistMessage::Load**方法以加载的现有邮件窗体。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

 仅当表单处于以下状态之一时调用**负载**： 
  
- [未初始化](uninitialized-state.md)
    
- [HandsOffAfterSave](handsoffaftersave-state.md)
    
- [HandsOffFromNormal](handsofffromnormal-state.md)
    
如果表单查看器调用**负载**在窗体中任何其他状态时，该方法将返回 E_UNEXPECTED。 
  
如果窗体有一个引用传递到**负载**以外的活动邮件网站，释放原始网站，因为不再使用它。 存储从_pMessageSite_和_pMessage_参数的消息网站和消息的指针和调用这两个对象的[IUnknown::AddRef](http://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法，以增加其引用计数。 
  
**AddRef**完成后，存储到表单的_ulMessageStatus_和_ulMessageFlags_参数中的属性。 显示之前, 转换为其[普通](normal-state.md)状态窗体，并通过调用其[IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法通知注册的查看器。 
  
如果没有错误，则返回 S_OK。 
  
## <a name="see-also"></a>另请参阅



[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IPersistMessage: IUnknown](ipersistmessageiunknown.md)


[未初始化的状态](uninitialized-state.md)
  
[HandsOffAfterSave 状态](handsoffaftersave-state.md)
  
[HandsOffFromNormal 状态](handsofffromnormal-state.md)
  
[窗体状态](form-states.md)


[IPersistStorage::Load](http://msdn.microsoft.com/library/34379b8d-4e00-49cd-9fd1-65f88746c61a.aspx)
  
[IPersistStream::Load](http://msdn.microsoft.com/library/351e1187-9959-4542-8778-925457c3b8e3.aspx)
  
[IPersistFile::Load](http://msdn.microsoft.com/library/8391aa5c-fe6e-4b03-9eef-7958f75910a5.aspx)

