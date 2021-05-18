---
title: PidLidUseTnef 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidUseTnef
api_type:
- COM
ms.assetid: 954048d6-e2eb-43e7-b52c-c2f047bb84a4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 56f6e2355ee2e64cc766bafe27cd59454e210ab6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315419"
---
# <a name="pidlidusetnef-canonical-property"></a>PidLidUseTnef 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定在邮件从 MAPI 转换为多用途 Internet 邮件扩展 (MIME) 或简单邮件传输协议 (SMTP) 格式时，是否应在邮件中包含传输中性封装格式 (TNEF) 。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidUseTNEF  <br/> |
|属性集：  <br/> |PSETID_Common  <br/> |
|LONG ID (的一) ：  <br/> |0x00008582  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |运行时配置  <br/> |
   
## <a name="remarks"></a>备注

此属性指定当邮件从 TNEF 转换为 MIME 或 SMTP 格式时，是否应在邮件中包含 TNEF。 此属性可能不存在，如果不存在，则邮件中不得包含 TNEF。
  
此属性仅在邮件从 POP3/SMTP 邮件帐户发送时适用，不适用于其他提供程序（如 Microsoft Exchange Server）发送的邮件。
  
在某些情况下，例如启用投票按钮或将 OLE 嵌入对象附加到邮件时，Outlook设置此属性以强制使用 TNEF。
  
[PidTagMessageEditorFormat PR_MSG_EDITOR_FORMAT (PidTagMessageEditorFormat](pidtagmessageeditorformat-canonical-property.md)) 属性可用于在发送邮件时仅强制实施纯文本，而不是 TNEF。  因为 **PidLidUseTNEF** 会覆盖 **PR_MSG_EDITOR_FORMAT** 中的设置，所以想要对传出邮件强制使用纯文本的应用程序还应查找 **PidLidUseTNEF，** 并重置为 FALSE。 此外，外接程序必须删除需要 TNEF 的邮件功能，以避免最终发送的邮件上的附件不可用。 
  
调用[IConverterSession：：MAPIToMIMEStm](iconvertersession-mapitomimestm.md)时，使用 CCSF_USE_TNEF 标志将传出 MAPI 邮件转换为 MIME 流也可强制执行 TNEF。 即使未设置 **PidLidUseTNEF，** 这仍然适用。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定电子邮件对象允许的属性和操作。
    
[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码和解码为有效的流表示形式。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

