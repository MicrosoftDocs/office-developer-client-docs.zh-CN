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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5908069f5fa887fd9d2e3f8c0df75f2e3d69515c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579534"
---
# <a name="imessagegetrecipienttable"></a>IMessage::GetRecipientTable

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回邮件的收件人表。
  
```cpp
HRESULT GetRecipientTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控件返回的表。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许**GetRecipientTable**返回成功，原因可能是完全可调用客户端表之前。 如果表不可用，请进行后续呼叫到它会导致出错。 
    
MAPI_UNICODE 
  
> 字符串列应为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，应以 ANSI 格式为字符串列。
    
 _lppTable_
  
> [输出]为收件人表指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回收件人的表。
    
## <a name="remarks"></a>注解

**IMessage::GetRecipientTable**方法返回到邮件的收件人的表，其中包括所有邮件的收件人信息的指针。 没有用于每个收件人的一行。 
  
收件人表具有一个不同的列，具体取决于是否已提交邮件设置。 收件人的表中的列的完整列表，请参阅[收件人表](recipient-tables.md)。
  
某些收件人表支持多种限制;有些则没有。 限制对支持取决于消息存储提供程序的实现。 
  
_UlFlags_参数中设置 MAPI_UNICODE 标志会影响以下呼叫到收件人表： 
  
- [IMAPITable::QueryColumns](imapitable-querycolumns.md)检索列集。 
    
- [IMAPITable::QueryRows](imapitable-queryrows.md)检索行。 
    
- [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) ，若要检索的排序次序。 
    
设置与这些呼叫返回任何字符串列的信息将 Unicode 格式的 Unicode 标志请求。 但是，因为不是所有的消息存储提供程序支持 Unicode，设置此标志是仅的请求。
  
## <a name="notes-to-callers"></a>给调用方的说明

打开时，调用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法，您可以更改收件人的表。 **ModifyRecipients**将收件人添加、 删除收件人，或修改收件人的属性。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)

