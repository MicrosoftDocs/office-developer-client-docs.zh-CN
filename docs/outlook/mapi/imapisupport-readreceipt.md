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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326304"
---
# <a name="imapisupportreadreceipt"></a>IMAPISupport::ReadReceipt

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
生成邮件的读取或未读报告。
  
```cpp
HRESULT ReadReceipt(
ULONG ulFlags,
LPMESSAGE lpReadMessage,
LPMESSAGE FAR * lppEmptyMessage
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时标志的位掩码, 用于控制如何生成读取或未读报告。 可以设置以下标志:
    
MAPI_NON_READ 
  
> 生成未读报告。 如果未设置 MAPI_NON_READ, 则会生成一个读取报告。
    
 _lpReadMessage_
  
> 实时指向有关应生成报告的邮件的指针。
    
 _lppEmptyMessage_
  
> [in, out]在输入时, _lppEmptyMessage_指向指向空邮件的指针。 在输出时, _lppEmptyMessage_指向报告消息的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功生成报告。
    
## <a name="remarks"></a>注解

仅对消息存储提供程序支持对象实现**IMAPISupport:: ReadReceipt**方法。 邮件存储提供程序调用**ReadReceipt**以指示 MAPI 为_lpReadMessage_参数指向的邮件生成读取或未读报告。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果设置了**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性, 并且满足以下条件之一, 则调用**ReadReceipt** :
  
- 邮件已阅读。
    
- 邮件已移动。
    
- 邮件已复制。
    
- 已调用邮件的[IMessage:: SetReadFlag](imessage-setreadflag.md)方法。 
    
删除邮件时不要调用**ReadReceipt** 。 
  
对于一条消息, 应仅向其发送一次 read 或未读报告。 跟踪邮件的阅读状态, 并且不发送单个邮件的多个报告。
  
如果 MAPI 从**ReadReceipt**返回时, 如果_lppEmptyMessage_参数指向有效的报告消息, 请调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法以发送邮件, 然后通过调用其 IUnknown 来释放指针 **: s: release**方法。 
  
如果**ReadReceipt**失败, 应在不提交邮件的情况下释放邮件。 如果您存储邮件的阅读状态, 则可以尝试在以后生成 read 或未读报告。 
  
您可以隐藏或显示由文件夹中的存储生成的已读和未读报告。 在隐藏文件夹中存储读取和未读报告使您能够实现更严格的安全性。
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)
  
[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[PidTagReadReceiptRequested 规范属性](pidtagreadreceiptrequested-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

