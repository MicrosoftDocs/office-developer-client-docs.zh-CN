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
ms.openlocfilehash: 23d943d5576f5e9d7694b03c90dea79a878dee64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777380"
---
# <a name="pidtagbody-canonical-property"></a>PidTagBody 规范属性

  
  
**适用于**： Outlook 
  
包含消息文本。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_BODY，PR_BODY_A，PR_BODY_W  <br/> |
|标识符：  <br/> |0x1000  <br/> |
|数据类型：  <br/> |PT_UNICODE PT_STRING8  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

通常只能在人际邮件 (IPM) 中使用这些属性。 
  
支持富文本格式 (RTF) 的消息存储忽略空格消息文本中的任何更改。 当**PR_BODY**存储首次时，消息存储还将生成该文件，并将存储**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性，消息文本的 RTF 版本。 如果[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法之后调用和已修改**PR_BODY** ，消息存储调用[RTFSync](rtfsync.md)函数，以确保与 RTF 版本同步。 属性如果只已更改的空白区域，将保留不变。 这会保留任何不常用 RTF 格式时通过非 RTF 感知客户端的消息传输和邮件系统。 
  
此属性的值必须用表示操作系统 MAPI 正在运行的代码页。 
  
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



[PidTagRtfInSync 规范属性](pidtagrtfinsync-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

