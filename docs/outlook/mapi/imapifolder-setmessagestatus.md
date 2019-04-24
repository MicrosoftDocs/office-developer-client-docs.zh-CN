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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fbb05efff67fa90c68db86249d4657e489e7bd63
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342775"
---
# <a name="imapifoldersetmessagestatus"></a>IMAPIFolder::SetMessageStatus

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置与邮件关联的状态 (例如, 是否将该邮件标记为要删除)。
  
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
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向其状态为设置的邮件的条目标识符的指针。
    
 _ulNewStatus_
  
> 实时要分配的新状态。 
    
 _ulNewStatusMask_
  
> 实时应用于新状态并指示要设置的标志的标志的位掩码。 可以设置以下标志:
    
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
    
 _lpulOldStatus_
  
> 排除指向邮件的上一个状态的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置邮件状态。
    
## <a name="remarks"></a>注解

**IMAPIFolder:: SetMessageStatus**方法将邮件状态设置为存储在其**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中的值。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如何设置、清除和使用邮件状态位完全取决于您的实现, 只保留0到15位, 并且必须为零。 
  
此方法的远程传输提供程序的实现必须遵循此处所述的语义。 没有特殊的注意事项。 客户端使用此方法来设置 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 位, 以指示要从远程邮件存储中下载或删除特定邮件。 远程传输提供程序无需实现相关的[IMAPIFolder:: GetMessageStatus](imapifolder-getmessagestatus.md)方法。 客户端必须在文件夹的内容表中查找, 以确定邮件的状态。 
  
## <a name="notes-to-callers"></a>给调用方的说明

可以使用邮件的**PR_MSG_STATUS**属性将邮件锁定操作与其他客户端进行协商。 将一个位指定为锁定位。 若要确定是否设置了锁定位, 请在_lpulOldStatus_参数中检查邮件状态的以前的值。 使用_ulNewStatus_参数中的其他位跟踪邮件状态, 而不影响锁定位。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)

