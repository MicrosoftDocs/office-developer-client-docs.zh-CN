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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437362"
---
# <a name="imessagesubmitmessage"></a>IMessage::SubmitMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
保存邮件的所有属性，将邮件标记为已准备好发送。
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]用于控制邮件提交方式的标志的位掩码。 可以设置以下标志：
    
FORCE_SUBMIT 
  
> MAPI 应立即提交邮件。 此标志当前未使用。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_NO_RECIPIENTS 
  
> 邮件的收件人表为空。
    
## <a name="remarks"></a>备注

**IMessage：：SubmitMessage** 方法将邮件标记为已准备好传输。 MAPI 按邮件标记为发送的顺序将邮件传递给基础邮件系统。 由于此功能，邮件可能在邮件存储中停留一段时间，然后基础邮件系统才能承担相关责任。 目标接收的顺序在基础邮件系统的控制中，不一定匹配邮件的发送顺序。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

调用邮件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来保存邮件，然后检查邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性。 如果设置了MSGFLAG_RESEND，请调用 [IMAPISupport：:P repareSubmit](imapisupport-preparesubmit.md)。 **PrepareSubmit** 更新收件人类型PR_RESPONSIBILITY (重新发送) 所有收件人的 [PidTagResponsibility](pidtagresponsibility-canonical-property.md)属性。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当 **SubmitMessage** 返回时，指向邮件及其关联的子对象、文件夹、附件、流、表等的所有指针将不再有效。 MAPI 不允许在这些指针上执行任何其他操作，除非调用它们的 **IUnknown：：Release** 方法。 MAPI 设计为在调用 **SubmitMessage** 后，应释放邮件以及所有关联的子对象。 但是，如果 **SubmitMessage** 返回指示缺失或无效信息的错误值，则邮件将保持打开状态，指针保持有效。 
  
若要取消发送操作，请获取并存储指向邮件的 PR_ENTRYID ( [PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的指针，然后再提交邮件。 由于邮件的条目标识符在提交邮件后无效，因此有必要在调用 **SubmitMessage 之前保存它**。 若要取消发送，请将  _lpEntryId_ 参数指向此条目标识符并调用 [IMsgStore：：AbortSubmit](imsgstore-abortsubmit.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |**CFolderDlg：：OnSubmitMessage** <br/> |MFCMAPI 使用 **IMessage：：SubmitMessage** 方法提交所选邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

