---
title: PidTagAttachEncoding 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachEncoding
api_type:
- HeaderDef
ms.assetid: 3b30cec6-da1e-4ef1-8c17-24b66f31cf0a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4bda4783012a3a5cd50d9c0aea6a37ccd238b660
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345491"
---
# <a name="pidtagattachencoding-canonical-property"></a>PidTagAttachEncoding 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含指定附件编码的 ASN.1 对象标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_ENCODING  <br/> |
|标识符:  <br/> |0x3702  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

此属性标识用于转换附件中数据的算法。
  
 **注意** 不应 **混淆 PR_ATTACH_ENCODING** **PR_ATTACH_TAG (** [PidTagAttachTag) 和 PidTagAttachTag](pidtagattachtag-canonical-property.md) 属性。 它们不配对或相关。 **PR_ATTACH_TAG** 标识最初生成附件的应用程序。 "对象"在术语对象标识符和 X.400 中比在面向对象的编程中具有更为一般的含义。 
  
对象标识符语法和示例对象标识符在 MAPIOID 中定义。H 头文件。 值 **PR_ATTACH_ENCODING** MAPIOID.H 中定义的值。 例如，附加的 Macintosh 文件可以使用标识符（如 MacBinary）。 
  
有关这些对象标识符的完整信息，请参阅有关 ASN.1、X.208 和 X.209 的文档。 对象标识符位于 FTBP 文件传输正文部分 (应用程序引用) 元素。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

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

