---
title: IMAPIFolderSetMessageStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.SetMessageStatus
api_type:
- COM
ms.assetid: 42ffbbe0-d678-474a-a016-91c71255613e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fcca6a7e8fa70a2df9042e8b3c2b28825cee9a7b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775370"
---
# <a name="imapifoldersetmessagestatus"></a>IMAPIFolder::SetMessageStatus

  
  
**适用于**： Outlook 
  
设置 （例如，无论该邮件被标记为删除） 与消息关联的状态。
  
```cpp
HRESULT SetMessageStatus(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulNewStatus,
  ULONG ulNewStatusMask,
  ULONG FAR * lpulOldStatus
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向其状态设置消息的项标识符的指针。
    
 _ulNewStatus_
  
> [in]要分配的新状态。 
    
 _ulNewStatusMask_
  
> [in]位掩码的标志应用于新的状态，并表示要设置的标志。 可以设置以下标志：
    
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
    
 _lpulOldStatus_
  
> [输出]一个指向邮件的以前的状态。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置邮件状态。
    
## <a name="remarks"></a>说明

**IMAPIFolder::SetMessageStatus**方法将邮件状态设置为在其**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中存储的值。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如何设置、 清除状态，以及使用消息状态位完全取决于您的实现，只不过 0 到 15 位保留，必须为零。 
  
远程传输提供程序实现此方法必须遵循此处所述的语义。 没有任何特殊的注意事项。 客户端使用此方法可设置 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 二进制文件，以指明要下载或从远程邮件存储区删除特定的消息。 远程传输提供程序没有实现相关的[IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md)方法。 若要确定一条消息，状态的文件夹的内容表中必须查找客户端。 
  
## <a name="notes-to-callers"></a>给调用方的说明

一条消息的**PR_MSG_STATUS**属性可用于协商与其他客户端的消息锁定操作。 将指定有点为锁定位。 若要确定是否已设置的锁定位，请检查_lpulOldStatus_参数中的邮件状态的以前值。 使用_ulNewStatus_参数中其他位而不会干扰锁定位跟踪消息状态。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)

