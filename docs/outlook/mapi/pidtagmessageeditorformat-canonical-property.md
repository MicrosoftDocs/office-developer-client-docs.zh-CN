---
title: PidTagMessageEditorFormat 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageEditorFormat
api_type:
- HeaderDef
ms.assetid: 197b21ed-9f2f-425f-a6ed-cae1208fa2ca
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a6a3eb88377777a3d27687179bfdcb82057be3a9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777857"
---
# <a name="pidtagmessageeditorformat-canonical-property"></a>PidTagMessageEditorFormat 规范属性

  
  
**适用于**： Outlook 
  
指定编辑器，用于显示一条消息的格式。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MSG_EDITOR_FORMAT  <br/> |
|标识符：  <br/> |0x5909  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>说明

**PR_MSG_EDITOR_FORMAT**的可能值可以是下列选项之一： 
  
|**值**|**说明**|
|:-----|:-----|
|**EDITOR_FORMAT_DONTKNOW** <br/> |未知编辑器要使用的格式。  <br/> |
|**EDITOR_FORMAT_PLAINTEXT** <br/> |在编辑器应以纯文本格式显示消息。  <br/> |
|**EDITOR_FORMAT_HTML** <br/> |在编辑器应显示邮件以 HTML 格式。  <br/> |
|**EDITOR_FORMAT_RTF** <br/> |在编辑器应以富文本格式显示消息。  <br/> |
   
默认情况下，邮件的邮件 （邮件类**IPM 中。注意**或**IPM 从派生自定义邮件类别。请注意**) 发送帐户从 POP3/SMTP 邮件发送中传输中性封装格式 (TNEF)。 **PR_MSG_EDITOR_FORMAT**属性可用于强制实施仅纯文本，而不是 TNEF，发送邮件时。 如果**PR_MSG_EDITOR_FORMAT**设置为**EDITOR_FORMAT_PLAINTEXT**，没有 TNEF 纯文本形式发送邮件。 如果**PR_MSG_EDITOR_FORMAT**设置为**EDITOR_FORMAT_RTF**，隐式启用 TNEF 编码，并通过使用 Outlook 客户端中指定的默认 Internet 格式发送邮件。
  
有两个其他方式发送邮件时强制使用 TNEF。
  
- 设置**dispidUseTNEF** ([PidLidUseTnef](pidlidusetnef-canonical-property.md)) 名为属性设置为 True 上一条消息，指示转换为 MIME/SMTP 邮件 MAPI 时应包含 TNEF。 请注意该**dispidUseTNEF**仅适用于邮件发送的 POP3/SMTP 邮件帐户，并不适用于由其他提供程序，例如 Microsoft Exchange Server 发送邮件时。 **dispidUseTNEF**覆盖**PR_MSG_EDITOR_FORMAT**中的设置。
    
- 使用**CCSF_USE_TNEF**标志调用[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)时将传出的 MAPI 邮件转换为 MIME 流还可以强制 TNEF。 这适用即使**dispidUseTNEF**未设置。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义所使用的基本的数据结构中远程操作。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
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

