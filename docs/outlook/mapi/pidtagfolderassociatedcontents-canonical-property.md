---
title: PidTagFolderAssociatedContents 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFolderAssociatedContents
api_type:
- HeaderDef
ms.assetid: d1f3f589-dc2d-4538-a13f-278dad29bcc7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c85c5d7c3e80508c4d328f69ac4ad15f0f2c355a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316301"
---
# <a name="pidtagfolderassociatedcontents-canonical-property"></a>PidTagFolderAssociatedContents 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个嵌入式内容表对象，该对象提供有关关联内容表的信息。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FOLDER_ASSOCIATED_CONTENTS  <br/> |
|标识符:  <br/> |0x3610  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>备注

关联的内容表表示未显示在标准内容表中的子文件夹。 它包含文件夹的关联或隐藏邮件。 
  
此属性可以在 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 操作中排除，也可以包含在 [IMAPIProp：：CopyProps 操作](imapiprop-copyprops.md) 中。 作为类型为 PT_OBJECT **的属性**[，IMAPIProp：：GetProps](imapiprop-getprops.md)方法无法成功检索它;它的内容应该由 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法访问，并请求 **IID_IMAPITable标识符。** 如果已设置，服务提供商必须报告给 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法，但如果尚未设置，也可以不报告此方法。 
  
若要检索表内容，客户端应用程序应调用 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法。 有关文件夹内容表的信息， [请参阅内容表](contents-tables.md) 和 [显示文件夹内容表](displaying-a-folder-contents-table.md)。 
  
[PidTagContainerContents PR_CONTAINER_CONTENTS (PidTagContainerContents](pidtagcontainercontents-canonical-property.md)  **) 、PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) ，此属性的用法类似。 多个 MAPI 属性提供对表的访问权限： 
  
|**Property**|**Table**|
|:-----|:-----|
|**PR_CONTAINER_CONTENTS (** [PidTagContainerContents)](pidtagcontainercontents-canonical-property.md)  <br/> |Contents 表  <br/> |
|**PR_CONTAINER_HIERARCHY (** [PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))   <br/> |层次结构表  <br/> |
|**PR_FOLDER_ASSOCIATED_CONTENTS** <br/> |关联内容表  <br/> |
|**PR_MESSAGE_ATTACHMENTS (** [PidTagMessageAttachments)](pidtagmessageattachments-canonical-property.md)  <br/> |Attachment 表  <br/> |
|**PR_MESSAGE_RECIPIENTS (** [PidTagMessageRecipients)](pidtagmessagerecipients-canonical-property.md)  <br/> |收件人表  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端和服务器之间数据传输的顺序和流。
    
[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> 在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议项目之间转换。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagAssociatedContentCount 规范属性](pidtagassociatedcontentcount-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

