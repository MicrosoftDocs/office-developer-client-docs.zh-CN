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
ms.openlocfilehash: 029df4397f4d24c7c111d2017d34e6403df367d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325632"
---
# <a name="pidtagmessageeditorformat-canonical-property"></a>PidTagMessageEditorFormat 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定用于显示消息的编辑器的格式。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MSG_EDITOR_FORMAT  <br/> |
|标识符:  <br/> |0x5909  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>注解

**PR_MSG_EDITOR_FORMAT**的可能值可以是下列值之一: 
  
|**Value**|**说明**|
|:-----|:-----|
|**EDITOR_FORMAT_DONTKNOW** <br/> |要使用的编辑器的格式未知。  <br/> |
|**EDITOR_FORMAT_PLAINTEXT** <br/> |编辑器应以纯文本格式显示邮件。  <br/> |
|**EDITOR_FORMAT_HTML** <br/> |编辑器应以 HTML 格式显示邮件。  <br/> |
|**EDITOR_FORMAT_RTF** <br/> |编辑器应以 rtf 格式显示邮件。  <br/> |
   
默认情况下, 邮件为邮件类**IPM。请注意**或使用从 IPM 派生的自定义邮件类 **。注意**) 从 POP3/SMTP 邮件帐户发送将以传输中性封装格式 (TNEF) 的形式发送。 **PR_MSG_EDITOR_FORMAT**属性可用于在发送邮件时仅强制实现纯文本, 而不是 TNEF。 如果将**PR_MSG_EDITOR_FORMAT**设置为**EDITOR_FORMAT_PLAINTEXT**, 则邮件将以纯文本格式发送, 而不进行 TNEF。 如果将**PR_MSG_EDITOR_FORMAT**设置为**EDITOR_FORMAT_RTF**, 将隐式启用 TNEF 编码, 并使用在 Outlook 客户端中指定的默认 Internet 格式发送邮件。
  
在发送邮件时, 有两种其他方法可以强制使用 TNEF。
  
- 如果将邮件中的 " **dispidUseTNEF** " ([PidLidUseTnef](pidlidusetnef-canonical-property.md)) 命名属性设置为 True, 则会在将邮件从 MAPI 转换为 MIME/SMTP 时包含 TNEF。 请注意, **dispidUseTNEF**仅适用于从 POP3/SMTP 邮件帐户发送邮件时, 如果邮件是由其他提供商 (如 Microsoft Exchange Server) 发送的, 则不适用。 **dispidUseTNEF**将覆盖**PR_MSG_EDITOR_FORMAT**中的设置。
    
- 在调用[IConverterSession:: MAPIToMIMEStm](iconvertersession-mapitomimestm.md)将传出 MAPI 邮件转换为 MIME 流时使用**CCSF_USE_TNEF**标志也可以强制使用 TNEF。 即使未设置**dispidUseTNEF** , 这也适用。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义在远程操作中使用的基本数据结构。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
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

