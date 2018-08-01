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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f3642c890c3922611d57dea6f03aca5606876864
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775684"
---
# <a name="imapisupportstatusrecips"></a>IMAPISupport::StatusRecips

  
  
**适用于**： Outlook 
  
生成送达和原件报告。
  
```cpp
HRESULT StatusRecips(
LPMESSAGE lpMessage,
LPADRLIST lpRecipList
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> [in]一个指向应为其生成报告的邮件。
    
 _lpRecipList_
  
> [in]由_lpMessage_指向指向介绍邮件的收件人[ADRLIST](adrlist.md)结构的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功生成报告。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功总体上讲，但没有这种类型的收件人的收件人的选项。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

对于传输提供程序支持对象实现**IMAPISupport::StatusRecips**方法。 传输提供程序调用**StatusRecips**请求的 MAPI 发送到一组一个或多个收件人的邮件的传递或原件报表。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以一条消息处理过程中调用**StatusRecips**多次。 但是，如果您调用**StatusRecips**打开邮件时，进行收集信息传递和原件所有邮件的收件人，并对该收件人列表调用**StatusRecips**您最佳。 因为有一个收件人的多个**StatusRecips**呼叫会发送的多个相同的报告，很重要，单点的集合。 
  
存储与邮件传递或原件_lpRecipList_参数指示**ADRLIST**结构中的相关的属性。 送达报告和未送达报告的必需的和可选属性的完整列表，请参阅[所需的报表消息属性](required-report-message-properties.md)和[可选的报表消息属性](optional-report-message-properties.md)。 
  
使用[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIAllocateMore](mapiallocatemore.md)函数为_lpRecipList_的**ADRLIST**结构分配内存。 MAPI 通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数，仅当**StatusRecips**成功释放内存。 
  
送达和原件报告的概述，请参阅[MAPI 报告消息](mapi-report-messages.md)。
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IMAPISupport::Address](imapisupport-address.md)
  
[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IXPLogon::EndMessage](ixplogon-endmessage.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

