---
title: IMAPIFormMgrIsInConflict
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgrIsInConflict
api_type:
- COM
ms.assetid: 5ca86ee8-1bf6-4ec8-95b3-575c22fbb170
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 87432d8982c5dc1f64396187739e97314edb385c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321845"
---
# <a name="imapiformmgrisinconflict"></a>IMAPIFormMgr::IsInConflict

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定表单是否可以处理自己的邮件冲突。 如果有多个用户同时编辑邮件, 则邮件发生冲突。 公用文件夹中的邮件可能会发生这种情况。
  
```cpp
HRESULT IsInConflict(
  ULONG ulMessageFlags,
  ULONG ulMessageStatus,
  LPCSTR szMessageClass LPMAPIFOLDER pFolderFocus
);
```

## <a name="parameters"></a>参数

 _ulMessageFlags_
  
> 实时指向从消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志位掩码的指针, 该消息指示邮件的当前状态。
    
 _ulMessageStatus_
  
> 实时从邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中复制的客户端定义或提供程序定义的标志的位掩码, 它提供有关邮件状态的其他信息。
    
 _szMessageClass_
  
> 实时一个用于命名邮件的邮件类的字符串。
    
 _pFolderFocus_
  
> 实时指向包含邮件的文件夹的指针。 如果不存在这样的文件夹 (例如, 如果邮件嵌入在另一封邮件中), _pFolderFocus_参数可以为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单不会处理自己的邮件冲突。
    
S_FALSE 
  
> 该表单处理自己的邮件冲突, 或者信息传递的邮件未发生冲突。
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormMgr:: IsInConflict**方法, 以发现特定表单是否未处理自己的邮件冲突。 **IsInConflict**检查_ulMessageFlags_和_ulMessageStatus_参数中的位掩码是否存在冲突标志。 如果设置了冲突标志, **IsInConflict**将解析在_szMessageClass_参数中传递的邮件类, 如果窗体不处理自己的冲突, 则返回 S_OK。 如果窗体处理自己的冲突, **IsInConflict**将返回 S_FALSE。 
  
必须使用[IMAPIFormMgr:: LoadForm](imapiformmgr-loadform.md)方法打开不处理自己的冲突的窗体, 并且无法重用现有的 form 对象。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当应用程序从文件夹中的一封邮件移动到下一封邮件或上一封邮件时, 客户端应用程序通常需要处理冲突。 如果邮件发生冲突, 但该邮件的表单服务器可以处理冲突, 则客户端应用程序应执行通常的代码以显示下一条或上一封邮件。 如果窗体服务器无法处理冲突, 客户端应用程序应继续进行, 就像它不知道下一条或上一封邮件的邮件类一样。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormAdviseSink::OnActivateNext](imapiformadvisesink-onactivatenext.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

