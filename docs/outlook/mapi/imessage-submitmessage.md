---
title: IMessageSubmitMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.SubmitMessage
api_type:
- COM
ms.assetid: 9ce93469-c55d-48d1-9abb-a637716ed4f2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1d325c67c836e727d8285bd2dceecf88bf68327c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775769"
---
# <a name="imessagesubmitmessage"></a>IMessage::SubmitMessage

  
  
**适用于**： Outlook 
  
保存所有消息的属性，并将邮件标记为已准备好发送。
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]用于控制一条消息的提交方式的标志位掩码。 可以设置以下标记：
    
FORCE_SUBMIT 
  
> MAPI 应立即提交的邮件。 此标志不当前正在使用中。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NO_RECIPIENTS 
  
> 邮件的收件人表为空。
    
## <a name="remarks"></a>说明

**IMessage::SubmitMessage**方法将邮件标记为已准备好进行传输。 MAPI 将消息传递给基础邮件系统发送的标记的顺序。 由于此功能，一条消息可能消息存储区中保持之前基础消息系统可以负责为它一些时间。 在目标接收的顺序处于基础邮件系统的控件，并且不一定匹配已发送邮件的顺序。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

调用消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法以将其保存，然后检查消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性。 如果设置了 MSGFLAG_RESEND 标志，调用[IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md)。 **PrepareSubmit**更新中重新发送邮件的收件人的所有收件人类型和**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性。
  
## <a name="notes-to-callers"></a>给调用方的说明

**SubmitMessage**返回时，所有指向邮件，并与其关联的子对象的邮件，将不再有效文件夹、 附件、 流、 表和等等。 MAPI 不允许任何进一步的操作对这些指针，调用其**IUnknown::Release**方法除外。 MAPI 旨在以便调用**SubmitMessage**后，您应释放消息和所有关联的子对象。 但是，如果**SubmitMessage**返回错误值，该值指示缺失或无效的信息，邮件保持打开状态，指针保持有效。 
  
若要取消发送操作，获取并提交邮件之前存储指向消息的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 因为消息的项标识符将失效提交邮件后，很有必要，以将其保存在调用**SubmitMessage**之前。 若要取消发送， _lpEntryId_参数指向此条目标识符，并调用[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |**CFolderDlg::OnSubmitMessage** <br/> |MFCMAPI 使用**IMessage::SubmitMessage**方法提交所选的消息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

