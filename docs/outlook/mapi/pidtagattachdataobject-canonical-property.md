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
ms.openlocfilehash: 3961330476cad8947f94152e49c90adb1e8f8b21
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339282"
---
# <a name="pidtagattachdataobject-canonical-property"></a>PidTagAttachDataObject 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个附件对象，该对象通常通过对象链接和嵌入 (OLE) **IStorage** 接口访问。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_DATA_OBJ  <br/> |
|标识符:  <br/> |0x3701  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

当 [PidTagAttachMethod PR_ATTACH_METHOD (PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性值为 ATTACH_EMBEDDED_MSG 或ATTACH_OLE 时，此属性将 **保留附件**。  可以从 [PidTagAttachTag](pidtagattachtag-canonical-property.md) **PR_ATTACH_TAG (** OLE 编码) 。 
  
对于与值关联的[ATTACH_EMBEDDED_MSG，IMessage：IMAPIProp](imessageimapiprop.md)接口可用于加快访问速度。  
  
对于嵌入的动态 OLE 对象 **，PR_ATTACH_DATA_OBJ** 属性包含其自己的呈现信息 **，PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 属性应为不存在或为空。 
  
对于 OLE 文档文件附件，邮件存储提供程序必须对 PR_ATTACH_DATA_OBJ 上的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 调用做出响应 **，** 并且可以选择响应 **对 PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 的调用。 属性 **PR_ATTACH_DATA_BIN** 和 **PR_ATTACH_DATA_OBJ** 属性共享同一属性标识符，因此是同一属性的两种表示形式。 
  
对于存储对象（如 OLE 2.0 docfile 格式的复合文件）来说，某些服务提供程序允许使用 MAPI **IStreamDocfile** 接口 **（IStream** 的子类）打开该对象，该接口没有其他成员，旨在优化性能。 潜在的保存足以证明尝试通过 **IStreamDocfile** **PR_ATTACH_DATA_OBJ** 打开文件。 如果 **MAPI_E_INTERFACE_NOT_SUPPORTED，** 客户端随后可以使用 **IStream** **PR_ATTACH_DATA_BIN** 文件。 
  
如果客户端应用程序或服务提供商无法使用在客户端应用程序或服务提供商的帮助下使用 PR_ATTACH_DATA_OBJ 打开附件子 **PR_ATTACH_METHOD，** 则 **它应** PR_ATTACH_DATA_BIN。 
  
有关 OLE 接口和格式的信息，请参阅 [OLE 和数据传输](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
## <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

