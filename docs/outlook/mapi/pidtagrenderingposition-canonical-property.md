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
  
包含在主邮件文本中呈现附件时要使用的偏移量 (以字符为单位)。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RENDERING_POSITION  <br/> |
|标识符:  <br/> |0x370B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 附件  <br/> |
   
## <a name="remarks"></a>注解

当提供的偏移量为-1 (0xffffffff) 时, 不使用此属性呈现附件。 -1 以外的所有值指示要在**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中呈现附件的位置。
  
 **注释**由**PR_BODY**中的此属性指示的字符将替换为附件。 通常, 此字符是一个空格, 尽管也可以使用一个特殊的占位符字符。 
  
此属性以字符表示。 在某些字符集中, 这与字节不等效。 Unicode 应用程序可以基于双字节字符计算位置。 双字节字符集 (DBCS) 应用程序必须将文本扫描到此属性值, 因为它们的字符表示形式在每个字符的1到2个字节之间有所不同。
  
此属性不应用于 rtf 格式文本。 呈现位置通过称为对象附件占位符的转义序列以 RTF 表示。 此序列由后跟单个`\objattph`字符 (通常为空格) 的字符串组成, 附件呈现将替换该字符串。 
  
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

