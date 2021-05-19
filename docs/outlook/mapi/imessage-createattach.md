---
title: IMessageCreateAttach
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.IMessage::CreateAttach
api_type:
- COM
ms.assetid: 01711aca-c598-438c-88d7-0719b6691e34
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f534912377aadb3c342030fc02fce26693857476
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417669"
---
# <a name="imessagecreateattach"></a>IMessage::CreateAttach

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建新的附件。
  
```cpp
HRESULT CreateAttach(
LPCIID lpInterface,
ULONG ulFlags,
ULONG FAR * lpulAttachmentNum,
LPATTACH FAR * lppAttach
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> [in]指向接口标识符的 (IID) 表示用于访问邮件的接口的 IID 标识符。 传递 NULL 会导致返回邮件的标准接口 **IMessage。** 
    
 _ulFlags_
  
> [in]控制附件创建方式的标志的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **CreateAttach** 在调用客户端完全访问附件之前成功返回。 如果附件不可访问，则对附件进行后续调用可能会导致错误。 
    
 _lpulAttachmentNum_
  
> [out]指向标识新创建的附件的索引号的指针。 此号码仅在邮件打开时有效，是附件的 PR_ATTACH_NUM ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 的基础。 
    
 _lppAttach_
  
> [out]指向打开的 attachment 对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建附件。
    
## <a name="remarks"></a>备注

**IMessage：：CreateAttach** 方法在邮件上创建新附件。 在客户端同时调用附件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法和邮件的 **IMAPIProp：：SaveChanges** 方法之前，新附件及其设置的任何属性都不可用。 
  
_lpulAttachmentNum_ 指向的附件编号是唯一的，并且仅在邮件上下文中有效。 也就是说，两个不同邮件中的两个附件可以具有相同的编号，而同一邮件中的两个附件不能相同。 
  
## <a name="see-also"></a>另请参阅



[IMessage : IMAPIProp](imessageimapiprop.md)

