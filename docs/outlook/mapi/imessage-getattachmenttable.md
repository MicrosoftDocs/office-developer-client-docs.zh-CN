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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9a77d335f3c8980de29dab6e14079c83bd711b43
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421170"
---
# <a name="imessagegetattachmenttable"></a>IMessage::GetAttachmentTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回邮件的附件表。
  
```cpp
HRESULT GetAttachmentTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时与表创建相关的标志的位掩码。 可以设置以下标志: 
    
MAPI_UNICODE 
  
> 字符串列采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串列的格式为 ANSI。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**GetAttachmentTable**成功返回, 这可能在表完全可用于调用客户端之前。 如果该表不可用, 则对其进行后续调用可能会导致出错。 
    
 _lppTable_
  
> 排除指向附件表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索附件表。
    
## <a name="remarks"></a>说明

**IMessage:: GetAttachmentTable**方法返回指向邮件附件表的指针, 其中包含有关邮件中所有附件的信息。 客户端只能通过附件表获取附件的访问权限。 通过检索附件编号的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性, 客户端可以使用多个**IMessage**方法来处理附件。 
  
每个附件都有一个行。 有关附件表中的列的完整列表, 请参阅[附件表](attachment-tables.md)。
  
附件通常不会显示在附件表格中, 直到附件和邮件均已通过调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)保存。 附件表是动态的。 如果客户端创建新附件、删除现有附件或更改一个或多个属性, 则在对邮件上的附件进行**SaveChanges**调用之后, 附件表将进行更新以反映新的信息。 
  
某些附件表支持各种限制;而不是其他人。 对限制的支持取决于邮件存储提供程序的实现。 
  
最初打开时, 附件表不一定以任何特定的顺序进行排序。 
  
在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响对附件表的以下调用: 
  
- [IMAPITable:: QueryColumns](imapitable-querycolumns.md)检索列集。 
    
- [IMAPITable:: QueryRows](imapitable-queryrows.md)检索行。 
    
- [IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)检索排序顺序。 
    
设置 unicode 标志请求从这些调用返回的任何字符串列的信息都是 Unicode 格式。 但是, 由于并非所有邮件存储提供程序都支持 Unicode, 因此设置此标志只是一个请求。
  
## <a name="see-also"></a>另请参阅



[IMessage::CreateAttach](imessage-createattach.md)
  
[IMessage::DeleteAttach](imessage-deleteattach.md)
  
[IMessage::OpenAttach](imessage-openattach.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)

