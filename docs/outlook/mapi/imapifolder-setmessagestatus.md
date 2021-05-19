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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417271"
---
# <a name="imapifoldersetmessagestatus"></a>IMAPIFolder::SetMessageStatus

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置与邮件相关联的状态 (例如，是否将邮件标记为删除) 。
  
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
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向状态已设置的邮件的条目标识符的指针。
    
 _ulNewStatus_
  
> [in]要分配的新状态。 
    
 _ulNewStatusMask_
  
> [in]应用于新状态并指示要设置的标志的位掩码。 可以设置以下标志：
    
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
    
 _lpulOldStatus_
  
> [out]指向邮件以前的状态的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置邮件状态。
    
## <a name="remarks"></a>备注

**IMAPIFolder：：SetMessageStatus** 方法将邮件状态设置为存储在 **其 PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性的值。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

消息状态位的设置、清除和使用方式完全取决于您的实现，除了保留 0 到 15 位，并且必须为零。 
  
远程传输提供程序的此方法实现必须遵循此处所述的语义。 没有特别注意事项。 客户端使用此方法来设置MSGSTATUS_REMOTE_DOWNLOAD MSGSTATUS_REMOTE_DELETE位，以指示将从远程邮件存储下载或删除特定邮件。 远程传输提供程序无需实现相关的 [IMAPIFolder：：GetMessageStatus](imapifolder-getmessagestatus.md) 方法。 客户端必须查看文件夹的内容表以确定邮件的状态。 
  
## <a name="notes-to-callers"></a>给调用方的说明

可以使用邮件的 **PR_MSG_STATUS** 属性与其他客户端协商邮件锁定操作。 将位指定为锁定位。 若要确定是否设置了锁定位，请检查  _lpulOldStatus_ 参数中邮件状态的上一个值。 使用  _ulNewStatus_ 参数中的其他位跟踪邮件状态，而不会影响锁定位。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)

