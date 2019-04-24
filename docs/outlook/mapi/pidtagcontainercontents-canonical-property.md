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
ms.openlocfilehash: 5f0717c2a6def6f99f1e53217764e8820125b79d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283126"
---
# <a name="pidtagcontainercontents-canonical-property"></a>PidTagContainerContents 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个提供有关容器信息的嵌入的内容表对象。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAINER_CONTENTS  <br/> |
|标识符:  <br/> |0x360F  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |Container  <br/> |
   
## <a name="remarks"></a>注解

此属性可以排除在[IMAPIProp:: CopyTo](imapiprop-copyto.md)操作中, 也可以包含在[IMAPIProp:: CopyProps](imapiprop-copyprops.md)操作中。 作为 PT_OBJECT 类型的属性, [IMAPIProp:: GetProps](imapiprop-getprops.md)方法无法成功检索它;其内容应由[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法访问, 请求 IID_IMAPITable 接口标识符。 如果设置了服务提供程序, 则必须将其报告给[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法, 但如果未设置, 则可以选择报告它。 
  
若要检索表内容, 客户端应用程序应调用[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法。 有关详细信息，请参阅[内容表](contents-tables.md)。 
  
此属性、 **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 和**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 在使用中相似。 有几个 MAPI 属性提供对表的访问权限: 
  
|**Property**|**Table**|
|:-----|:-----|
|PidTagContainerContents  <br/> |内容表  <br/> |
|**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))  <br/> |层次结构表  <br/> |
|**PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))  <br/> |关联的内容表  <br/> |
|**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))  <br/> |附件表  <br/> |
|**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))  <br/> |收件人表  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

