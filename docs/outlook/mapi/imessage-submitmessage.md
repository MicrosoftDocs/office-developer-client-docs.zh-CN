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
ms.openlocfilehash: 28786f483c4d2031c334d7b9697db7c5e627fe93
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349229"
---
# <a name="imessagesubmitmessage"></a>IMessage::SubmitMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
保存邮件的所有属性, 并将邮件标记为 "已准备好发送"。
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制如何提交邮件的标志的位掩码。 可以设置以下标志:
    
FORCE_SUBMIT 
  
> MAPI 应立即提交邮件。 此标志当前未在使用中。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NO_RECIPIENTS 
  
> 邮件的收件人表为空。
    
## <a name="remarks"></a>注解

**IMessage:: SubmitMessage**方法将邮件标记为已准备好传输。 MAPI 将邮件按标记为发送的顺序传递给基础邮件系统。 由于此功能, 邮件可能会在邮件存储区中保留一段时间, 然后基础邮件系统才能对其承担责任。 目标中的收据顺序位于基础邮件系统的控制中, 并不一定与发送邮件的顺序一致。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

调用邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以保存它, 然后检查邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性。 如果设置了 MSGFLAG_RESEND 标志, 则调用[IMAPISupport::P reparesubmit](imapisupport-preparesubmit.md)。 **PrepareSubmit**更新重发邮件中所有收件人的收件人类型和**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性。
  
## <a name="notes-to-callers"></a>给调用方的说明

当**SubmitMessage**返回时, 指向邮件及其关联的子消息、文件夹、附件、流、表格等的所有指针都将不再有效。 MAPI 不允许对这些指针执行任何进一步的操作, 但调用其**IUnknown:: Release**方法除外。 MAPI 的设计方式是, 在调用**SubmitMessage**后, 您应释放邮件和所有关联的子类型。 但是, 如果**SubmitMessage**返回一个指示缺少或无效信息的错误值, 则邮件仍处于打开状态, 并且指针仍然有效。 
  
若要取消发送操作, 请先获取并存储指向邮件的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的指针, 然后再提交邮件。 由于在提交邮件后邮件的条目标识符无效, 因此必须先保存它, 然后才能调用**SubmitMessage**。 若要取消发送, 请将_lpEntryId_参数指向此条目标识符, 并调用[IMsgStore:: AbortSubmit](imsgstore-abortsubmit.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg  <br/> |**CFolderDlg:: OnSubmitMessage** <br/> |MFCMAPI 使用**IMessage:: SubmitMessage**方法提交选定的邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

