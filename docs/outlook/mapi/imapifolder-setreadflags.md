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
  
设置或清除文件夹的一个或多个邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的 MSGFLAG_READ 标志，并管理读取报表的发送。 
  
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
  
> [in]指向 [ENTRYLIST](entrylist.md) 结构的数组的指针，该数组标识要设置或清除的读取标志的邮件。 如果  _lpMsgList_ 设置为 NULL，则设置或清除文件夹的所有邮件的读取标志。 
    
_ulUIParam_
  
> [in]进度指示器的父窗口的句柄。 除非  _在 ulFlags_ 参数中设置了 MESSAGE_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。 
    
_lpProgress_
  
> [in]指向显示进度指示器的进度对象的指针。 如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 的实现显示进度指示器。 除非在 _ulFlags_ 中设置了 MESSAGE_DIALOG 标志，否则将忽略 _lpProgress_ 参数。
    
_ulFlags_
  
> [in]控制邮件的读取标志设置和读取报告处理的标志位掩码。 可以设置以下标志：
    
  - CLEAR_READ_FLAG：MSGFLAG_READ中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送阅读报告。 
        
  - CLEAR_NRN_PENDING：MSGFLAG_NRN_PENDING中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送未读报告。 
        
  - CLEAR_RN_PENDING：MSGFLAG_RN_PENDING中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送阅读报告。 
        
  - GENERATE_RECEIPT_ONLY：如果一个已读报告挂起，则应该发送一个已读报告，但该读取报告MSGFLAG_READ状态。
        
  - MAPI_DEFERRED_ERRORS：允许在操作完成之前成功返回 **SetReadFlags。** 
        
  - MESSAGE_DIALOG：在操作进行时显示进度指示器。
    
  - SUPPRESS_RECEIPT：如果已请求读取报告，并且此调用将邮件的状态从"未读"改为"已读"，应取消挂起的阅读报告。 如果此调用不更改邮件的状态，则邮件存储提供程序可以忽略此标志。
    
## <a name="return-values"></a>返回值

S_OK 
  
> 已成功设置或清除指定邮件的读取标志。
    
MAPI_E_NO_SUPPRESS 
  
> 邮件存储提供程序不支持禁止读取报告。
    
MAPI_E_INVALID_PARAMETER 
  
> 在  _ulFlags_ 参数中设置以下不兼容的标志组合之一： 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
   - CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但并非所有邮件都已成功处理。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPIFolder：：SetReadFlags** 方法设置或清除文件夹的一个或多个邮件的 PR_MESSAGE_FLAGS 属性中的 **MSGFLAG_READ** 标志。 设置MSGFLAG_READ标记将邮件标记为已读，这不一定表示目标收件人实际上已阅读该邮件。 
  
**SetReadFlags** 还管理读取报表的发送。 
  
不能为以下项更改读取标志：
  
- 不存在的邮件。
    
- 已移动到其他位置的邮件。
    
- 具有读/写权限打开的邮件。
    
- 当前提交的邮件。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

您可以决定不支持发送阅读报告和禁止显示阅读报告的请求。 为了避免隐藏读取报表，当调用 **setReadFlags** MAPI_E_NO_SUPPRESS  _ulFlags_ 参数中设置SUPPRESS_RECEIPT返回一个返回值。 
  
当  _lpMsgList_ 参数指向多个邮件时，请尽可能完全地执行每封邮件的操作。 除非发生超出你的控制范围（如内存不足、磁盘空间不足或邮件存储损坏）发生的故障，否则不要提前停止操作。 
  
如果在  _ulFlags_ 参数中未设置任何标志，则以下规则适用： 
  
- 如果MSGFLAG_READ，则不执行任何操作。
    
- 如果未MSGFLAG_READ，则立即设置它，如果设置了 PR_READ_RECEIPT_REQUESTED ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 发送任何挂起的已读报告。 
    
设置 SUPPRESS_RECEIPT 标志时，以下规则适用：
  
- 如果MSGFLAG_READ，则不执行任何操作。 
    
- 如果未MSGFLAG_READ，请设置它并取消任何挂起的已读报告。
    
设置 CLEAR_READ_FLAG 标记时，清除MSGFLAG_READ属性中的 PR_MESSAGE_FLAGS 标记，不要发送任何已读报告。 
  
设置GENERATE_RECEIPT_ONLY时，发送任何挂起的已读报告。 不要设置或清除MSGFLAG_READ。
  
当设置 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志时，PR_READ_RECEIPT_REQUESTED设置为 FALSE，并且不要发送读取报告。 
  
## <a name="notes-to-callers"></a>给调用方的说明

预计以下情况下会返回这些值。
  
|**Condition**|**返回值**|
|:-----|:-----|
|**SetReadFlags** 已成功处理每封邮件。  <br/> |S_OK  <br/> |
|**SetReadFlags** 无法成功处理每封邮件。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**SetReadFlags** 无法完成。  <br/> |任何错误值（MAPI_E_NOT_FOUND  <br/> |
   
当 **SetReadFlags** 无法完成时，不要假定未完成任何工作。 **SetReadFlags** 可能能够在遇到错误之前为一个或多个邮件设置或清除 MSGFLAG_READ 标志。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolderDlg：：OnSetReadFlag  <br/> |MFCMAPI 使用 **IMAPIFolder：：SetReadFlags** 方法手动设置指定邮件的读取状态。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [ENTRYLIST](entrylist.md) 
- [IMessage::SetReadFlag](imessage-setreadflag.md)  
- [PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)  
- [PidTagReadReceiptRequested 规范属性](pidtagreadreceiptrequested-canonical-property.md)  
- [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)  
- [使用宏处理错误](using-macros-for-error-handling.md)

