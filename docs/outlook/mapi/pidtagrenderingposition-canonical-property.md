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
ms.openlocfilehash: aa149a81102a4981712ea3ca897d8b1ad448a1eb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778201"
---
# <a name="pidtagrenderingposition-canonical-property"></a>PidTagRenderingPosition 规范属性

  
  
**适用于**： Outlook 
  
包含偏移量，以字符，用于在呈现主消息文本中的附件。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RENDERING_POSITION  <br/> |
|标识符：  <br/> |0x370B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 附件  <br/> |
   
## <a name="remarks"></a>说明

时提供的偏移量为-1 (0xFFFFFFFF)，则不使用此属性中呈现附件。 -1 以外的所有值都指示频率附件是要呈现的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中的位置。
  
 **注释**附件被替换**PR_BODY**中此属性指定的字符。 通常该字符为一个空格，但也可以使用特殊的占位符。 
  
此属性以字符为单位。 在某些字符集这是不等于字节。 Unicode 应用程序可以计算基于双字节字符的位置。 双字节字符集 (DBCS) 应用程序必须扫描的文本，最多为此属性值，因为其字符表示形式而异每个字符的一和第二个字节。
  
使用富文本格式 (RTF) 文本，不应使用此属性。 呈现位置的转义序列调用对象的附件占位符指示以 rtf 格式。 此序列包含字符串`\objattph`跟单个字符，通常空格将替换为附件呈现。 
  
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



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

