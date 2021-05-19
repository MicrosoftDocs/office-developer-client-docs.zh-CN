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
  
包含通常通过对象链接和嵌入 **IStream** 接口 (OLE) 二进制附件数据。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_DATA_BIN  <br/> |
|标识符:  <br/> |0x3701  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

当 **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值为 ATTACH_BY_VALUE 时，此属性保留附件，这是常用的 attachment 方法，也是唯一需要支持的方法。 **PR_ATTACH_DATA_BIN** OLE 1.0 OLESTREAM 附件时，PR_ATTACH_METHOD **OLESTREAM** **ATTACH_OLE。** 
  
 **OLESTREAM** 附件可以通过调用 OLE **IStream：：CopyTo** 方法复制到文件中。 OLE 编码类型可以从[PidTagAttachTag PR_ATTACH_TAG (PidTagAttachTag](pidtagattachtag-canonical-property.md)) 确定。  
  
对于 OLE 文档文件附件，邮件存储提供程序必须对 PR_ATTACH_DATA_OBJ ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md) **)** 上的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)调用做出响应，并且可以选择响应 **对 PR_ATTACH_DATA_BIN 的调用**。 请注意 **，PR_ATTACH_DATA_BIN** 和 **PR_ATTACH_DATA_OBJ** 共享同一属性标识符，因此是同一属性的两个表示形式。 
  
对于存储对象（如 OLE 2.0 docfile 格式的复合文件）来说，某些服务提供程序允许使用 MAPI **IStreamDocfile** 接口打开该对象，以提高性能。 支持 **IStreamDocfile** 的提供程序必须在 PR_ATTACH_DATA_OBJ 上公开它 **，** 并且可以选择在 PR_ATTACH_DATA_BIN 上 **公开** 它。 
  
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

