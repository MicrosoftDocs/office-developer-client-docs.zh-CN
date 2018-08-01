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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6351be353100649e38a14543a44df5e115c9408b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775767"
---
# <a name="imessagecreateattach"></a>IMessage::CreateAttach

  
  
**适用于**： Outlook 
  
创建一个新附件。
  
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
  
> [in]表示要用于访问邮件的接口的界面标识符 (IID) 的指针。 传递 NULL 将导致消息的标准界面或**IMessage**，返回。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何创建附件。 可以设置以下标记：
    
MAPI_DEFERRED_ERRORS 
  
> 允许**CreateAttach**返回成功，可能之前附件是完全可调用客户端。 如果附件不可访问，则进行后续呼叫到它会导致错误。 
    
 _lpulAttachmentNum_
  
> [输出]指向标识新创建的附件的索引号。 仅当邮件处于打开状态，并且基础的附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性时，此数字是有效。
    
 _lppAttach_
  
> [输出]指向打开附件对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 附件已成功创建。
    
## <a name="remarks"></a>说明

**IMessage::CreateAttach**方法创建一个新附件的邮件。 客户端具有调用附件的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法和消息的**IMAPIProp::SaveChanges**方法之前，新的附件和该设置的任何属性不可用。 
  
指向_lpulAttachmentNum_的附件数是唯一的并且只在邮件的上下文中有效。 即两个不同的邮件中的两个附件可以具有相同数量，而不能在同一消息中的两个附件。 
  
## <a name="see-also"></a>另请参阅



[IMessage : IMAPIProp](imessageimapiprop.md)

