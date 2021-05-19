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
  
包含 RTF 格式 (RTF) 格式的邮件文本版本，通常采用压缩形式。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RTF_COMPRESSED  <br/> |
|标识符:  <br/> |0x1009  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>备注

此属性包含与[PidTagBody](pidtagbody-canonical-property.md) 属性中的 PR_BODY (文本) RTF 中相同的消息文本。 
  
RTF 中的邮件文本通常以压缩形式存储。 但是，某些系统不压缩格式化文本。 为了容纳它们，MAPI 为流标头提供 dwMagicUncompressedRTF 值以标识未压缩的 RTF，为 **邮件** 存储提供 PR_STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 中的 **STORE_UNCOMPRESSED_RTF** 标志，以指示它可以存储未压缩的 RTF。 
  
若要获取此属性的内容，请调用 **OpenProperty**，然后调用 [WrapCompressedRTFStream](wrapcompressedrtfstream.md) 和 **MAPI_READ** 标志。 若要写入此属性，请用 MAPI_MODIFY **和** MAPI_CREATE **打开它** 。 这可确保新数据完全替换任何旧数据，并确保使用最少数量的存储更新执行写入。 
  
支持 RTF 的邮件存储将忽略对邮件文本中的空格的任何更改。 首次 **PR_BODY** 时，邮件存储还会生成并存储此属性。 如果[随后调用 IMAPIProp：：SaveChanges](imapiprop-savechanges.md)方法，PR_BODY修改了该函数，则消息存储将调用[RTFSync](rtfsync.md)函数以确保与 RTF 版本同步。 如果仅更改了空格，则属性保持不变。 这将在邮件通过非 RTF 感知客户端和邮件系统时保留任何非实时 RTF 格式。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXRTFCP]](https://msdn.microsoft.com/library/65dfe2df-1b69-43fc-8ebd-21819a7463fb%28Office.15%29.aspx)
  
> 对 RTF 邮件正文中的压缩流进行编码和解码。
    
[[MS-OXRTFEX]](https://msdn.microsoft.com/library/411d0d58-49f7-496c-b8c3-5859b045f6cf%28Office.15%29.aspx)
  
> 封装邮件和附件 (RTF 正文) HTML 格式等附加内容格式。
    
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

