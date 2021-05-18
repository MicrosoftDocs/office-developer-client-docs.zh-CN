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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412882"
---
# <a name="imapiformmgrisinconflict"></a>IMAPIFormMgr::IsInConflict

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定表单是否可以处理自己的邮件冲突。 如果邮件已由多个用户同时编辑，则邮件存在冲突。 公用文件夹中的邮件可能会发生这种情况。
  
```cpp
HRESULT IsInConflict(
  ULONG ulMessageFlags,
  ULONG ulMessageStatus,
  LPCSTR szMessageClass LPMAPIFOLDER pFolderFocus
);
```

## <a name="parameters"></a>参数

 _ulMessageFlags_
  
> [in]指向从邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志的位掩码的指针，指示邮件的当前状态。
    
 _ulMessageStatus_
  
> [in]从邮件的 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制的客户端定义或提供程序定义标志的位掩码，提供有关邮件状态的其他信息。
    
 _szMessageClass_
  
> [in]一个字符串，用于命名邮件的邮件类。
    
 _pFolderFocus_
  
> [in]指向包含邮件的文件夹的指针。 如果  _不存在此类文件夹，pFolderFocus_ 参数可以是 NULL (例如，如果邮件嵌入另一个邮件) 。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单不处理自己的邮件冲突。
    
S_FALSE 
  
> 表单处理自己的邮件冲突，或者传递信息的邮件没有冲突。
    
## <a name="remarks"></a>备注

表单查看者调用 **IMAPIFormMgr：：IsInConflict** 方法来发现特定表单是否不处理其自己的邮件冲突。 **IsInConflict** 检查  _ulMessageFlags_ 和  _ulMessageStatus_ 参数中的位掩码是否存在冲突标志。 如果设置了冲突标志 **，IsInConflict** 将解析  _在 szMessageClass_ 参数中传递的邮件类，如果S_OK不处理自己的冲突，则返回 S_OK。 **如果表单处理S_FALSE，则 IsInConflict** 返回 S_FALSE。 
  
不处理其自身的冲突的表单必须使用 [IMAPIFormMgr：：LoadForm](imapiformmgr-loadform.md) 方法打开，并且不能重复使用现有的表单对象。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当应用程序从一封邮件移动到文件夹中的下一封邮件或上一封邮件时，客户端应用程序通常必须处理冲突。 如果邮件存在冲突，但该邮件的窗体服务器可以处理冲突，则客户端应用程序应执行其用于显示下一封邮件或上一封邮件的常用代码。 如果表单服务器无法处理冲突，则客户端应用程序应继续，就像不知道下一封邮件或上一封邮件的邮件类一样。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormAdviseSink::OnActivateNext](imapiformadvisesink-onactivatenext.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

