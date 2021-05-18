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
ms.openlocfilehash: d647b41018afbade91dffb2818b48b0738148855
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411762"
---
# <a name="imapiformadvisesinkonactivatenext"></a>IMAPIFormAdviseSink::OnActivateNext

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示表单是否可以处理要显示的下一封邮件的邮件类。
  
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
  
> [in]指向下一封邮件的邮件类的指针。
    
 _ulMessageStatus_
  
> [in]客户端定义或提供程序定义标志的位掩码，从要显示的下一封邮件的 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制，提供有关包含邮件的内容表的状态信息。
    
 _ulMessageFlags_
  
> [in]指向从要显示的下一封邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志的位掩码的指针，指示邮件的当前状态。
    
 _ppPersistMessage_
  
> [out]指向用于新表单的表单对象的 [IPersistMessage](ipersistmessageiunknown.md) 实现（如果需要新表单）的指针。 如果当前表单对象可用于显示和保存下一条消息，则返回一个指向 NULL 的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知成功，表单可以处理下一封邮件。
    
S_FALSE 
  
> 窗体不处理下一封邮件的邮件类。
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormAdviseSink：：OnActivateNext** 方法，以帮助表单确定是否可以在文件夹中显示下一封邮件。 下一封邮件可能是任何类的邮件，但通常为同一个类或相关类。 这样，通过允许客户端应用程序尽可能重复使用表单对象，可以更高效地读取同一类的多个消息。 
  
大多数表单对象将使用  _lpszMessageClass_ 参数指向的消息类来确定它们是否可以处理下一封邮件。 通常，除了属于默认类的邮件之外，窗体还可以处理属于其默认类的类的邮件。 但是，表单可以使用其他因素来确定是否可以处理邮件，如下一封邮件的已发送状态或未发送状态。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果S_OK可以处理邮件类，则返回  _ppPersistMessage_ 参数中的值和 NULL。 如果表单可以创建一个新表单来处理无法处理的邮件，请按照以下步骤操作： 
  
1. 调用窗体的类工厂以创建一个新的窗体对象的实例。
    
2. 将实例存储在  _ppPersistMessage_ 指针参数的内容中。 
    
3. 返回S_OK。
    
表单查看器将通过使用 [IPersistMessage：：Load](ipersistmessage-load.md) 方法加载邮件，该方法属于  _ppPersistMessage_ 指向的对象。
  
如果窗体和可以创建的窗体均不能处理下一封邮件，则返回S_FALSE。 但是，通常，表单不应返回此值，因为它会导致在表单查看器中性能降低。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |CMyMAPIFormViewer：：ActivateNext  <br/> |MFCMAPI 使用 **IMAPIFormAdviseSink：：OnActivateNext** 方法实现 [IMAPIViewContext：：ActivateNext](imapiviewcontext-activatenext.md) 方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)
  
[IPersistMessage::Load](ipersistmessage-load.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFormAdviseSink : IUnknown](imapiformadvisesinkiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

