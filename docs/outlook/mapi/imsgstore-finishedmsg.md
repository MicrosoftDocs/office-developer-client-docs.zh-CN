---
title: IMsgStoreFinishedMsg
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.FinishedMsg
api_type:
- COM
ms.assetid: c32493fa-aa42-485b-9ea4-f93b835906df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e7d7ba91791258eca93a2b8bedf95cf121062c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427085"
---
# <a name="imsgstorefinishedmsg"></a>IMsgStore::FinishedMsg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使邮件存储提供程序能够对已发送的邮件执行处理。 此方法仅由 MAPI 后台处理程序调用。
  
```cpp
HRESULT FinishedMsg(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向要处理的邮件的条目标识符的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 对已发送邮件的处理已成功。
    
MAPI_E_NO_SUPPORT 
  
> 邮件存储区提供程序不支持发送的邮件处理。 如果调用方不是 MAPI 后台处理程序, 将返回此错误值。
    
## <a name="remarks"></a>说明

**IMsgStore:: FinishedMsg**方法对已发送的邮件执行处理。 此处理可能涉及删除邮件、将邮件移动到其他文件夹或两种操作。 处理的类型取决于是否设置了**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 和**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在**FinishedMsg**的实现中, 解锁_lpEntryID_标识的邮件并执行相应的处理。 目标邮件将始终处于锁定状态;MAPI 后台处理程序从不将未锁定邮件的条目标识符传递给**FinishedMsg**。
  
**PR_DELETE_AFTER_SUBMIT**或**PR_SENTMAIL_ENTRYID**的设置可能既不是已设置的, 也可能是一个或另一个设置。 下表描述了应基于设置执行的操作: 
  
|||
|:-----|:-----|
|如果两个属性都不设置:  <br/> |将邮件保留在发送邮件的文件夹中 (通常为 "发件箱")。  <br/> |
|如果同时设置这两个属性:  <br/> |如果需要, 将邮件移至指定的文件夹, 然后将其删除。  <br/> |
|如果设置了 PR_SENTMAIL_ENTRYID:  <br/> |将邮件移动到指定的文件夹。  <br/> |
|如果设置了 PR_DELETE_AFTER_SUBMIT:  <br/> |删除邮件。  <br/> |
   
采取任何适合的操作后, 请调用[IMAPISupport::D osentmail](imapisupport-dosentmail.md)方法。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::DoSentMail](imapisupport-dosentmail.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

