---
title: IMAPIFormAdviseSinkOnActivateNext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormAdviseSink.OnActivateNext
api_type:
- COM
ms.assetid: db621dfd-c6ad-42d2-8089-db40a63cab36
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7e8fb69e7d25420186d7269943c5d957311e813d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581753"
---
# <a name="imapiformadvisesinkonactivatenext"></a>IMAPIFormAdviseSink::OnActivateNext

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示表单是否可以处理的下一条消息以显示的邮件类。
  
```cpp
HRESULT OnActivateNext(
  LPCSTR lpszMessageClass,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags,
  LPPERSISTMESSAGE FAR * ppPersistMessage
);
```

## <a name="parameters"></a>参数

 _lpszMessageClass_
  
> [in]指向下一条消息的邮件类的指针。
    
 _ulMessageStatus_
  
> [in]客户端或提供程序定义的标志，复制**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性以显示，下一条消息中的位掩码，它提供邮件包含有关内容表的状态信息中。
    
 _ulMessageFlags_
  
> [in]指向标志复制**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性以显示的下一条消息中的位掩码的指示邮件的当前状态。
    
 _ppPersistMessage_
  
> [输出]指向用于新窗体，如果需要一个新窗体的窗体对象的[IPersistMessage](ipersistmessageiunknown.md)实现的指针的指针。 如果当前窗体对象可用于显示和保存下一条消息，则可以返回为 NULL 的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功和窗体可以处理下一条消息。
    
S_FALSE 
  
> 窗体并不处理的邮件类的下一条消息。
    
## <a name="remarks"></a>注解

表单查看器调用**IMAPIFormAdviseSink::OnActivateNext**方法，可帮助确定是否可以在文件夹中显示下一条消息的窗体。 下一条消息可能的任何类中，一条消息，但它通常是相同的类或相关的类。 这样使客户端应用程序能够重复使用表单对象尽可能读取效率同一个类的多个邮件的过程。 
  
大多数窗体对象将使用_lpszMessageClass_参数指向的邮件类来确定是否能够处理下一条消息。 通常窗体可以处理属于窗体的默认类的子类，除了所属的默认类的邮件类的消息。 但是，表单可以使用其他因素问题不确定是否可以处理消息，如下一条消息的发送或未发送的状态。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果窗体可以处理的邮件类中_ppPersistMessage_参数中返回 S_OK 和 NULL。 如果窗体可以创建新表单可以处理窗体处于无法处理的消息，请按照下列步骤： 
  
1. 调用窗体的类工厂，以创建新的窗体对象的实例。
    
2. 在_ppPersistMessage_指针参数的内容中存储的实例。 
    
3. 返回 S_OK。
    
表单查看器将使用指向_ppPersistMessage_对象所属的[IPersistMessage::Load](ipersistmessage-load.md)方法加载邮件。
  
如果既没有表单，也可以创建窗体可以处理下一条消息，则返回 S_FALSE。 但是，一般情况下，窗体不应该返回此值，因为它会导致降低表单查看器中的性能。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |CMyMAPIFormViewer::ActivateNext  <br/> |MFCMAPI 使用**IMAPIFormAdviseSink::OnActivateNext**方法实现[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)
  
[IPersistMessage::Load](ipersistmessage-load.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFormAdviseSink : IUnknown](imapiformadvisesinkiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

