---
title: PidTagAttachDataBinary 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachDataBinary
api_type:
- HeaderDef
ms.assetid: 3b0a8b28-863e-4b96-a4c0-fdb8f40555b9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3646f3e3906e62fe148fe1c2b6ddca39013391e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777338"
---
# <a name="pidtagattachdatabinary-canonical-property"></a>PidTagAttachDataBinary 规范属性

  
  
**适用于**： Outlook 
  
包含通常通过对象链接和嵌入 (OLE) **IStream**接口访问的二进制附件数据。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_DATA_BIN  <br/> |
|标识符：  <br/> |0x3701  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>说明

此属性包含附件时**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值是 ATTACH_BY_VALUE，这是您的常用附件方法和必须支持的唯一一个。 **PR_ATTACH_DATA_BIN** ATTACH_OLE **PR_ATTACH_METHOD**的值时，还包含 OLE 1.0 **OLESTREAM**附件。 
  
 **OLESTREAM**附件可以复制到文件中，通过调用 OLE **IStream::CopyTo**方法。 可以从**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 属性确定 OLE 编码类型。 
  
OLE 文档文件附件，消息存储提供程序必须响应[IMAPIProp::OpenProperty](imapiprop-openproperty.md)呼叫的**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))，并 （可选） 可能响应**PR_ATTACH_DATA_BIN 上的呼叫**. 请注意， **PR_ATTACH_DATA_BIN**和**PR_ATTACH_DATA_OBJ**共享相同属性标识符，因此都是相同的属性的两个呈现形式。 
  
对于存储对象，例如复合文件格式 docfile OLE 2.0，某些服务提供商允许其打开与 MAPI **IStreamDocfile**接口以提高性能。 支持**IStreamDocfile**的提供程序必须公开其**PR_ATTACH_DATA_OBJ**上，并可能 （可选） 将其公开**PR_ATTACH_DATA_BIN**上。 
  
OLE 接口和格式的详细信息，请参阅[OLE 和数据传输](http://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
## <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

