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
  
如果**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性的文本内容与此邮件的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性相同, 则该参数为 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RTF_IN_SYNC  <br/> |
|标识符:  <br/> |0x0E1F  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>注解

如果值为 TRUE, 则表示**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性、此邮件的纯文本版本和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性, rtf 格式 (rtf) 版本完全相同, 但**PR_RTF_COMPRESSED**中的**PR_BODY**和格式的空格。 这两个版本中的文本由相同序列中的相同字符组成。
  
如果值为 FALSE, 则表示两个版本不同步文本内容, 但可以通过[RTFSync](rtfsync.md)函数进行同步。 一个版本已更改, 另一个版本未更改。 
  
"无值" 表示两个版本 (如果存在或都已存在) 无法同步。 一个版本已被删除或更改, 因此不再可能进行同步。
  
已修改**PR_RTF_COMPRESSED**的客户端应用程序应将此属性中的值设置为 FALSE, 以强制进行同步。 RTF 感知邮件存储应在[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用过程中使用**RTFSync**执行同步。 RTF 感知客户端应先检查**PR_RTF_IN_SYNC**的设置, 然后再读取**PR_RTF_COMPRESSED**, 并在必要时先调用**RTFSync** 。 
  
如果**PR_BODY**对非空白区域的任何内容进行了修改, 邮件存储必须删除**PR_RTF_IN_SYNC**以终止同步。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
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

