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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316525"
---
# <a name="imapisupportexpandrecips"></a>IMAPISupport::ExpandRecips

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
完成邮件的收件人列表, 展开特定的通讯组列表。
  
```cpp
HRESULT ExpandRecips(
  LPMESSAGE lpMessage,
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> 实时指向包含要处理的收件人列表的邮件的指针。
    
 _lpulFlags_
  
> 排除一个指针, 指向用于控制所发生的处理类型的标志的位掩码。 可以设置以下标志:
    
NEEDS_PREPROCESSING 
  
> 邮件在发送之前需要进行预处理。
    
NEEDS_SPOOLER 
  
> MAPI 后台处理程序 (而不是呼叫者紧密耦合的传输提供程序) 必须发送邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功处理邮件的收件人列表。
    
## <a name="remarks"></a>注解

为邮件存储提供程序支持对象实现了**IMAPISupport:: ExpandRecips**方法。 邮件存储提供程序调用**ExpandRecips**以提示 MAPI 执行以下任务: 
  
- 将某些个人通讯组列表展开到其组件收件人。
    
- 使用原始名称替换已更改的所有显示名称。
    
- 标记任何重复条目。
    
- 解决所有的一次性地址。 
    
- 检查邮件是否需要进行预处理, 如果有, 则将_lpulFlags_指向 NEEDS_PREPROCESSING 的标志设置为 ""。 
    
 **ExpandRecips**展开邮件地址类型为 MAPIPDL 的任何通讯组列表。 
  
## <a name="notes-to-callers"></a>给调用方的说明

始终在邮件处理过程中调用**ExpandRecips** 。 调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法实现中的第一个调用的**ExpandRecips** 。 
  
## <a name="see-also"></a>另请参阅



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

