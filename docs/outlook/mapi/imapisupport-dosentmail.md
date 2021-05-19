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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423949"
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
  
> [in]保留;必须为零。
    
 _lpMessage_
  
> [in]指向打开邮件的指针，邮件应在指定用于保留已发送项目的文件夹中生成。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

**IMAPISupport：:D oSentMail** 方法为邮件存储提供程序支持对象实现。 邮件存储提供程序通过 [实现 IMsgStore：：FinishedMsg](imsgstore-finishedmsg.md)方法调用 **DoSentMail，MAPI** 后台处理程序在处理完邮件后将调用此方法。 **FinishedMsg** 解锁邮件，确保邮件的引用计数为 1，并调用 **DoSentMail**。
  
 **DoSentMail** 执行以下任务： 
  
- 检查[PidTagDeleteAfterSubmit PR_DELETE_AFTER_SUBMIT (PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)属性) 邮件发送后是否应该删除该邮件。 
    
- 确定"已发送项目"文件夹的位置。
    
- 启动"已发送项目"文件夹上设置的任何挂钩的邮件挂钩处理。
    
- 将邮件移动到"已发送的项目"文件夹、"已删除邮件"文件夹或其他文件夹。
    
- 释放邮件。
    
## <a name="see-also"></a>另请参阅



[IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)
  
[PidTagDeleteAfterSubmit 规范属性](pidtagdeleteaftersubmit-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

