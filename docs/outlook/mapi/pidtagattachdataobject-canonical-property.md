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
  
包含通常通过对象链接和嵌入 (OLE) **IStorage**接口访问的附件对象。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_DATA_OBJ  <br/> |
|标识符:  <br/> |0x3701  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

如果**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值为**ATTACH_EMBEDDED_MSG**或**ATTACH_OLE**, 则此属性将保留附件。 可以从**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 确定 OLE 编码类型。 
  
对于与**ATTACH_EMBEDDED_MSG**值关联的附件, 可以使用[IMessage: IMAPIProp](imessageimapiprop.md)接口来实现更快的访问。 
  
对于嵌入的动态 OLE 对象, **PR_ATTACH_DATA_OBJ**属性包含其自己的呈现信息, 并且**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 属性不应为 "不存在" 或 "空"。 
  
对于 OLE 文档文件附件, 邮件存储提供程序必须响应**PR_ATTACH_DATA_OBJ**上的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)呼叫, 并且可以选择响应**PR_ATTACH_DATA_BIN**上的呼叫 ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md) )。). **PR_ATTACH_DATA_BIN**和**PR_ATTACH_DATA_OBJ**属性共享相同的属性标识符, 因此这是同一属性的两个格式副本。 
  
对于存储对象 (例如, 采用 OLE 2.0 docfile 格式的复合文件), 某些服务提供程序允许使用 MAPI **IStreamDocfile**接口打开它, 而没有其他成员的**IStream**子类将用于优化性能。 可能的保存足以证明试图通过**IStreamDocfile**打开**PR_ATTACH_DATA_OBJ** 。 如果返回**MAPI_E_INTERFACE_NOT_SUPPORTED** , 则客户端可以使用**IStream**打开**PR_ATTACH_DATA_BIN** 。 
  
如果客户端应用程序或服务提供程序无法通过使用**PR_ATTACH_DATA_OBJ**和**PR_ATTACH_METHOD**的帮助打开附件子方法, 则应使用**PR_ATTACH_DATA_BIN**。 
  
有关 ole 接口和格式的详细信息, 请参阅[ole and Data Transfer](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
## <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

