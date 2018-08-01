---
title: PidTagContainerContents 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContainerContents
api_type:
- HeaderDef
ms.assetid: 66dbe65a-b9fd-41d5-946f-ec8888363043
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c2979a0825ad6c62dbbb7931255501e90d8450a5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777462"
---
# <a name="pidtagcontainercontents-canonical-property"></a>PidTagContainerContents 规范属性

  
  
**适用于**： Outlook 
  
包含一个嵌入的内容表对象，提供有关容器的信息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAINER_CONTENTS  <br/> |
|标识符：  <br/> |0x360F  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |Container  <br/> |
   
## <a name="remarks"></a>说明

可以在[IMAPIProp::CopyTo](imapiprop-copyto.md)操作中排除或[IMAPIProp::CopyProps](imapiprop-copyprops.md)操作中包括此属性。 作为 PT_OBJECT 类型的属性，它无法成功检索[IMAPIProp::GetProps](imapiprop-getprops.md)方法;应由请求 IID_IMAPITable 接口标识符的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法访问其内容。 服务提供商必须将其报告[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法或如果其设置，但可以选择将其报告不如果它未设置。 
  
若要检索目录，客户端应用程序应调用[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法。 有关详细信息，请参阅[内容表](contents-tables.md)。 
  
此属性， **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 和**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 相近的用法。 几个 MAPI 属性提供对表访问： 
  
|**属性**|**Table**|
|:-----|:-----|
|PidTagContainerContents  <br/> |内容表  <br/> |
|**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))  <br/> |层次结构表  <br/> |
|**PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))  <br/> |关联的内容表  <br/> |
|**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))  <br/> |附件表  <br/> |
|**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))  <br/> |收件人表  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

