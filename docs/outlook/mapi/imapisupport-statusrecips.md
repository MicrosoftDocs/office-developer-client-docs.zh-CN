---
title: IMAPISupportStatusRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.StatusRecips
api_type:
- COM
ms.assetid: 9c34538e-5ba4-47c8-8002-85afa9d6c067
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 39d8786bf558ade4599d69e0a764f87fe60d99f3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408766"
---
# <a name="imapisupportstatusrecips"></a>IMAPISupport::StatusRecips

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
生成送达和未送达报告。
  
```cpp
HRESULT StatusRecips(
LPMESSAGE lpMessage,
LPADRLIST lpRecipList
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> [in]指向应生成报告的消息的指针。
    
 _lpRecipList_
  
> [in]指向 [ADRLIST](adrlist.md) 结构的指针，该结构描述  _lpMessage 指向的邮件的收件人_。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 报告已成功生成。
    
MAPI_W_ERRORS_RETURNED 
  
> 呼叫整体成功，但此类型的收件人没有收件人选项。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPISupport：：StatusRecips** 方法为传输提供程序支持对象实现。 传输提供程序调用 **StatusRecips** 以请求 MAPI 将传递或非送达报告发送给一组邮件的一个或多个收件人。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在处理邮件 **期间，可以多次调用 StatusRecips。** 但是，如果为打开的邮件调用 **StatusRecips，** 请尽力收集邮件收件人的所有传递和未送达信息，并呼叫该收件人列表的 **StatusRecips。** 一个集合点很重要，因为对一个收件人的多个 **StatusRecips** 调用可能会导致发送多个相同的报告。 
  
将与邮件传递或非送达相关的属性存储在 _由 lpRecipList_ 参数指示的 **ADRLIST** 结构中。 有关送达报告和未送达报告的必需属性和可选属性的完整列表，请参阅 Required Report [Message Properties](required-report-message-properties.md)和[Optional Report Message Properties。](optional-report-message-properties.md) 
  
使用 [MAPIAllocateBuffer](mapiallocatebuffer.md)和 [MAPIAllocateMore](mapiallocatemore.md)函数为 _lpRecipList_ 中的 **ADRLIST** 结构分配内存。 MAPI 仅在 **StatusRecips** 成功时通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放内存。 
  
有关送达和未送达报告的概述，请参阅 [MAPI Report Messages](mapi-report-messages.md)。
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IMAPISupport::Address](imapisupport-address.md)
  
[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IXPLogon::EndMessage](ixplogon-endmessage.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

