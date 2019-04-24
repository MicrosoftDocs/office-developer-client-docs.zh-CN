---
title: IMessageSetReadFlag
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.SetReadFlag
api_type:
- COM
ms.assetid: 2d02ebf6-bb8b-42bb-9bd0-870dbae9aeb4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 874dba4aa18190792a52e29064155f5afa0ef44d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349264"
---
# <a name="imessagesetreadflag"></a>IMessage::SetReadFlag

**适用于**：Outlook 2013 | Outlook 2016 
  
设置或清除邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的 MSGFLAG_READ 标记, 并管理阅读报告的发送。
  
```cpp
HRESULT SetReadFlag(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

_ulFlags_
  
> 实时标志的位掩码, 用于控制邮件的阅读标志的设置, 即邮件的 MSGFLAG_READ 标记在其**PR_MESSAGE_FLAGS**属性和处理读取报告。 可以设置以下标志: 
    
  - CLEAR_READ_FLAG: 应在**PR_MESSAGE_FLAGS**中清除 MSGFLAG_READ 标志, 并且不应发送任何读取报告。 
      
  - CLEAR_NRN_PENDING: 应在**PR_MESSAGE_FLAGS**中清除 MSGFLAG_NRN_PENDING 标志, 且不应发送不阅读的报告。 
      
  - CLEAR_RN_PENDING: 应在**PR_MESSAGE_FLAGS**中清除 MSGFLAG_RN_PENDING 标志, 并且不应发送任何读取报告。 
      
  - GENERATE_RECEIPT_ONLY: 应在一个已挂起的情况下发送已读报告, 但在 MSGFLAG_READ 标志的状态中不应进行任何更改。
      
  - MAPI_DEFERRED_ERRORS: 允许**SetReadFlag**成功返回, 可能在操作完成前。 
      
  - SUPPRESS_RECEIPT: 如果已请求读取报告且此呼叫将邮件的状态从 "未读" 更改为 "已读", 则应取消挂起的读取报告。 如果此调用不更改邮件的状态, 则邮件存储提供程序可以忽略此标志。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置或清除邮件的读取标志。
    
MAPI_E_NO_SUPPRESS 
  
> 邮件存储区提供程序不支持禁止显示已读报告。
    
MAPI_E_INVALID_PARAMETER 
  
> 在_ulFlags_参数中设置以下标志组合中的一种: 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
   - CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
## <a name="remarks"></a>注解

**IMessage:: SetReadFlag**方法设置或清除**PR_MESSAGE_FLAGS**属性中的邮件的 MSGFLAG_READ 标记, 并调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)以保存该邮件。 设置 MSGFLAG_READ 标志将邮件标记为已阅读, 这并不一定表明预期收件人确实已阅读邮件。 
  
**SetReadFlags**还管理阅读报告的发送。 仅当发件人请求了一个阅读报告时, 才会发送该报告。 
  
无法为以下项更改读取标志:
  
- 不存在的邮件。
    
- 已移动到其他位置的邮件。
    
- 以读/写权限打开的邮件。
    
- 当前已提交的邮件。
    
## <a name="notes-to-callers"></a>给调用方的说明

如果未在_ulFlags_参数中设置任何标志, 则以下规则适用: 
  
- 如果已设置 MSGFLAG_READ, 则不执行任何操作。
    
- 如果未设置 MSGFLAG_READ, 则设置它并发送任何挂起的读取报告 (如果设置了**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性)。
    
如果同时设置了 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志, 则应清除 PR_READ_RECEIPT_REQUESTED 位, 如果设置, 则不应发送读取报告。
  
设置 SUPPRESS_RECEIPT 标志时:
  
- 如果已设置 MSGFLAG_READ, 则不执行任何操作。 
    
- 如果未设置 MSGFLAG_READ, 请将其设置并取消任何待执行的已读报告。
    
设置 CLEAR_READ_FLAG 标志后, 清除每个邮件的**PR_MESSAGE_FLAGS**属性中的 MSGFLAG_READ 标记, 而不发送任何已读报告。 
  
设置 GENERATE_RECEIPT_ONLY 标志后, 发送任何挂起的读取报告。 请勿设置或清除 MSGFLAG_READ。
  
如果设置了 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志, 则将 PR_READ_RECEIPT_REQUESTED 属性设置为 FALSE, 如果设置了该属性, 但不发送已读报告。
  
您可以通过在特定条件下禁止生成阅读报告来优化报告行为。 但是, 如果您不支持禁止显示报告和客户端调用**SetReadFlag**并设置 SUPPRESS_RECEIPT 标志, 则返回 MAPI_E_NO_SUPPRESS。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg  <br/> |CFolderDlg:: OnSetReadFlag  <br/> |MFCMAPI 使用**IMessage:: SetReadFlag**方法来设置所选邮件上的读取标志。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)  
- [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)  
- [IMAPIProp::GetProps](imapiprop-getprops.md)  
- [IMAPIProp::SaveChanges](imapiprop-savechanges.md) 
- [PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md) 
- [IMessage : IMAPIProp](imessageimapiprop.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

