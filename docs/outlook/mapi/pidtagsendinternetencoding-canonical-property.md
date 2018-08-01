---
title: PidTagSendInternetEncoding 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSendInternetEncoding
api_type:
- COM
ms.assetid: ae408b4f-dee3-484b-a19c-f472cfa95996
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b6814df2b28961be7e8c07a2d19932988605dc87
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778384"
---
# <a name="pidtagsendinternetencoding-canonical-property"></a>PidTagSendInternetEncoding 规范属性

  
  
**适用于**： Outlook 
  
包含编码首选项的位掩码。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SEND_INTERNET_ENCODING  <br/> |
|标识符：  <br/> |0x3A71  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>说明

设置此属性来指示使用的编码选项。 
  
此属性包含以下标志：
  
BODY_ENCODING_HTML 
  
> HTML 格式的消息文本进行编码。 除非设置了 ENCODING_MIME 标志，则忽略此标志。 
    
BODY_ENCODING_TEXT_AND_HTML 
  
> 编码为多用途 Internet 邮件扩展 (MIME) 的替代方案中使用的文本和 HTML 的消息文本。 除非设置了 ENCODING_MIME 标志，则忽略此标志。 
    
ENCODING_MIME 
  
> 编码使用 MIME 邮件。 如果未设置此标志，MAPI 对采用纯文本形式的消息文本和 UUENCODE 中的附件进行编码。 
    
ENCODING_PREFERENCE 
  
> 使用此位掩码中其他标志来确定编码。 如果未设置此标志，MAPI 使其消息的系统进行编码的决策。 
    
MAC_ATTACH_ENCODING_APPLEDOUBLE 
  
> 对在 Apple 双模式下的 Macintosh 附件进行编码。 除非设置了 ENCODING_MIME 标志，则忽略此标志。 
    
MAC_ATTACH_ENCODING_APPLESINGLE 
  
> 对在 Apple 单模式 Macintosh 附件进行编码。 除非设置了 ENCODING_MIME 标志，则忽略此标志。 
    
MAC_ATTACH_ENCODING_UUENCODE 
  
> 对在 UUENCODE Macintosh 附件进行编码。 如果设置了 ENCODING_MIME 标志，则忽略此标志并 BinHex 编码改为使用。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

