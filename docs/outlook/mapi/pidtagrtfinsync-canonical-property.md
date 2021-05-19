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
ms.openlocfilehash: ed038faf44f350b041191373cf573e7e185337c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357874"
---
# <a name="pidtagrtfinsync-canonical-property"></a>PidTagRtfInSync 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果 PR_RTF_COMPRESSED  ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性具有与此消息的 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性相同的文本内容，则包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RTF_IN_SYNC  <br/> |
|标识符:  <br/> |0x0E1F  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>备注

TRUE 值表示 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性、此消息的纯文本版本和 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性（RTF RTF (RTF) 版本）相同，PR_BODY 中的空格和 PR_RTF_COMPRESSED 中的 **格式** 除外。  两个版本中的文本由同一序列中的相同字符组成。
  
FALSE 值表示两个版本不同步文本内容，但能够由 [RTFSync](rtfsync.md) 函数进行同步。 一个版本已被更改，另一个版本尚未更改。 
  
没有值意味着两个版本（如果存在或曾经存在）无法同步。 一个版本已被删除或改变，因此无法再进行同步。
  
已修改此 **PR_RTF_COMPRESSED应在此属性** 中设置 FALSE 值以强制同步。 RTF 感知邮件存储应在 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)调用期间使用 **RTFSync** 执行同步。 RTF 感知客户端应先检查 PR_RTF_IN_SYNC **的设置，** 然后再PR_RTF_COMPRESSED调用 **RTFSync（** 如有必要）。 
  
如果 **PR_BODY** 对空格外的其他任何内容进行了修改，则邮件存储必须删除 **PR_RTF_IN_SYNC终止同步** 。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
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

