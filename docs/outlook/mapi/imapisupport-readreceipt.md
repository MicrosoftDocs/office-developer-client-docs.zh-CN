---
title: IMAPISupportReadReceipt
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ReadReceipt
api_type:
- COM
ms.assetid: ef31b61a-93b6-4ae8-bc71-f5ef5caf43f4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1915004847fdfd27c97656223866aaab9d3e59c9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425321"
---
# <a name="imapisupportreadreceipt"></a>IMAPISupport::ReadReceipt

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
生成邮件的已读或非读报告。
  
```cpp
HRESULT ReadReceipt(
ULONG ulFlags,
LPMESSAGE lpReadMessage,
LPMESSAGE FAR * lppEmptyMessage
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制如何生成已读报表或非读报表的标志的位掩码。 可以设置以下标志：
    
MAPI_NON_READ 
  
> 将生成未读报告。 如果未MAPI_NON_READ，将生成读取报告。
    
 _lpReadMessage_
  
> [in]指向应生成报告的消息的指针。
    
 _lppEmptyMessage_
  
> [in， out]在输入时  _，lppEmptyMessage_ 指向指向空消息的指针。 在输出上  _，lppEmptyMessage_ 指向指向报告邮件的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 报告已成功生成。
    
## <a name="remarks"></a>备注

**IMAPISupport：：ReadReceipt** 方法仅为邮件存储提供程序支持对象实现。 邮件存储提供程序调用 **ReadReceipt** 以指示 MAPI 为  _lpReadMessage_ 参数指向的邮件生成已读或非读报告。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当设置了 [PidTagReadReceiptRequested PR_READ_RECEIPT_REQUESTED (PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) ，并且满足下列条件之一时，调用 **ReadReceipt：** 
  
- 邮件已阅读。
    
- 邮件已移动。
    
- 邮件已复制。
    
- 已调用邮件 [的 IMessage：：SetReadFlag](imessage-setreadflag.md) 方法。 
    
删除邮件时不要调用 **ReadReceipt。** 
  
对于邮件，应只发送一次已读或非读报告。 跟踪邮件的阅读状态，不要发送单个邮件的多个报告。
  
如果  _lppEmptyMessage_ 参数在 MAPI 从 **ReadReceipt** 返回时指向有效的报告邮件，请调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法发送邮件，然后通过调用指针 **的 IUnknown：s：Release** 方法释放指针。 
  
如果 **ReadReceipt** 失败，应释放邮件而不提交。 如果存储邮件的阅读状态，可以尝试稍后生成已读或不读报告。 
  
可以隐藏或显示文件夹中存储生成的已读和非读报告。 将已读和非读报告存储在隐藏文件夹中使您能够实现更严格的安全性。
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)
  
[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[PidTagReadReceiptRequested 规范属性](pidtagreadreceiptrequested-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

