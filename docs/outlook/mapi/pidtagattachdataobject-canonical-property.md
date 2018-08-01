---
title: PidTagAttachDataObject 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachDataObject
api_type:
- HeaderDef
ms.assetid: b76312c6-7682-4ded-be25-55e21b0b091b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3fc7690a8c9eb2ada3a34bc44217ff463721e4d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777327"
---
# <a name="pidtagattachdataobject-canonical-property"></a>PidTagAttachDataObject 规范属性

  
  
**适用于**： Outlook 
  
包含通常通过对象链接和嵌入 (OLE) **IStorage**界面访问一个 attachment 对象。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_DATA_OBJ  <br/> |
|标识符：  <br/> |0x3701  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>说明

**ATTACH_EMBEDDED_MSG**或**ATTACH_OLE** **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值时，此属性包含附件。 可从**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 确定 OLE 编码类型。 
  
与**ATTACH_EMBEDDED_MSG**值相关联的附件， [IMessage:IMAPIProp](imessageimapiprop.md)接口可用于更快地访问。 
  
动态 OLE 嵌入对象， **PR_ATTACH_DATA_OBJ**属性包含自己呈现的信息，并**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 属性应为空或不存在。 
  
OLE 文档文件附件，消息存储提供程序必须响应上**PR_ATTACH_DATA_OBJ** [IMAPIProp::OpenProperty](imapiprop-openproperty.md)呼叫，并 （可选） 可能响应**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)上的呼叫). **PR_ATTACH_DATA_BIN**和**PR_ATTACH_DATA_OBJ**属性共享相同属性标识符，因此都是相同的属性的两个呈现形式。 
  
对于存储对象，例如复合文件格式 docfile OLE 2.0，某些服务提供商允许其使用 MAPI **IStreamDocfile**界面，不包含任何其他成员，旨在优化性能的**IStream**子类打开。 潜在保存已足够 justify 尝试打开**PR_ATTACH_DATA_OBJ**通过**IStreamDocfile**。 如果返回**MAPI_E_INTERFACE_NOT_SUPPORTED** ，客户端就可以与**IStream**中打开**PR_ATTACH_DATA_BIN** 。 
  
如果客户端应用程序或服务提供商不能使用**PR_ATTACH_METHOD**借助**PR_ATTACH_DATA_OBJ**打开附件子对象，它应使用**PR_ATTACH_DATA_BIN**。 
  
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

