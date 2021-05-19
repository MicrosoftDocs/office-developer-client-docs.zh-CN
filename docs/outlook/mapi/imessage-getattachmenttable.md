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
  
> [in]与表的创建相关的标志的位掩码。 可以设置以下标志： 
    
MAPI_UNICODE 
  
> 字符串列采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串列采用 ANSI 格式。
    
MAPI_DEFERRED_ERRORS 
  
> 允许在表完全可供调用客户端使用之前，成功返回 **GetAttachmentTable。** 如果表不可用，则对该表进行后续调用会导致错误。 
    
 _lppTable_
  
> [out]指向指向附件表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索附件表。
    
## <a name="remarks"></a>备注

**IMessage：：GetAttachmentTable** 方法返回一个指向邮件附件表的指针，其中包括有关邮件中所有附件的信息。 客户端只能通过附件表访问附件。 通过检索附件的编号PR_ATTACH_NUM ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，客户端可以使用多种 **IMessage** 方法处理附件。  
  
每个附件有一行。 有关附件表中的列的完整列表，请参阅附件 [表](attachment-tables.md)。
  
附件通常不会显示在附件表中，直到通过 [调用 IMAPIProp：：SaveChanges](imapiprop-savechanges.md)保存附件和邮件。 附件表是动态的。 如果客户端在邮件的附件上执行 **SaveChanges** 调用后创建新附件、删除现有附件或更改一个或多个属性，附件表将进行更新以反映新信息。 
  
某些附件表支持各种限制;其他则不允许。 对限制的支持取决于邮件存储提供程序的实现。 
  
初次打开时，附件表不一定按任何特定顺序排序。 
  
在  _ulFlags_ MAPI_UNICODE设置值标记会影响对附件表的以下调用： 
  
- [IMAPITable：：QueryColumns，](imapitable-querycolumns.md) 用于检索列集。 
    
- [IMAPITable：：QueryRows，](imapitable-queryrows.md) 用于检索行。 
    
- [IMAPITable：：QuerySortOrder，](imapitable-querysortorder.md) 用于检索排序顺序。 
    
设置 Unicode 标志请求从这些调用返回的任何字符串列的信息采用 Unicode 格式。 但是，由于并非所有邮件存储提供程序都支持 Unicode，因此设置此标志只是一个请求。
  
## <a name="see-also"></a>另请参阅



[IMessage::CreateAttach](imessage-createattach.md)
  
[IMessage::DeleteAttach](imessage-deleteattach.md)
  
[IMessage::OpenAttach](imessage-openattach.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)

