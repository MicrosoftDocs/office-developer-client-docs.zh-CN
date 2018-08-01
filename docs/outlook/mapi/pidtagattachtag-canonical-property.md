---
title: PidTagAttachTag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachTag
api_type:
- HeaderDef
ms.assetid: 3d223809-b697-47c6-bc3c-2206aff7ad33
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d8d8d32bddb98e0ac180b0898478c67297980492
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777386"
---
# <a name="pidtagattachtag-canonical-property"></a>PidTagAttachTag 规范属性

  
  
**适用于**： Outlook 
  
包含指定的应用程序提供附件 ASN.1 对象标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_TAG  <br/> |
|标识符：  <br/> |0x370A  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>说明

此属性标识最初生成附件的应用程序。
  
 **注释**不能混淆**PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md)) 和**PR_ATTACH_TAG**属性。 它们不是配对或相关。 **PR_ATTACH_ENCODING**标识用于转换附件中的数据的算法。 "对象"具有更常规的含义和 X.400 使用率中的术语对象标识符，比在面向对象的编程。 
  
MAPIOID 中定义的对象标识符语法和示例对象标识符。H 头文件。 **PR_ATTACH_TAG**值不限于 MAPIOID 中定义的值。H。 
  
有关这些对象标识符的完整信息，请参阅 ASN.1、 X.208 和 X.209 上的文档。 文件传输正文部分 (FTBP) 环境的应用程序引用元素中找到对象标识符。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagAttachMimeTag 规范属性](pidtagattachmimetag-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

