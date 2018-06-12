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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5e56fd8c053ff32bdeb7b243701c0330b378cdc0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775669"
---
# <a name="imapisupportreadreceipt"></a>IMAPISupport::ReadReceipt

  
  
**适用于**： Outlook 
  
生成一个读取或 nonread 的报销单以供一条消息。
  
```cpp
HRESULT ReadReceipt(
ULONG ulFlags,
LPMESSAGE lpReadMessage,
LPMESSAGE FAR * lppEmptyMessage
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控制如何生成读取或 nonread 的报告。 可以设置以下标记：
    
MAPI_NON_READ 
  
> 生成 nonread 的报告。 如果未设置 MAPI_NON_READ，生成读取的报表。
    
 _lpReadMessage_
  
> [in]一个指向有关哪些应生成报告的邮件。
    
 _lppEmptyMessage_
  
> [传入、 传出]在输入_lppEmptyMessage_指向指向空消息的指针。 输出， _lppEmptyMessage_指向指向报告消息的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功生成报告。
    
## <a name="remarks"></a>备注

只为消息存储提供程序支持对象实现**IMAPISupport::ReadReceipt**方法。 消息存储提供程序调用**readreceipt 已**以指示 MAPI 生成读取或 nonread 的报告_lpReadMessage_参数指向的邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

时设置**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性，而且以下条件之一是，则返回 true，则调用**readreceipt 已**：
  
- 邮件已被阅读。
    
- 邮件已移动。
    
- 邮件已复制。
    
- 调用了消息的[IMessage::SetReadFlag](imessage-setreadflag.md)方法。 
    
不要调用**readreceipt 已**删除邮件时。 
  
为读取或 nonread 的报表应发送仅执行一次邮件。 跟踪的消息的只读的状态，但不会发送单个邮件的多个报表。
  
如果_lppEmptyMessage_参数指向有效报告消息 MAPI 返回**readreceipt 已**从时，，呼叫要发送消息，然后通过调用其**IUnknown:s:Release 释放鼠标指针的[IMessage::SubmitMessage](imessage-submitmessage.md)方法**方法。 
  
如果**readreceipt 已**失败，则应未经要提交释放邮件。 如果存储消息的只读的状态，您可以尝试在以后生成的已读或 nonread 的报告。 
  
您可以隐藏或显示生成的文件夹中存储的读取和 nonread 报告。 隐藏文件夹中存储读取和 nonread 报告使您能够实现更严格的安全性。
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)
  
[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[PidTagReadReceiptRequested 规范属性](pidtagreadreceiptrequested-canonical-property.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

