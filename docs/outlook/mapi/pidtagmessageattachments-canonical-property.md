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
ms.openlocfilehash: 975f52e6ea0ca7a469a027565f845f9dc0f9c2cf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342565"
---
# <a name="pidtagmessageattachments-canonical-property"></a>PidTagMessageAttachments 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件的附件表。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_ATTACHMENTS  <br/> |
|标识符:  <br/> |0x0E13  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

此属性可以在 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 操作中排除，也可以包含在 [IMAPIProp：：CopyProps 操作](imapiprop-copyprops.md) 中。 作为类型为 [PT_OBJECT，IMAPIProp：：GetProps](imapiprop-getprops.md) 方法无法成功检索它。 它的内容应该由 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法访问，并请求 **IID_IMAPITable标识符。** 如果已设置，服务提供商必须报告给 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法，但如果尚未设置，也可以不报告此方法。 
  
若要检索表内容，客户端应用程序应调用 [IMessage：：GetAttachmentTable](imessage-getattachmenttable.md) 方法。 有关详细信息，请参阅附件 [表](attachment-tables.md)。 
  
此属性可用于子对象限制，具体方法为在 [SSubRestriction](ssubrestriction.md) 结构中指定它。 这允许客户端将容器视图限制为附件符合给定条件的邮件。 如果附件表中至少有一行（即一个附件）满足子对象限制，则邮件符合查看条件。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)
  
> 定义远程操作中使用的基本数据结构。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义远程操作中使用的基本数据结构。
    
[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> 在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。
    
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

