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
ms.openlocfilehash: 1486730dfa2d76bf8e97439213851b195504962f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414380"
---
# <a name="imsgstoreabortsubmit"></a>IMsgStore::AbortSubmit

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
尝试从传出队列中删除邮件。
  
```cpp
AbortSubmit(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向要从传出队列中删除的邮件的条目标识符的指针。 
    
 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功从传出队列中删除。
    
MAPI_E_NOT_IN_QUEUE 
  
> _lpEntryID_ 标识的邮件不再位于邮件存储的传出队列中，通常是因为它已发送。 
    
MAPI_E_UNABLE_TO_ABORT 
  
> _lpEntryID_ 标识的邮件被 MAPI 后台处理程序锁定，操作无法中止。 
    
## <a name="remarks"></a>备注

**IMsgStore：：AbortSubmit** 方法尝试从邮件存储的传出队列中删除已提交的邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

提交邮件后，通过调用 **AbortSubmit** 中止提交是可以在邮件上执行的唯一操作。 不要期望 **AbortSubmit** 始终成功。 根据基础邮件系统的实现方式，可能无法取消邮件发送。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolderDlg：：OnAbortSubmit  <br/> |MFCMAPI 使用 **IMsgStore：：AbortSubmit** 方法中止提交所选邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

