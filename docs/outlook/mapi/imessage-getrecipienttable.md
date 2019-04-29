---
title: IMessageGetRecipientTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.GetRecipientTable
api_type:
- COM
ms.assetid: a335dfca-44da-452e-b16f-25d314b1758f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ca42e91528cdb7e61ae3620989c4a89966db1061
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424607"
---
# <a name="imessagegetrecipienttable"></a>IMessage::GetRecipientTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回邮件的收件人表。
  
```cpp
HRESULT GetRecipientTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时控制表的返回的标志的位掩码。 可以设置以下标志:
    
MAPI_DEFERRED_ERRORS 
  
> 允许**GetRecipientTable**成功返回, 这可能在表完全可用于调用客户端之前。 如果该表不可用, 则对其进行后续调用可能会导致出错。 
    
MAPI_UNICODE 
  
> 字符串列应采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串列应为 ANSI 格式。
    
 _lppTable_
  
> 排除指向收件人表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回收件人表。
    
## <a name="remarks"></a>说明

**IMessage:: GetRecipientTable**方法返回指向邮件的收件人表的指针, 其中包含有关邮件的所有收件人的信息。 每个收件人都有一个行。 
  
收件人表根据邮件是否已提交而设置了不同的列。 有关收件人表中的列的完整列表, 请参阅[收件人表](recipient-tables.md)。
  
某些收件人表支持各种限制;而不是其他人。 对限制的支持取决于邮件存储提供程序的实现。 
  
在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响对收件人表的以下调用: 
  
- [IMAPITable:: QueryColumns](imapitable-querycolumns.md)检索列集。 
    
- [IMAPITable:: QueryRows](imapitable-queryrows.md)检索行。 
    
- [IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)检索排序顺序。 
    
设置 unicode 标志请求从这些调用返回的任何字符串列的信息都是 Unicode 格式。 但是, 由于并非所有邮件存储提供程序都支持 Unicode, 因此设置此标志只是一个请求。
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过调用[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法来更改打开的收件人表。 **ModifyRecipients**添加收件人、删除收件人或修改收件人属性。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)

