---
title: IMessageGetAttachmentTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.GetAttachmentTable
api_type:
- COM
ms.assetid: e568917e-6085-4094-8728-89ba90a78c40
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 275dc17a141f1c002f62a43824174458e591d4de
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775758"
---
# <a name="imessagegetattachmenttable"></a>IMessage::GetAttachmentTable

  
  
**适用于**： Outlook 
  
返回邮件的附件表。
  
```cpp
HRESULT GetAttachmentTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]创建表与相关的标志的位掩码。 可以设置以下标记： 
    
MAPI_UNICODE 
  
> 字符串列的 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，字符串列的 ANSI 格式。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**GetAttachmentTable**返回成功，原因可能是完全可调用客户端表之前。 如果表不可用，请进行后续呼叫到它会导致出错。 
    
 _lppTable_
  
> [输出]为附件表指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索附件表。
    
## <a name="remarks"></a>说明

**IMessage::GetAttachmentTable**方法返回到邮件的附件表，其中包括有关的所有附件信息消息中的指针。 客户端可以获取对仅通过附件表附件的访问。 通过检索的附件数其**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性客户端可以使用几个**IMessage**方法来处理附件。 
  
没有每个附件的一行。 附件表中的列的完整列表，请参阅[附件表](attachment-tables.md)。
  
附件通常不显示附件表中直到附件，邮件已保存到[IMAPIProp::SaveChanges](imapiprop-savechanges.md)呼叫。 附件表是动态的。 如果客户端创建一个新附件、 删除现有附件，或更改一个或多个属性，对邮件附件进行了**SaveChanges**呼叫后，将更新附件表，以反映新的信息。 
  
某些附件表支持多种限制;有些则没有。 限制对支持取决于消息存储提供程序的实现。 
  
最初打开时，附件表不一定是任何特定顺序排序。 
  
_UlFlags_参数中设置 MAPI_UNICODE 标志会影响对附件表的以下调用： 
  
- [IMAPITable::QueryColumns](imapitable-querycolumns.md)检索列集。 
    
- [IMAPITable::QueryRows](imapitable-queryrows.md)检索行。 
    
- [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) ，若要检索的排序次序。 
    
设置与这些呼叫返回任何字符串列的信息将 Unicode 格式的 Unicode 标志请求。 但是，因为不是所有的消息存储提供程序支持 Unicode，设置此标志是仅的请求。
  
## <a name="see-also"></a>另请参阅



[IMessage::CreateAttach](imessage-createattach.md)
  
[IMessage::DeleteAttach](imessage-deleteattach.md)
  
[IMessage::OpenAttach](imessage-openattach.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)

