---
title: IMsgStoreAbortSubmit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.AbortSubmit
api_type:
- COM
ms.assetid: 9be6b88e-2510-4b82-8b35-5f20a0f99fc0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e2871f5804cda172328fbd3ebdc43f860de939ab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775876"
---
# <a name="imsgstoreabortsubmit"></a>IMsgStore::AbortSubmit

  
  
**适用于**： Outlook 
  
尝试从传出队列中删除一条消息。
  
```cpp
AbortSubmit(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要从传出队列中移除的消息的项标识符的指针。 
    
 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功删除传出队列中。
    
MAPI_E_NOT_IN_QUEUE 
  
> 由_lpEntryID_标识邮件不再在传出队列中的消息存储，通常是因为已发送。 
    
MAPI_E_UNABLE_TO_ABORT 
  
> 由_lpEntryID_标识邮件已被锁定通过 MAPI 后台处理程序，且不能中止操作。 
    
## <a name="remarks"></a>说明

**IMsgStore::AbortSubmit**方法尝试删除的消息存储传出队列中的已提交的邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

邮件提交后，通过调用**AbortSubmit**中止提交是唯一可以对邮件执行的操作。 不希望**AbortSubmit**总是成功。 根据实现基础邮件系统的方式，它可能不是邮件的可以取消发送。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolderDlg::OnAbortSubmit  <br/> |MFCMAPI 使用**IMsgStore::AbortSubmit**方法中止的所选消息提交。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

