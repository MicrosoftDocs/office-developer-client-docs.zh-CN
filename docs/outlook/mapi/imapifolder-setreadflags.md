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
ms.openlocfilehash: 88185efea344844016547d0844277de6e0d661db
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578316"
---
# <a name="imapifoldersetreadflags"></a>IMAPIFolder::SetReadFlags

**适用于**： Outlook 2013 |Outlook 2016 
  
设置或清除 MSGFLAG_READ 标志中的一个或多个文件夹的邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性并管理阅读报告的发送。 
  
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
  
> [in]一个指向[ENTRYLIST](entrylist.md)结构标识的邮件或阅读标志设置或清除的邮件的数组。 如果_lpMsgList_设置为 NULL，读取的所有文件夹的邮件被设置或清除标志。 
    
_ulUIParam_
  
> [in]进度指示器的父窗口句柄。 除非 MESSAGE_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。 
    
_lpProgress_
  
> [in]指向显示进度指示器进度对象的指针。 如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 的实现显示进度指示器。 除非_ulFlags_中设置了 MESSAGE_DIALOG 标志，则将忽略该_lpProgress_参数。
    
_ulFlags_
  
> [in]邮件阅读标记的设置和处理控件的标志的位掩码阅读报告。 可以设置以下标志：
    
  - CLEAR_READ_FLAG： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_READ 标志和不应发送读取的报表。 
        
  - CLEAR_NRN_PENDING： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_NRN_PENDING 标志，不应发送未读的报告。 
        
  - CLEAR_RN_PENDING： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_RN_PENDING 标志和不应发送读取的报表。 
        
  - GENERATE_RECEIPT_ONLY： 应发送读取的报表，如果一个处于挂起状态，但不应 MSGFLAG_READ 标志的状态发生任何变化。
        
  - MAPI_DEFERRED_ERRORS： 允许**SetReadFlags**返回成功，原因可能是完成此操作之前。 
        
  - MESSAGE_DIALOG： 显示进度指示器时需执行的操作。
    
  - SUPPRESS_RECEIPT： 应取消挂起的阅读的报告，如果阅读的报告已被请求，并且此呼叫将从未读读取更改邮件的状态。 如果此呼叫不会更改邮件的状态，消息存储提供程序可以忽略此标志。
    
## <a name="return-values"></a>返回值

S_OK 
  
> 对指定的邮件或消息读取标志成功设置或清除。
    
MAPI_E_NO_SUPPRESS 
  
> 消息存储提供程序不支持阅读报告的禁止显示。
    
MAPI_E_INVALID_PARAMETER 
  
> _UlFlags_参数中设置以下不兼容的标志组合之一： 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG 
    
   - SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
   - CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但不是所有的邮件已成功处理。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPIFolder::SetReadFlags**方法设置或清除 MSGFLAG_READ 标志的一个或多个文件夹的邮件的**PR_MESSAGE_FLAGS**属性中。 设置 MSGFLAG_READ 标志将邮件标记为已读，不一定表示预期接收人已实际阅读消息。 
  
**SetReadFlags**还管理阅读报告的发送。 
  
读取标志不能更改以下：
  
- 不存在的邮件。
    
- 邮件已移动至其他位置。
    
- 打开具有读/写权限的邮件。
    
- 当前提交的邮件。
    
## <a name="notes-to-implementers"></a>针对实施者的注释

您可以决定不支持的读取的报表和禁止阅读的报告的请求发送。 若要避免消除读取的报表，返回 MAPI_E_NO_SUPPRESS **SetReadFlags**调用与 SUPPRESS_RECEIPT _ulFlags_参数中设置时。 
  
当_lpMsgList_参数指向多个邮件时，执行操作完全尽可能每条消息。 不停止操作提前除非超过了您的控件，如运行内存不足、 不足磁盘空间或损坏消息存储区中的出现故障。 
  
如果无标志设置_ulFlags_参数中，下列规则适用： 
  
- 如果已设置 MSGFLAG_READ，不执行任何操作。
    
- 如果未设置 MSGFLAG_READ，立即设置，并发送任何挂起的阅读报告如果**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性设置。
    
当 SUPPRESS_RECEIPT 标志设置时，下列规则适用：
  
- 如果已设置 MSGFLAG_READ，不执行任何操作。 
    
- 如果未设置 MSGFLAG_READ，将其设置和取消任何挂起的阅读报告。
    
当设置 CLEAR_READ_FLAG 标志时，清除 MSGFLAG_READ 标志每条消息**PR_MESSAGE_FLAGS**属性中的并不发送任何阅读的报告。 
  
当设置 GENERATE_RECEIPT_ONLY 标志时，发送任何挂起的阅读的报告。 执行操作未设置或清除 MSGFLAG_READ。
  
时设置的 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志， **PR_READ_RECEIPT_REQUESTED**如果设置为 false，则其设置，但不发送读取的报表。 
  
## <a name="notes-to-callers"></a>给调用方的说明

希望在下列情况下的这些返回值。
  
|**条件**|**返回值**|
|:-----|:-----|
|**SetReadFlags**已成功处理每条消息。  <br/> |S_OK  <br/> |
|**SetReadFlags**未能成功处理每条消息。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**SetReadFlags**无法完成。  <br/> |除 MAPI_E_NOT_FOUND 任何错误值  <br/> |
   
无法完成**SetReadFlags**时，不假定任何工作已完成。 **SetReadFlags**可能已经能够设置或在遇到错误之前的一个或多个邮件清除 MSGFLAG_READ 标志。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolderDlg::OnSetReadFlag  <br/> |MFCMAPI 使用**IMAPIFolder::SetReadFlags**方法将读取的状态手动设置对指定的邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [ENTRYLIST](entrylist.md) 
- [IMessage::SetReadFlag](imessage-setreadflag.md)  
- [PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)  
- [PidTagReadReceiptRequested 规范属性](pidtagreadreceiptrequested-canonical-property.md)  
- [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)  
- [使用宏进行错误处理](using-macros-for-error-handling.md)

