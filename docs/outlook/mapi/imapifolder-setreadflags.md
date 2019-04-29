---
title: IMAPIFolderSetReadFlags
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.SetReadFlags
api_type:
- COM
ms.assetid: 95a40c8a-0a8b-46c7-a07a-cbc6a7de8a3c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 15504ecc88188ed7bc4eed0e64b1871dbc6a5e8d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406911"
---
# <a name="imapifoldersetreadflags"></a>IMAPIFolder::SetReadFlags

**适用于**：Outlook 2013 | Outlook 2016 
  
设置或清除一个或多个文件夹的邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的 MSGFLAG_READ 标记, 并管理读取报告的发送。 
  
```cpp
HRESULT SetReadFlags(
  LPENTRYLIST lpMsgList,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

_lpMsgList_
  
> 实时指向[ENTRYLIST](entrylist.md)结构的数组的指针, 这些结构标识了具有已读标志以进行设置或清除的邮件。 如果将_lpMsgList_设置为 NULL, 则会设置或清除所有文件夹的邮件的读取标志。 
    
_ulUIParam_
  
> 实时进度指示器的父窗口的句柄。 除非在_ulFlags_参数中设置了 MESSAGE_DIALOG 标志, 否则将忽略_ulUIParam_参数。 
    
_lpProgress_
  
> 实时指向显示进度指示器的进度对象的指针。 如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 的实现显示进度指示器。 除非在_ulFlags_中设置了 MESSAGE_DIALOG 标志, 否则_lpProgress_参数将被忽略。
    
_ulFlags_
  
> 实时标志的位掩码, 用于控制邮件的阅读标志和读取报告的处理设置。 可以设置以下标志:
    
  - CLEAR_READ_FLAG: 应在**PR_MESSAGE_FLAGS**中清除 MSGFLAG_READ 标志, 且不应发送读取报告。 
        
  - CLEAR_NRN_PENDING: 应在**PR_MESSAGE_FLAGS**中清除 MSGFLAG_NRN_PENDING 标志, 且不应发送未读报告。 
        
  - CLEAR_RN_PENDING: 应在**PR_MESSAGE_FLAGS**中清除 MSGFLAG_RN_PENDING 标志, 且不应发送读取报告。 
        
  - GENERATE_RECEIPT_ONLY: 应在一个已挂起的情况下发送已读报告, 但在 MSGFLAG_READ 标志的状态中不应进行任何更改。
        
  - MAPI_DEFERRED_ERRORS: 允许**SetReadFlags**成功返回, 可能在操作完成前。 
        
  - MESSAGE_DIALOG: 在操作进行过程中显示进度指示器。
    
  - SUPPRESS_RECEIPT: 如果已请求读取报告且此呼叫将邮件的状态从 "未读" 更改为 "已读", 则应取消挂起的读取报告。 如果此调用不更改邮件的状态, 则邮件存储提供程序可以忽略此标志。
    
## <a name="return-values"></a>返回值

S_OK 
  
> 成功设置或清除了指定的一个或一条消息的读取标志。
    
MAPI_E_NO_SUPPRESS 
  
> 邮件存储区提供程序不支持禁止显示已读报告。
    
MAPI_E_INVALID_PARAMETER 
  
> 在_ulFlags_参数中设置以下不兼容的标志组合之一: 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
   - CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功, 但未成功处理所有邮件。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

**IMAPIFolder:: SetReadFlags**方法设置或清除一个或多个文件夹的邮件的**PR_MESSAGE_FLAGS**属性中的 MSGFLAG_READ 标记。 设置 MSGFLAG_READ 标志将邮件标记为 "已读", 这并不一定表明预期收件人确实已阅读邮件。 
  
**SetReadFlags**还管理阅读报告的发送。 
  
无法更改以下项的读取标志:
  
- 不存在的邮件。
    
- 已移动到其他位置的邮件。
    
- 以读/写权限打开的邮件。
    
- 当前已提交的邮件。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

您可以决定不支持发送阅读报告和禁止阅读报告的请求。 若要避免阻止阅读报告, 请在_ulFlags_参数中使用 SUPPRESS_RECEIPT set 调用**SetReadFlags**时返回 MAPI_E_NO_SUPPRESS。 
  
当_lpMsgList_参数指向多封邮件时, 请尽可能完全地对每封邮件执行该操作。 请勿提前停止操作, 除非发生超出控制范围的故障 (如内存不足、磁盘空间不足或邮件存储区损坏)。 
  
如果未在_ulFlags_参数中设置任何标志, 则以下规则适用: 
  
- 如果已设置 MSGFLAG_READ, 则不执行任何操作。
    
- 如果未设置 MSGFLAG_READ, 则立即设置它并发送任何挂起的读取报告 (如果设置了**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性)。
    
设置 SUPPRESS_RECEIPT 标志后, 将应用以下规则:
  
- 如果已设置 MSGFLAG_READ, 则不执行任何操作。 
    
- 如果未设置 MSGFLAG_READ, 请将其设置并取消任何待执行的已读报告。
    
设置 CLEAR_READ_FLAG 标志后, 清除每个邮件的**PR_MESSAGE_FLAGS**属性中的 MSGFLAG_READ 标记, 而不发送任何已读报告。 
  
设置 GENERATE_RECEIPT_ONLY 标志后, 发送任何挂起的读取报告。 请勿设置或清除 MSGFLAG_READ。
  
如果设置了 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志, 则将**PR_READ_RECEIPT_REQUESTED**设置为 FALSE (如果已设置) 且不发送阅读报告。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在下列情况下, 需要这些返回值。
  
|**条件**|**返回值**|
|:-----|:-----|
|**SetReadFlags**已成功处理每封邮件。  <br/> |S_OK  <br/> |
|**SetReadFlags**无法成功处理每封邮件。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**SetReadFlags**无法完成。  <br/> |除 MAPI_E_NOT_FOUND 外的任何错误值  <br/> |
   
当**SetReadFlags**无法完成时, 请不要假定没有任何工作已完成。 **SetReadFlags**可能已能够在遇到错误之前设置或清除一个或多个邮件的 MSGFLAG_READ 标志。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg  <br/> |CFolderDlg:: OnSetReadFlag  <br/> |MFCMAPI 使用**IMAPIFolder:: SetReadFlags**方法手动设置指定邮件的读取状态。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [ENTRYLIST](entrylist.md) 
- [IMessage::SetReadFlag](imessage-setreadflag.md)  
- [PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)  
- [PidTagReadReceiptRequested 规范属性](pidtagreadreceiptrequested-canonical-property.md)  
- [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)  
- [使用宏进行错误处理](using-macros-for-error-handling.md)

