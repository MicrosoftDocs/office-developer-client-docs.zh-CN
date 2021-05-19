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
  
获取与特定文件夹中的邮件相关联的状态 (例如，是否将邮件标记为删除) 。
  
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
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向获取其状态的邮件的条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulMessageStatus_
  
> [out]指向指示邮件状态的位掩码标志的指针的指针。 保留 0 到 15 位，并且必须为零;位 16 到 31 可用于实现特定用途。 可以设置以下标志：
    
MSGSTATUS_DELMARKED 
  
> 邮件已标记为删除。
    
MSGSTATUS_HIDDEN 
  
> 不显示消息。 
    
MSGSTATUS_HIGHLIGHTED 
  
> 邮件将突出显示。
    
MSGSTATUS_REMOTE_DELETE 
  
> 邮件已在远程邮件存储中标记为删除，无需下载到本地客户端。
    
MSGSTATUS_REMOTE_DOWNLOAD 
  
> 邮件已标记为从远程邮件存储下载到本地客户端。
    
MSGSTATUS_TAGGED 
  
> 邮件已标记为客户端定义。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索邮件状态。
    
## <a name="remarks"></a>备注

**IMAPIFolder：：GetMessageStatus** 方法返回消息的状态。 邮件状态存储在邮件的邮件PR_MSG_STATUS ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性。  
  
## <a name="notes-to-implementers"></a>针对实现者的说明

消息状态位的设置、清除和使用方式完全取决于您的实现，除了保留 0 到 15 位，并且必须为零。 如果将邮件存储在 IPM 子树中，MAPI 将保留 16 位到 31 位，供 IPM 客户端使用。 如果将邮件存储在其他子树中，可以使用位 16 到 31 来达到自己的目的。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：GetNextMessage  <br/> |MFCMAPI 使用 **IMAPIFolder：：GetMessageStatus** 方法获取要显示的下一条消息的状态。  <br/> |
|MAPIFormFunctions.cpp  <br/> |OpenMessageNonModal 和 OpenMessageModal  <br/> |MFCMAPI 使用 **IMAPIFolder：：GetMessageStatus** 方法获取要显示的消息的状态以传递到表单查看器，即 CMyMAPIFormViewer 或 [IMAPISession：：ShowForm](imapisession-showform.md)。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md)
  
[IMAPISession::ShowForm](imapisession-showform.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

