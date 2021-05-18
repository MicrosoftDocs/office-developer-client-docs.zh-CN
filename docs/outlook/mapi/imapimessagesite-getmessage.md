---
title: IMAPIMessageSiteGetMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetMessage
api_type:
- COM
ms.assetid: 49d12c49-84f8-44ac-bc4a-2ee44a46f8c1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 03dd0553d0203585850ac5c4f8c91c86ef60236a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409025"
---
# <a name="imapimessagesitegetmessage"></a>IMAPIMessageSite::GetMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回当前邮件。
  
```cpp
HRESULT GetMessage(
  LPMESSAGE FAR * ppmsg
);
```

## <a name="parameters"></a>参数

 _ppmsg_
  
> [out]指向消息返回的接口的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
S_FALSE 
  
> 当前不存在用于调用窗体的消息。
    
## <a name="remarks"></a>备注

表单调用 **IMAPIMessageSite：：GetMessage** 方法以获取当前邮件的消息接口。 当前邮件与之前在[IPersistMessage：：InitNew、IPersistMessage：：Load](ipersistmessage-initnew.md)或[IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md)方法中传递的邮件相同。 [](ipersistmessage-load.md) 
  
 **如果当前不存在S_FALSE，GetMessage** 将返回一个返回消息。 在调用 [IPersistMessage：：HandsOffMessage](ipersistmessage-handsoffmessage.md) 方法之后或下次调用 **IPersistMessage：：Load** 或 **IPersistMessage：：SaveCompleted** 之前，可能会发生此状态。 
  
有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：GetSession  <br/> |MFCMAPI 使用 **IMAPIMessageSite：：GetMessage** 方法返回当前缓存的邮件指针（如果可用）。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)
  
[IPersistMessage::InitNew](ipersistmessage-initnew.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)
  
[IPersistMessage::Load](ipersistmessage-load.md)
  
[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

