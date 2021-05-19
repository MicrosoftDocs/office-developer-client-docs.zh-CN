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
ms.openlocfilehash: e157fa640026d13362084b30ad73cdb66a0b35b5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342670"
---
# <a name="pidtagsendinternetencoding-canonical-property"></a>PidTagSendInternetEncoding 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含编码首选项的位掩码。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SEND_INTERNET_ENCODING  <br/> |
|标识符:  <br/> |0x3A71  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |地址  <br/> |
   
## <a name="remarks"></a>备注

设置此属性以指示使用的编码选项。 
  
此属性包含以下标志：
  
BODY_ENCODING_HTML 
  
> 使用 HTML 对邮件文本进行编码。 此标志将被忽略，除非ENCODING_MIME标志。 
    
BODY_ENCODING_TEXT_AND_HTML 
  
> 使用文本和 HTML 将邮件文本编码为多用途 Internet 邮件扩展 (MIME) 多部分替代项。 此标志将被忽略，除非ENCODING_MIME标志。 
    
ENCODING_MIME 
  
> 使用 MIME 对邮件进行编码。 如果未设置此标志，MAPI 会用纯文本和 UUENCODE 中的附件对邮件文本进行编码。 
    
ENCODING_PREFERENCE 
  
> 使用此位掩码中的其他标志可确定编码。 如果未设置此标志，MAPI 会保留它给邮件系统，以做出编码决策。 
    
MAC_ATTACH_ENCODING_APPLEDOUBLE 
  
> 在 Apple 双模式下对 Macintosh 附件进行编码。 此标志将被忽略，除非ENCODING_MIME标志。 
    
MAC_ATTACH_ENCODING_APPLESINGLE 
  
> 在 Apple 单一模式下对 Macintosh 附件进行编码。 此标志将被忽略，除非ENCODING_MIME标志。 
    
MAC_ATTACH_ENCODING_UUENCODE 
  
> 使用 UUENCODE 对 Macintosh 附件进行编码。 如果ENCODING_MIME，则忽略此标志，而改为使用 BinHex 编码。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定电子邮件对象允许的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

