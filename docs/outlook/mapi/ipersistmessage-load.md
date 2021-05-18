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
  
为指定邮件加载窗体。
  
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
  
> [in]指向要加载的表单的消息网站的指针。
    
 _pMessage_
  
> [in]指向应加载表单的消息的指针。
    
 _ulMessageStatus_
  
> [in]客户端定义或提供程序定义标志的位掩码，从邮件的 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制，提供有关邮件状态的信息。
    
 _ulMessageFlags_
  
> [in]从邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志位掩码，提供有关邮件状态的进一步信息。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功加载表单。
    
## <a name="remarks"></a>备注

表单查看器调用 **IPersistMessage：：Load** 方法来加载现有邮件的表单。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

 **只有在** 表单具有以下状态之一时调用 Load： 
  
- [未初始化](uninitialized-state.md)
    
- [HandsOffAfterSave](handsoffaftersave-state.md)
    
- [HandsOffFromNormal](handsofffromnormal-state.md)
    
如果窗体查看器在窗体位于任何其他状态时调用 **Load，** 该方法将返回E_UNEXPECTED。 
  
如果您的表单具有对活动邮件网站的引用，而不是传递到 **Load** 的活动邮件网站，请释放原始网站，因为它将不再使用。 从  _pMessageSite_ 和  _pMessage_ 参数存储指向邮件网站和邮件的指针，并调用这两个对象的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) 方法来增加其引用计数。 
  
**AddRef** 完成后，将 _ulMessageStatus_ 和 _ulMessageFlags_ 参数中的属性存储到表单中。 在显示表单之前，将表单转换为 [正常](normal-state.md) 状态，并调用其 [IMAPIViewAdviseSink：：OnNewMessage](imapiviewadvisesink-onnewmessage.md) 方法通知注册的查看者。 
  
如果未发生错误，则返回S_OK。 
  
## <a name="see-also"></a>另请参阅



[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)


[未初始化状态](uninitialized-state.md)
  
[HandsOffAfterSave 状态](handsoffaftersave-state.md)
  
[HandsOffFromNormal 状态](handsofffromnormal-state.md)
  
[表单状态](form-states.md)


[IPersistStorage：：Load](https://msdn.microsoft.com/library/34379b8d-4e00-49cd-9fd1-65f88746c61a.aspx)
  
[IPersistStream：：Load](https://msdn.microsoft.com/library/351e1187-9959-4542-8778-925457c3b8e3.aspx)
  
[IPersistFile：：Load](https://msdn.microsoft.com/library/8391aa5c-fe6e-4b03-9eef-7958f75910a5.aspx)

