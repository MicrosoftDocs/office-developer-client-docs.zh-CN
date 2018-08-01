---
title: PidTagRtfInSync 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfInSync
api_type:
- COM
ms.assetid: 443cc68e-7898-4285-a606-f916fcd18554
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 85e517601d291f144652befa267d8fd8f76dea64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778262"
---
# <a name="pidtagrtfinsync-canonical-property"></a>PidTagRtfInSync 规范属性

  
  
**适用于**： Outlook 
  
如果**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性具有相同的文本内容此消息的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性，包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RTF_IN_SYNC  <br/> |
|标识符：  <br/> |0x0E1F  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>说明

值为 TRUE 表示**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性，此消息的纯文本版本和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性，富文本格式 (RTF) 版本中，完全相同的除外**PR_BODY**和中**PR_RTF_COMPRESSED**格式中的空格。 两个版本中的文本包含的顺序相同的字符。
  
值为 FALSE 表示的两个版本不同步的文本内容，但能够在同步[RTFSync](rtfsync.md)函数。 已更改一个版本和其他版本却没有。 
  
没有值表示的两个版本中，如果同时存在或以往任何时候都存在，无法同步。 已删除或修改大大同步不再可能一个版本。
  
已修改**PR_RTF_COMPRESSED**客户端应用程序应设置的值为 FALSE 以强制执行同步此属性中。 RTF 感知消息存储应执行[IMAPIProp::SaveChanges](imapiprop-savechanges.md)呼叫期间使用**RTFSync**同步。 RTF 感知客户端应检查**PR_RTF_IN_SYNC**阅读**PR_RTF_COMPRESSED**之前, 的设置，并首先呼叫**RTFSync** ，如有必要。 
  
如果**PR_BODY**已为其空格以外的任何修改，消息存储库必须删除**PR_RTF_IN_SYNC**终止同步。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
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

