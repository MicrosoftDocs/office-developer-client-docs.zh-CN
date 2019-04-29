---
title: IMAPIFolderGetMessageStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.GetMessageStatus
api_type:
- COM
ms.assetid: 3ddbb129-5d6b-4eca-aba0-3620609ed0c1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 621c20376cc671a2ff9d1406bfb6248846e1bc81
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418636"
---
# <a name="imapifoldergetmessagestatus"></a>IMAPIFolder::GetMessageStatus

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
获取与特定文件夹中的邮件相关联的状态 (例如, 是否将该邮件标记为删除)。
  
```cpp
HRESULT GetMessageStatus(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags,
  ULONG FAR * lpulMessageStatus
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向已获取其状态的邮件的条目标识符的指针。
    
 _ulFlags_
  
> 实时保留必须为零。
    
 _lpulMessageStatus_
  
> 排除指向指示邮件状态的标志位掩码的指针。 0到15位是保留的, 并且必须为零。16到31位可用于特定于实现的用途。 可以设置以下标志:
    
MSGSTATUS_DELMARKED 
  
> 邮件已被标记为删除。
    
MSGSTATUS_HIDDEN 
  
> 不显示该邮件。 
    
MSGSTATUS_HIGHLIGHTED 
  
> 将突出显示该消息。
    
MSGSTATUS_REMOTE_DELETE 
  
> 已将邮件标记为在远程邮件存储库中删除, 而不会将其下载到本地客户端。
    
MSGSTATUS_REMOTE_DOWNLOAD 
  
> 已将邮件标记为从远程邮件存储下载到本地客户端。
    
MSGSTATUS_TAGGED 
  
> 已针对客户端定义的目的对邮件进行了标记。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索邮件状态。
    
## <a name="remarks"></a>说明

**IMAPIFolder:: GetMessageStatus**方法返回邮件的状态。 邮件状态存储在邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如何设置、清除和使用邮件状态位完全取决于您的实现, 只保留0到15位, 并且必须为零。 如果将邮件存储在 IPM 子树中, MAPI 将保留位16到31以供 IPM 客户端使用。 如果将邮件存储在其他子树中, 则可以使用 bits 16 到31来实现自己的目的。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer  <br/> |CMyMAPIFormViewer:: GetNextMessage  <br/> |MFCMAPI 使用**IMAPIFolder:: GetMessageStatus**方法获取要显示的下一封邮件的状态。  <br/> |
|MAPIFormFunctions  <br/> |OpenMessageNonModal 和 OpenMessageModal  <br/> |MFCMAPI 使用**IMAPIFolder:: GetMessageStatus**方法获取要显示的消息的状态, 以传递给表单查看器, 即 CMyMAPIFormViewer 或[IMAPISession:: ShowForm](imapisession-showform.md)。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md)
  
[IMAPISession::ShowForm](imapisession-showform.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

