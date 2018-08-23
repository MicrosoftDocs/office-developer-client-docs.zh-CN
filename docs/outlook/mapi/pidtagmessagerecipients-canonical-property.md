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
ms.openlocfilehash: 6d0d2c07355140e89ffb24095d1ca3a302f6e5ce
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568446"
---
# <a name="pidtagmessagerecipients-canonical-property"></a>PidTagMessageRecipients 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含可应用到内容表中查找包含满足限制的收件人子对象的所有消息的限制的表。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_RECIPIENTS  <br/> |
|标识符：  <br/> |0x0E12  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

可以在[IMAPIProp::CopyTo](imapiprop-copyto.md)操作中排除或[IMAPIProp::CopyProps](imapiprop-copyprops.md)操作中包括此属性。 作为**PT_OBJECT**类型的属性，它无法成功检索[IMAPIProp::GetProps](imapiprop-getprops.md)方法。 应由请求**IID_IMAPITable**接口标识符的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法访问其内容。 服务提供商必须将其报告[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法如果设置，但可以选择将其报告或不如果它未设置。 
  
若要检索目录，客户端应用程序应调用[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法。 
  
此属性可用于任务的子对象限制通过指定[SSubRestriction](ssubrestriction.md)结构中。 这样的客户端限制到会议的收件人的邮件给定条件的容器的视图。 查看如果其收件人表，即一个收件人中的至少一个行满足子对象限制符合一条消息。 
  
 **注释**使用子对象限制结果是相当于[IMAPISession::OpenEntry](imapisession-openentry.md)呼叫上表中的每条消息。 根据客户端应用程序和要搜索的消息的数目，它会影响性能。 
  
**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性和此属性是在使用率类似。 几个 MAPI 属性提供对表访问： 
  
|**属性**|**Table**|
|:-----|:-----|
|**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))  <br/> |内容表  <br/> |
|**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))  <br/> |层次结构表  <br/> |
|**PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))  <br/> |关联的内容表  <br/> |
|**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))  <br/> |附件表  <br/> |
|PR_MESSAGE_RECIPIENTS  <br/> |收件人表  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理顺序和客户端和服务器之间的数据传输的流。
    
[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。
    
[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许处理的允许/阻止列表，并确定的垃圾邮件。
    
[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 进行编码和解码为有效的流表示形式的消息和附件对象。
    
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

