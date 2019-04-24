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
ms.openlocfilehash: 1a5f8688b8ea747590cf2a2d6d5efb271aa488f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356544"
---
# <a name="pidtagattachdatabinary-canonical-property"></a>PidTagAttachDataBinary 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含通常通过对象链接和嵌入 (OLE) **IStream**接口访问的二进制附件数据。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_DATA_BIN  <br/> |
|标识符:  <br/> |0x3701  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

当**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值为 ATTACH_BY_VALUE 时, 此属性将保留附件, 这是常用的附件方法, 并且是需要支持的唯一一个。 当**PR_ATTACH_METHOD**的值为 ATTACH_OLE 时, **PR_ATTACH_DATA_BIN**还保留 OLE 1.0 **OLESTREAM**附件。 
  
 通过调用 OLE **IStream:: CopyTo**方法, 可以将**OLESTREAM**附件复制到文件中。 可以通过**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 属性确定 OLE 编码类型。 
  
对于 OLE 文档文件附件, 邮件存储提供程序必须响应**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 上的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)呼叫, 并且可以选择响应对 PR_ATTACH_DATA_BIN 的呼叫。 ****. 请注意, **PR_ATTACH_DATA_BIN**和**PR_ATTACH_DATA_OBJ**共享相同的属性标识符, 因此这是同一属性的两个格式副本。 
  
对于存储对象 (如采用 OLE 2.0 docfile 格式的复合文件), 一些服务提供程序允许使用 MAPI **IStreamDocfile**接口打开它, 以提高性能。 支持**IStreamDocfile**的提供程序必须在**PR_ATTACH_DATA_OBJ**中公开它, 并且可以选择在**PR_ATTACH_DATA_BIN**上公开它。 
  
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

