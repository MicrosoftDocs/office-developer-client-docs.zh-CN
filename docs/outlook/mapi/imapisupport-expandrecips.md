---
title: IMAPISupportExpandRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ExpandRecips
api_type:
- COM
ms.assetid: 78edd549-d557-489a-85f5-adfb5c44a7d4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 105219fe430cd8746c3aa6cf5cd90629d5f72080
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411244"
---
# <a name="imapisupportexpandrecips"></a>IMAPISupport::ExpandRecips

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
完成邮件的收件人列表，扩展特定通讯组列表。
  
```cpp
HRESULT ExpandRecips(
  LPMESSAGE lpMessage,
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> [in]指向包含要处理的收件人列表的邮件的指针。
    
 _lpulFlags_
  
> [out]指向控制所发生处理类型的标志的位掩码的指针。 可以设置以下标志：
    
NEEDS_PREPROCESSING 
  
> 在发送邮件之前，需要先对邮件进行预处理。
    
NEEDS_SPOOLER 
  
> MAPI 后台处理程序 (与呼叫者紧密耦合的传输提供程序) 必须发送邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功处理邮件的收件人列表。
    
## <a name="remarks"></a>备注

**IMAPISupport：：ExpandRecips** 方法为邮件存储提供程序支持对象实现。 邮件存储提供程序调用 **ExpandRecips** 以提示 MAPI 执行以下任务： 
  
- 将某些个人通讯组列表展开到其组件收件人。
    
- 将已更改的所有显示名称替换为原始名称。
    
- 标记任何重复的条目。
    
- 解析所有一次地址。 
    
- 检查邮件是否需要预处理，如果需要预处理，则设置  _lpulFlags_ 指向NEEDS_PREPROCESSING。 
    
 **ExpandRecips** 展开邮件地址类型为 MAPIPDL 的任何通讯组列表。 
  
## <a name="notes-to-callers"></a>给调用方的说明

始终在 **邮件处理过程中调用 ExpandRecips。** 调用 **ExpandRecips，** 这是 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法实现中的第一个调用。 
  
## <a name="see-also"></a>另请参阅



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

