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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 82490dbe597ebd3f7198aa7e0c904a10202ecd77
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568208"
---
# <a name="imapisupportdosentmail"></a>IMAPISupport::DoSentMail

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]一个指向打开的邮件中应为其在指定用于保存已发送的邮件文件夹中生成一条消息。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

消息存储提供程序支持对象的实现**IMAPISupport::DoSentMail**方法。 消息存储提供程序调用**DoSentMail**与[IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)方法，该处理一条消息完成 MAPI 后台处理程序调用方法的实现。 **FinishedMsg**解除对邮件、 确保消息的引用计数为 1，且调用**DoSentMail**。
  
 **DoSentMail**执行以下任务： 
  
- 检查**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性，以确定是否应发送后删除邮件的邮件。
    
- 确定发送邮件文件夹的位置。
    
- 启动的已发送邮件文件夹上设置任何挂接处理的消息挂钩。
    
- 将邮件移动到已发送邮件文件夹中，已删除邮件文件夹或另一个文件夹。
    
- 发布消息。
    
## <a name="see-also"></a>另请参阅



[IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)
  
[PidTagDeleteAfterSubmit 规范属性](pidtagdeleteaftersubmit-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

