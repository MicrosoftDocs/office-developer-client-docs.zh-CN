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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439868"
---
# <a name="imessagesetreadflag"></a>IMessage::SetReadFlag

**适用于**：Outlook 2013 | Outlook 2016 
  
设置或清除 MSGFLAG_READ [PidTagMessageFlags PR_MESSAGE_FLAGS (PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的"已读"标志，并管理已读报表的发送。 
  
```cpp
HRESULT SetReadFlag(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

_ulFlags_
  
> [in]控制邮件的读取标志设置的位掩码，即邮件的 MSGFLAG_READ 标志在其 **PR_MESSAGE_FLAGS** 属性中和读取报告处理。 可以设置以下标志： 
    
  - CLEAR_READ_FLAG：MSGFLAG_READ中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送任何读取报告。 
      
  - CLEAR_NRN_PENDING：MSGFLAG_NRN_PENDING中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送未读报告。 
      
  - CLEAR_RN_PENDING：MSGFLAG_RN_PENDING中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送任何读取报告。 
      
  - GENERATE_RECEIPT_ONLY：如果一个已读报告挂起，则应该发送一个已读报告，但该读取报告MSGFLAG_READ状态。
      
  - MAPI_DEFERRED_ERRORS：允许在操作完成之前成功返回 **SetReadFlag。** 
      
  - SUPPRESS_RECEIPT：如果已请求读取报告，并且此调用将邮件的状态从"未读"改为"已读"，应取消挂起的阅读报告。 如果此调用不更改邮件的状态，则邮件存储提供程序可以忽略此标志。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置或清除邮件的读取标志。
    
MAPI_E_NO_SUPPRESS 
  
> 邮件存储提供程序不支持禁止读取报告。
    
MAPI_E_INVALID_PARAMETER 
  
> 在  _ulFlags_ 参数中设置以下标志组合之一： 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
   - CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
## <a name="remarks"></a>备注

**IMessage：：SetReadFlag** 方法设置或清除 PR_MESSAGE_FLAGS 属性中的邮件 MSGFLAG_READ 标志 **，** 并调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)以保存邮件。 设置MSGFLAG_READ标记将邮件标记为已阅读，这不一定表示目标收件人实际上已阅读该邮件。 
  
**SetReadFlags** 还管理读取报表的发送。 仅在发件人已请求一份阅读报告时发送。 
  
不能为以下项目更改读取标志：
  
- 不存在的邮件。
    
- 已移动到其他位置的邮件。
    
- 具有读/写权限打开的邮件。
    
- 当前提交的邮件。
    
## <a name="notes-to-callers"></a>给调用方的说明

如果在  _ulFlags_ 参数中未设置任何标志，则以下规则适用： 
  
- 如果MSGFLAG_READ，则不执行任何操作。
    
- 如果未MSGFLAG_READ，请设置此属性，如果设置了 **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 发送任何挂起的已读报告。
    
如果设置了 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志，PR_READ_RECEIPT_REQUESTED位（如果已设置）并且不应发送读取报告。
  
设置SUPPRESS_RECEIPT标记时：
  
- 如果MSGFLAG_READ，则不执行任何操作。 
    
- 如果未MSGFLAG_READ，请设置它并取消任何挂起的已读报告。
    
设置 CLEAR_READ_FLAG 标记时，清除MSGFLAG_READ属性中的 PR_MESSAGE_FLAGS 标记，不要发送任何已读报告。 
  
设置GENERATE_RECEIPT_ONLY时，发送任何挂起的已读报告。 不要设置或清除MSGFLAG_READ。
  
设置 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志时，PR_READ_RECEIPT_REQUESTED属性设置为 FALSE（如果已设置）并且不发送读取报告。
  
您可以通过禁止在特定条件下生成读取报告来优化报告行为。 但是，如果您不支持抑制报告，并且客户端调用 **SetReadFlag** 时设置了 SUPPRESS_RECEIPT，则返回 MAPI_E_NO_SUPPRESS。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolderDlg：：OnSetReadFlag  <br/> |MFCMAPI 使用 **IMessage：：SetReadFlag** 方法在所选邮件上设置读取标志。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)  
- [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)  
- [IMAPIProp::GetProps](imapiprop-getprops.md)  
- [IMAPIProp::SaveChanges](imapiprop-savechanges.md) 
- [PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md) 
- [IMessage : IMAPIProp](imessageimapiprop.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

