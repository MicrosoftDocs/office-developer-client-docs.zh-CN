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
ms.openlocfilehash: 8b15f12c9a7ac2041c895b935098f9681e4b3a3c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589950"
---
# <a name="imsgstorefinishedmsg"></a>IMsgStore::FinishedMsg

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
启用对已发送的邮件执行处理的消息存储提供程序。 只能通过 MAPI 后台处理程序调用此方法。
  
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
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要处理的消息的项标识符的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 在已发送的邮件处理成功。
    
MAPI_E_NO_SUPPORT 
  
> 消息存储提供程序不支持已发送的邮件处理。 如果呼叫者不是 MAPI 后台处理程序，则返回此错误值。
    
## <a name="remarks"></a>注解

**IMsgStore::FinishedMsg**方法对已发送的邮件执行处理。 此过程可涉及删除邮件，并将其移动到另一个文件夹或两种操作。 处理的类型取决于是否设置**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 和**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

**FinishedMsg**在实现，解除锁定邮件由_lpEntryID_标识，并执行相应的处理。 目标邮件总是被锁定;MAPI 后台处理程序永远不会将解除锁定的消息的项标识符传递给**FinishedMsg**。
  
很可能，既不设置**PR_DELETE_AFTER_SUBMIT**或**PR_SENTMAIL_ENTRYID** 、 两者都设置，或设置一个或另一个。 下表介绍您应执行的操作基于在设置: 
  
|||
|:-----|:-----|
|如果既属性设置：  <br/> |将邮件保留从中发送 （通常发件箱） 的文件夹中。  <br/> |
|如果设置两个属性：  <br/> |将邮件移动到指定的文件夹中，如果需要，并将其删除。  <br/> |
|如果设置 PR_SENTMAIL_ENTRYID:  <br/> |将邮件移动到指定的文件夹。  <br/> |
|如果设置 PR_DELETE_AFTER_SUBMIT:  <br/> |删除邮件。  <br/> |
   
您已采取任何操作适合后，调用[IMAPISupport::DoSentMail](imapisupport-dosentmail.md)方法。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::DoSentMail](imapisupport-dosentmail.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

