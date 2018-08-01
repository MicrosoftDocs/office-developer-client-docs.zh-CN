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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2e41701d3a739864b1eafc8001833b7df5c8908b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775614"
---
# <a name="imapisupportexpandrecips"></a>IMAPISupport::ExpandRecips

  
  
**适用于**： Outlook 
  
完成邮件的收件人列表中，展开特定的通讯组列表。
  
```cpp
HRESULT ExpandRecips(
  LPMESSAGE lpMessage,
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> [in]一个指向其处理的收件人列表的邮件。
    
 _lpulFlags_
  
> [输出]指向控制，发生此事件的处理的类型的标志位掩码的指针。 可以设置以下标志：
    
NEEDS_PREPROCESSING 
  
> 需要发送之前预处理消息。
    
NEEDS_SPOOLER 
  
> MAPI 后台处理程序 （而不是指紧密耦合呼叫者的传输提供程序） 必须发送邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功处理邮件的收件人列表。
    
## <a name="remarks"></a>说明

消息存储提供程序支持对象的实现**IMAPISupport::ExpandRecips**方法。 消息存储提供程序调用**ExpandRecips**提示 MAPI 以执行以下任务： 
  
- 展开至其组件收件人的特定个人通讯组列表。
    
- 原始名称中替换所有已更改的显示名称。
    
- 标记任何重复项。
    
- 解决所有一次性地址。 
    
- 检查是否消息需要预处理，并且，如果是这样，设置所指的_lpulFlags_到 NEEDS_PREPROCESSING 标志。 
    
 **ExpandRecips**展开具有消息地址类型 MAPIPDL 的任何通讯组列表。 
  
## <a name="notes-to-callers"></a>给调用方的说明

始终调用**ExpandRecips**作为消息处理的一部分。 在您[IMessage::SubmitMessage](imessage-submitmessage.md)方法实现中进行调用**ExpandRecips**之一的第一个呼叫。 
  
## <a name="see-also"></a>另请参阅



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

