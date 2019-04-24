---
title: IMAPISupportDoSentMail
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoSentMail
api_type:
- COM
ms.assetid: 4bb65c2a-9926-42da-9161-47836e8de40a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8289b8dd2e0ab3c760e77a37b821d2fe74e4abe9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315967"
---
# <a name="imapisupportdosentmail"></a>IMAPISupport::DoSentMail

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
处理已发送的邮件。
  
```cpp
HRESULT DoSentMail(
  ULONG ulFlags,
  LPMESSAGE lpMessage
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _lpMessage_
  
> 实时指向打开邮件的指针, 该邮件应在指定用于保存已发送邮件的文件夹中生成。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

**IMAPISupport::D osentmail**方法是为邮件存储提供程序支持对象而实现的。 邮件存储提供程序从其[IMsgStore:: FinishedMsg](imsgstore-finishedmsg.md)方法的实现调用**DoSentMail** , 这是在处理完邮件后由 MAPI 后台处理程序调用的。 **FinishedMsg**解除锁定邮件, 确保邮件的引用计数为 1, 并调用**DoSentMail**。
  
 **DoSentMail**执行以下任务: 
  
- 检查**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性的邮件, 以确定是否应在发送后删除该邮件。
    
- 确定 "已发送邮件" 文件夹的位置。
    
- 为 "已发送邮件" 文件夹上设置的任何挂接启动邮件挂钩处理。
    
- 将邮件移至 "已发送邮件" 文件夹、"已删除邮件" 文件夹或其他文件夹。
    
- 释放邮件。
    
## <a name="see-also"></a>另请参阅



[IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)
  
[PidTagDeleteAfterSubmit 规范属性](pidtagdeleteaftersubmit-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

