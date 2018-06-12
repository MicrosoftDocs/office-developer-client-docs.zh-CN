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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c93d850551e766e97292d5417c3be5577f557af0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778251"
---
# <a name="pidtagrtfcompressed-canonical-property"></a>PidTagRtfCompressed 规范属性

  
  
**适用于**： Outlook 
  
包含消息文本，通常在压缩的窗体中的富文本格式 (RTF) 版本。 
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_RTF_COMPRESSED  <br/> |
|标识符:  <br/> |0x1009  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Email  <br/> |
   
## <a name="remarks"></a>备注

此属性包含相同的消息文本作为**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性，但以 rtf 格式。 
  
压缩的窗体中通常存储以 rtf 格式的消息文本。 但是，某些系统不压缩格式的文本。 若要容纳它们，MAPI，提供了标识未压缩的 RTF 和**STORE_UNCOMPRESSED_RTF**标志**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 中的邮件流标头的 dwMagicUncompressedRTF 值存储以指示它可以存储未压缩的 RTF。 
  
若要获得此属性的内容，呼叫**OpenProperty**，然后呼叫[WrapCompressedRTFStream](wrapcompressedrtfstream.md) **MAPI_READ**标志。 要写入此属性，请使用**MAPI_MODIFY**和**MAPI_CREATE**标志打开它。 这样可确保新数据完全替换任何旧数据和使用存储更新的最小数目执行写入操作。 
  
支持 RTF 的消息存储忽略空格消息文本中的任何更改。 当**PR_BODY**存储首次时，消息存储还生成该文件，并将此属性存储。 如果[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法之后调用和已修改**PR_BODY** ，消息存储调用[RTFSync](rtfsync.md)函数，以确保与 RTF 版本同步。 属性如果只已更改的空白区域，将保留不变。 这会保留任何不常用 RTF 格式时通过非 RTF 感知客户端的消息传输和邮件系统。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXRTFCP]](http://msdn.microsoft.com/library/65dfe2df-1b69-43fc-8ebd-21819a7463fb%28Office.15%29.aspx)
  
> 进行编码和解码 RTF 邮件正文中的压缩文件的流。
    
[[MS OXRTFEX]](http://msdn.microsoft.com/library/411d0d58-49f7-496c-b8c3-5859b045f6cf%28Office.15%29.aspx)
  
> 邮件和附件的 RTF body 属性中封装 （如 HTML) 的其他内容的格式。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

