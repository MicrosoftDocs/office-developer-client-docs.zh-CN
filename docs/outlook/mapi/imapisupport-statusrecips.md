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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341767"
---
# <a name="imapisupportstatusrecips"></a>IMAPISupport::StatusRecips

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
生成传递和 nondelivery 报告。
  
```cpp
HRESULT StatusRecips(
LPMESSAGE lpMessage,
LPADRLIST lpRecipList
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> 实时指向应为其生成报告的邮件的指针。
    
 _lpRecipList_
  
> 实时一个指向[ADRLIST](adrlist.md)结构的指针, 该结构描述_lpMessage_指向的邮件的收件人。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功生成报告。
    
MAPI_W_ERRORS_RETURNED 
  
> 呼叫全部成功, 但此类型的收件人没有收件人选项。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

为传输提供程序支持对象实现了**IMAPISupport:: StatusRecips**方法。 传输提供程序调用**StatusRecips**以请求 MAPI 向一组或多封邮件的一个或多个收件人发送传递或 nondelivery 报告。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在邮件处理过程中, 可以多次调用**StatusRecips** 。 但是, 如果您为打开的邮件调用**StatusRecips** , 则最好收集邮件收件人的所有传递和 nondelivery 信息, 并为该收件人列表调用**StatusRecips** 。 单点集合非常重要, 因为对一个收件人的多个**StatusRecips**调用可能会导致发送多个相同的报告。 
  
与_lpRecipList_参数指示的**ADRLIST**结构中的邮件传递或 nondelivery 相关的存储属性。 有关送达报告和 nondelivery 报告的必需属性和可选属性的完整列表, 请参阅[必需的报告邮件属性](required-report-message-properties.md)和[可选的报告邮件属性](optional-report-message-properties.md)。 
  
使用[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIAllocateMore](mapiallocatemore.md)函数为_lpRecipList_中的**ADRLIST**结构分配内存。 MAPI 仅在**StatusRecips**成功时调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 从而释放内存。 
  
有关传递和 nondelivery 报告的概述, 请参阅[MAPI 报告邮件](mapi-report-messages.md)。
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IMAPISupport::Address](imapisupport-address.md)
  
[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IXPLogon::EndMessage](ixplogon-endmessage.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

