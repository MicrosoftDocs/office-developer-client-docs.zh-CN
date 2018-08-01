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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d8f28a6b0a1633b0060f02af7e38ef058527eb24
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775419"
---
# <a name="imapiformmgrisinconflict"></a>IMAPIFormMgr::IsInConflict

  
  
**适用于**： Outlook 
  
确定窗体是否可以处理其自己的邮件冲突。 如果已通过多个用户同时编辑邮件有冲突。 这可能对公用文件夹中的邮件。
  
```cpp
HRESULT IsInConflict(
  ULONG ulMessageFlags,
  ULONG ulMessageStatus,
  LPCSTR szMessageClass LPMAPIFOLDER pFolderFocus
);
```

## <a name="parameters"></a>参数

 _ulMessageFlags_
  
> [in]一个指向标志从一条消息，指示邮件的当前状态的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的位掩码。
    
 _ulMessageStatus_
  
> [in]复制从一条消息，提供有关状态的消息的附加信息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性的客户端或提供程序定义标志的位掩码。
    
 _szMessageClass_
  
> [in]命名邮件的邮件类的字符串。
    
 _pFolderFocus_
  
> [in]一个指向包含邮件的文件夹。 _PFolderFocus_参数可以是 NULL，如果这样的文件夹不存在 （例如，如果邮件嵌入到另一条消息）。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 窗体并不处理其自己的邮件冲突。
    
S_FALSE 
  
> 窗体处理自己消息冲突，或为其传递信息消息不存在冲突。
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIFormMgr::IsInConflict**方法来发现是否特定窗体并不处理其自己的邮件冲突。 **IsInConflict**检查存在冲突标志_ulMessageFlags_和_ulMessageStatus_参数中的位掩码。 如果设置冲突标志， **IsInConflict**解析_szMessageClass_参数中传递的邮件类和如果窗体不处理其自己的冲突，则返回 S_OK。 如果表单处理自己冲突， **IsInConflict**返回 S_FALSE。 
  
并不处理其自己的冲突的窗体必须使用[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)方法打开和无法重用现有的窗体对象。 
  
## <a name="notes-to-callers"></a>给调用方的说明

客户端应用程序通常必须时应用程序将从一个邮件移动到文件夹中的下一页或上一页邮件处理冲突。 如果邮件是冲突，但该消息的窗体服务器可以处理冲突，客户端应用程序应执行用于显示的下一页或上一页消息其往常代码。 如果窗体服务器无法处理冲突，就好像它，下一页或上一页邮件的邮件类不知道应继续客户端应用程序。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormAdviseSink::OnActivateNext](imapiformadvisesink-onactivatenext.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

