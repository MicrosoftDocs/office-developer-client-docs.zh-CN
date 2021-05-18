---
title: PidTagBody 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagBody
api_type:
- HeaderDef
ms.assetid: 47c0d0fe-4d57-4b81-bdb5-336de85c194c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 243a59798980d8c0cfaf1a726d6408dbd66ebba8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326633"
---
# <a name="pidtagbody-canonical-property"></a>PidTagBody 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含消息文本。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_BODY、PR_BODY_A、PR_BODY_W  <br/> |
|标识符:  <br/> |0x1000  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

这些属性通常仅用于 IPM (的) 。 
  
支持 RTF 格式的邮件存储 (RTF) 忽略对邮件文本中的空格的任何更改。 首次 **PR_BODY** 时，邮件存储还会生成并存储 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性，即消息文本的 RTF 版本。 如果[随后调用 IMAPIProp：：SaveChanges](imapiprop-savechanges.md)方法，PR_BODY修改了该函数，则消息存储将调用[RTFSync](rtfsync.md)函数以确保与 RTF 版本同步。 如果仅更改了空格，则属性保持不变。 这将在邮件通过非 RTF 感知客户端和邮件系统时保留任何非实时 RTF 格式。 
  
此属性的值必须用运行 MAPI 的操作系统的代码页表示。 
  
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



[PidTagRtfInSync 规范属性](pidtagrtfinsync-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

