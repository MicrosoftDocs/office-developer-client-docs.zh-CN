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
ms.openlocfilehash: bac363183c15a2d53c15b46724266b6cb5744075
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775359"
---
# <a name="imapifoldergetmessagestatus"></a>IMAPIFolder::GetMessageStatus

  
  
**适用于**： Outlook 
  
获取与特定的文件夹中的邮件 （例如，无论该邮件被标记为删除） 的状态。
  
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
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向获得其状态的消息的项标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulMessageStatus_
  
> [输出]指向指示邮件的状态标志的位掩码的指针的指针。 0 到 15 位保留，必须为零;位到 31 16 是可用于特定于实现的。 可以设置以下标志：
    
MSGSTATUS_DELMARKED 
  
> 邮件已标记为删除。
    
MSGSTATUS_HIDDEN 
  
> 邮件是不显示。 
    
MSGSTATUS_HIGHLIGHTED 
  
> 邮件是显示突出显示。
    
MSGSTATUS_REMOTE_DELETE 
  
> 邮件已标记为删除远程邮件存储在无须下载到本地客户端。
    
MSGSTATUS_REMOTE_DOWNLOAD 
  
> 已从远程邮件存储下载到本地客户端标记邮件。
    
MSGSTATUS_TAGGED 
  
> 邮件已标记的客户端定义用途。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索邮件状态。
    
## <a name="remarks"></a>说明

**IMAPIFolder::GetMessageStatus**方法返回一条消息，的状态。 邮件状态存储在消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如何设置、 清除状态，以及使用消息状态位完全取决于您的实现，只不过 0 到 15 位保留，必须为零。 如果将消息存储 IPM 子树中，MAPI 保留 IPM 客户端通过使用 31 16 位。 如果将消息存储在其他子树中，您可用于通过 31 16 位自己的目的。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::GetNextMessage  <br/> |MFCMAPI 使用**IMAPIFolder::GetMessageStatus**方法来获取的状态将显示下一条消息。  <br/> |
|MAPIFormFunctions.cpp  <br/> |OpenMessageNonModal 和 OpenMessageModal  <br/> |MFCMAPI 使用**IMAPIFolder::GetMessageStatus**方法来获取要传递给表单查看器中，即 CMyMAPIFormViewer 或[IMAPISession::ShowForm](imapisession-showform.md)要显示的消息的状态。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md)
  
[IMAPISession::ShowForm](imapisession-showform.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

