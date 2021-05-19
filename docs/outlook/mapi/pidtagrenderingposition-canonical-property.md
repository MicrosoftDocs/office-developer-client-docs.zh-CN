---
title: PidTagRenderingPosition 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRenderingPosition
api_type:
- COM
ms.assetid: bce46687-17dc-4a3f-96be-303d8755158e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d463be4a14ecf478bdcbddc50b4ad9360829befc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355151"
---
# <a name="pidtagrenderingposition-canonical-property"></a>PidTagRenderingPosition 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于呈现主邮件文本中的附件的偏移（以字符表示）。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RENDERING_POSITION  <br/> |
|标识符:  <br/> |0x370B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 附件  <br/> |
   
## <a name="remarks"></a>备注

当提供的偏移量为 -1 (0xFFFFFFFF) ，则不通过使用此属性呈现附件。 除 -1 外的所有值都指示PidTagBody PR_BODY ([PidTagBody](pidtagbody-canonical-property.md)) 属性中要呈现附件的位置。
  
 **注意** 属性中的此属性指示的字符 **PR_BODY** 附件替换。 通常，此字符是一个空格，但也可使用特殊的占位符字符。 
  
此属性以字符表示。 在某些字符集，这不等同于字节。 Unicode 应用程序可以基于双字节字符计算位置。 Double-Byte DBCS (DBCS) 应用程序必须扫描此属性值前的文本，因为它们的字符表示形式因每个字符 1 到 2 个字节而异。
  
此属性不应与 RTF 格式或 RTF 格式 (一) 使用。 在 RTF 中，呈现位置由称为对象附件占位符的转义序列指示。 此序列由字符串后跟一个字符（通常为空格）组成，该字符  `\objattph` 将由附件呈现替换。 
  
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

