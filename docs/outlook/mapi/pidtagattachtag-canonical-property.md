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
ms.openlocfilehash: 5a908b3543dff5cf011c9bd4d5d05b3a07004ead
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361080"
---
# <a name="pidtagattachtag-canonical-property"></a>PidTagAttachTag 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 ASN. 1 对象标识符, 用于指定提供附件的应用程序。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_TAG  <br/> |
|标识符:  <br/> |0x370A  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

此属性标识最初生成附件的应用程序。
  
 **注释**不应混淆**PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md)) 和**PR_ATTACH_TAG**属性。 它们不是成对的, 也不是相关的。 **PR_ATTACH_ENCODING**标识用于转换附件中的数据的算法。 "对象" 在术语对象标识符中具有更常见的含义, 在与面向对象的编程中使用的是 X-400。 
  
对象标识符语法和示例对象标识符是在 MAPIOID 中定义的。H 头文件。 **PR_ATTACH_TAG**的值不限于在 MAPIOID 中定义的那些值。水平. 
  
有关这些对象标识符的完整信息, 请参阅 ASN. 1、x 208 和209个的相关文档。 对象标识符位于文件传输正文部件 (FTBP) 环境的应用程序引用元素中。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagAttachMimeTag 规范属性](pidtagattachmimetag-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

