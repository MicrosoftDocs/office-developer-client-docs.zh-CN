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
ms.openlocfilehash: 0ae35166f01f597c2c3ab399a1b66e5760ab0dc8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775765"
---
# <a name="imessagesetreadflag"></a>IMessage::SetReadFlag

**适用于**： Outlook 
  
设置或清除 MSGFLAG_READ 标志邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中并管理阅读报告的发送。
  
```cpp
HRESULT SetReadFlag(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

_ulFlags_
  
> [in]控制的消息的读取设置的标志位掩码，即标记其**PR_MESSAGE_FLAGS**属性和处理阅读报告中的邮件的 MSGFLAG_READ 标志。 可以设置以下标志： 
    
  - CLEAR_READ_FLAG： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_READ 标志，但应发送未读取的报告。 
      
  - CLEAR_NRN_PENDING： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_NRN_PENDING 标志，不应发送未读报告。 
      
  - CLEAR_RN_PENDING： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_RN_PENDING 标志，但应发送未读取的报告。 
      
  - GENERATE_RECEIPT_ONLY： 应发送读取的报表，如果一个处于挂起状态，但不应 MSGFLAG_READ 标志的状态发生任何变化。
      
  - MAPI_DEFERRED_ERRORS： 允许**SetReadFlag**返回成功，原因可能是完成此操作之前。 
      
  - SUPPRESS_RECEIPT： 应取消挂起的阅读的报告，如果阅读的报告已被请求，并且此呼叫将从未读读取更改邮件的状态。 如果此呼叫不会更改邮件的状态，消息存储提供程序可以忽略此标志。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置或清除邮件的阅读的标志。
    
MAPI_E_NO_SUPPRESS 
  
> 消息存储提供程序不支持阅读报告的禁止显示。
    
MAPI_E_INVALID_PARAMETER 
  
> _UlFlags_参数中设置以下标志的组合之一： 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
   - CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
## <a name="remarks"></a>说明

**IMessage::SetReadFlag**方法设置或清除**PR_MESSAGE_FLAGS**属性和呼叫[IMAPIProp::SaveChanges](imapiprop-savechanges.md)保存邮件中的消息的 MSGFLAG_READ 标志。 设置 MSGFLAG_READ 标志将邮件标记为已读，其中不一定表示预期接收人已实际阅读消息。 
  
**SetReadFlags**还管理阅读报告的发送。 仅当发件人已请求一个发送读取的报表。 
  
读取标志不能更改为：
  
- 不存在的邮件。
    
- 邮件已移动至其他位置。
    
- 打开具有读/写权限的邮件。
    
- 当前提交的邮件。
    
## <a name="notes-to-callers"></a>给调用方的说明

如果无标志设置_ulFlags_参数中，下列规则适用： 
  
- 如果已设置 MSGFLAG_READ，不执行任何操作。
    
- 如果未设置 MSGFLAG_READ，将其设置，并发送任何挂起的阅读报告如果**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性设置。
    
如果设置 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志，PR_READ_RECEIPT_REQUESTED 位，如果设置，应该被清除，不应发送读取的报表。
  
当 SUPPRESS_RECEIPT 标志设置：
  
- 如果已设置 MSGFLAG_READ，不执行任何操作。 
    
- 如果未设置 MSGFLAG_READ，将其设置和取消任何挂起的阅读报告。
    
当设置 CLEAR_READ_FLAG 标志时，清除 MSGFLAG_READ 标志每条消息**PR_MESSAGE_FLAGS**属性中的并不发送任何阅读的报告。 
  
当设置 GENERATE_RECEIPT_ONLY 标志时，发送任何挂起的阅读的报告。 执行操作未设置或清除 MSGFLAG_READ。
  
时设置的 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志，PR_READ_RECEIPT_REQUESTED 属性设置为 FALSE 如果设置，但不发送读取的报表。
  
您可以通过消除在某些情况下的阅读报告的生成优化报表行为。 但是，如果您不支持报告的禁止显示设置了 SUPPRESS_RECEIPT 标志在客户端调用**SetReadFlag** ，返回 MAPI_E_NO_SUPPRESS。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolderDlg::OnSetReadFlag  <br/> |MFCMAPI 使用**IMessage::SetReadFlag**方法对所选邮件设置只读的标志。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)  
- [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)  
- [IMAPIProp::GetProps](imapiprop-getprops.md)  
- [IMAPIProp::SaveChanges](imapiprop-savechanges.md) 
- [PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md) 
- [IMessage : IMAPIProp](imessageimapiprop.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

