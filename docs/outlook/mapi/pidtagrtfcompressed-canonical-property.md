---
title: PidTagRtfCompressed 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfCompressed
api_type:
- COM
ms.assetid: fd0ccb88-55ce-4d7c-9573-6e5d6239b6a8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3091a76a1b755bf5a0d641ed9bd79bcfaa4641b7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357888"
---
# <a name="pidtagrtfcompressed-canonical-property"></a>PidTagRtfCompressed 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件文本的 rtf 格式 (rtf) 版本 (通常为压缩格式)。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RTF_COMPRESSED  <br/> |
|标识符:  <br/> |0x1009  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>注解

此属性包含的邮件文本与**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性相同, 但格式为 RTF。 
  
RTF 中的邮件文本通常以压缩形式存储。 但是, 有些系统不会压缩格式化文本。 为了适应它们, MAPI 提供了流头的 dwMagicUncompressedRTF 值, 以标识未压缩的 RTF 以及邮件的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 中的**STORE_UNCOMPRESSED_RTF**标志store 以指示它可以存储解压缩的 RTF。 
  
若要获取此属性的内容, 请调用**OpenProperty**, 然后使用**MAPI_READ**标志调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md) 。 若要写入此属性, 请使用**MAPI_MODIFY**和**MAPI_CREATE**标志打开它。 这可确保新数据完全替换所有旧数据, 并使用最小存储更新数执行写入操作。 
  
支持 RTF 的邮件存储将忽略对邮件文本中的空格所做的任何更改。 首次存储**PR_BODY**时, 邮件存储也会生成和存储此属性。 如果随后调用了[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法并修改了**PR_BODY** , 则邮件存储将调用[RTFSync](rtfsync.md)函数以确保与 RTF 版本同步。 如果只更改了空白, 则属性保持不变。 当邮件通过非 RTF 感知客户端和邮件系统传输时, 这将保留任何 nontrivial RTF 格式。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[毫秒-OXRTFCP]](https://msdn.microsoft.com/library/65dfe2df-1b69-43fc-8ebd-21819a7463fb%28Office.15%29.aspx)
  
> 对 RTF 邮件正文中的压缩流进行编码和解码。
    
[[毫秒-OXRTFEX]](https://msdn.microsoft.com/library/411d0d58-49f7-496c-b8c3-5859b045f6cf%28Office.15%29.aspx)
  
> 封装邮件和附件的 RTF 正文属性中的其他内容格式 (如 HTML)。
    
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

