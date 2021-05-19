---
title: PidTagMessageRecipients 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageRecipients
api_type:
- HeaderDef
ms.assetid: 7f8b0d96-99d6-4f1c-8ac4-4dbb83626382
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d30088ba7398669228a18be825323afa800ec536
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355683"
---
# <a name="pidtagmessagerecipients-canonical-property"></a>PidTagMessageRecipients 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个限制表，可应用于内容表以查找包含符合限制的收件人子对象的所有邮件。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_RECIPIENTS  <br/> |
|标识符:  <br/> |0x0E12  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此属性可以在 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 操作中排除，也可以包含在 [IMAPIProp：：CopyProps 操作](imapiprop-copyprops.md) 中。 作为类型为 PT_OBJECT  [，IMAPIProp：：GetProps](imapiprop-getprops.md)方法无法成功检索它。 它的内容应该由 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法访问，并请求 **IID_IMAPITable标识符。** 如果已设置，服务提供商必须报告给 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法，但如果尚未设置，也可以不报告此方法。 
  
若要检索表内容，客户端应用程序应调用 [IMessage：：GetRecipientTable](imessage-getrecipienttable.md) 方法。 
  
此属性可用于子对象限制，具体方法为在 [SSubRestriction](ssubrestriction.md) 结构中指定它。 这使客户端能够将容器视图限制为收件人满足给定条件的邮件。 如果邮件的收件人表中至少有一行（即，一个收件人满足子对象限制，则邮件符合查看条件）。 
  
 **注意** 使用子对象限制结果等效于表中每条消息上的 [IMAPISession：：OpenEntry](imapisession-openentry.md) 调用。 根据客户端应用程序和要搜索的消息数，它可能会影响性能。 
  
**PR_MESSAGE_ATTACHMENTS** [PidTagMessageAttachments)  (PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)属性和此属性的用法相似。 多个 MAPI 属性提供对表的访问权限： 
  
|**Property**|**Table**|
|:-----|:-----|
|**PR_CONTAINER_CONTENTS (** [PidTagContainerContents)](pidtagcontainercontents-canonical-property.md)  <br/> |Contents 表  <br/> |
|**PR_CONTAINER_HIERARCHY (** [PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))   <br/> |层次结构表  <br/> |
|**PR_FOLDER_ASSOCIATED_CONTENTS (** [PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))   <br/> |关联内容表  <br/> |
|**PR_MESSAGE_ATTACHMENTS (** [PidTagMessageAttachments)](pidtagmessageattachments-canonical-property.md)  <br/> |Attachment 表  <br/> |
|PR_MESSAGE_RECIPIENTS  <br/> |收件人表  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端和服务器之间数据传输的顺序和流。
    
[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> 在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。
    
[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许/阻止列表的处理和垃圾邮件的确定。
    
[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码和解码为有效的流表示形式。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

