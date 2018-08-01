---
title: PidTagMessageAttachments 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageAttachments
api_type:
- HeaderDef
ms.assetid: 85762771-b823-4227-9a7b-75b6ac280b2d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5b76a73a0fde8f4531b99a58646b927724162e81
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777828"
---
# <a name="pidtagmessageattachments-canonical-property"></a>PidTagMessageAttachments 规范属性

  
  
**适用于**： Outlook 
  
包含可应用到内容表中查找包含满足限制的附件子对象的所有消息的限制的表。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_ATTACHMENTS  <br/> |
|标识符：  <br/> |0x0E13  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>说明

可以在[IMAPIProp::CopyTo](imapiprop-copyto.md)操作中排除或[IMAPIProp::CopyProps](imapiprop-copyprops.md)操作中包括此属性。 作为 PT_OBJECT 类型的属性，它无法成功检索[IMAPIProp::GetProps](imapiprop-getprops.md)方法。 应由请求**IID_IMAPITable**接口标识符的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法访问其内容。 服务提供商必须将其报告[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法如果设置，但可以选择将其报告或不如果它未设置。 
  
若要检索目录，客户端应用程序应调用[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)方法。 有关详细信息，请参阅[附件表](attachment-tables.md)。 
  
此属性可用于任务的子对象限制通过指定[SSubRestriction](ssubrestriction.md)结构中。 这样，客户端限制容器与给定条件的邮件的附件为会议的视图。 查看如果其附件表，即一个附件中的至少一个行满足子对象限制符合一条消息。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCDATA]](http://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)
  
> 定义所使用的基本的数据结构中远程操作。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义所使用的基本的数据结构中远程操作。
    
[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。
    
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

