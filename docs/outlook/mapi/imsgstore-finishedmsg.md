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
  
> [in]保留;必须为零。
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向要处理的邮件的条目标识符的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功处理已发送的邮件。
    
MAPI_E_NO_SUPPORT 
  
> 邮件存储提供程序不支持已发送的邮件处理。 如果调用方不是 MAPI 后台处理程序，则返回此错误值。
    
## <a name="remarks"></a>备注

**IMsgStore：：FinishedMsg** 方法对已发送的邮件执行处理。 此处理过程可能涉及删除邮件、将其移动到其他文件夹或执行这两项操作。 处理类型取决于是否设置 **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 和 **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在 **FinishedMsg 的** 实现中，解锁由  _lpEntryID_ 标识的邮件并执行相应的处理。 目标邮件将始终被锁定;MAPI 后台处理程序从不将未锁定邮件的条目标识符传递给 **FinishedMsg**。
  
两者 **可能PR_DELETE_AFTER_SUBMIT** 或PR_SENTMAIL_ENTRYID设置，或设置其中一个或另一个。 下表介绍了基于设置应执行的操作： 
  
|||
|:-----|:-----|
|如果两个属性都未设置：  <br/> |将邮件留在从其中发送邮件的文件夹中 (通常是发件箱) 。  <br/> |
|如果同时设置了这两个属性：  <br/> |如果需要，将邮件移动到指示的文件夹，然后将其删除。  <br/> |
|如果PR_SENTMAIL_ENTRYID设置：  <br/> |将邮件移动到指示的文件夹。  <br/> |
|如果PR_DELETE_AFTER_SUBMIT设置：  <br/> |删除邮件。  <br/> |
   
执行任何适当的操作后，调用 [IMAPISupport：:D oSentMail](imapisupport-dosentmail.md) 方法。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::DoSentMail](imapisupport-dosentmail.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

