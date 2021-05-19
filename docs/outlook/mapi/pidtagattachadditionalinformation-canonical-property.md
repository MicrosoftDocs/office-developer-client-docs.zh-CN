---
title: PidTagAttachAdditionalInformation 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachAdditionalInformation
api_type:
- HeaderDef
ms.assetid: 75f092f2-ee3f-45c2-a46f-e1dff2e22b2e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e0a8f49f96bf4c4f8518dddbe52e8692f7b6645a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339870"
---
# <a name="pidtagattachadditionalinformation-canonical-property"></a>PidTagAttachAdditionalInformation 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供非附件的文件类型Windows信息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_ADDITIONAL_INFO  <br/> |
|标识符:  <br/> |0x370F  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

此属性基于附件的编码提供有关特定附件的元数据。 例如，当 **PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md)) 属性包含 MacBinary 时 **，PR_ATTACH_ADDITIONAL_INFO** 将包含一个字符串，表示 Macintosh 文件创建者和文件类型，格式化为编码的 Macintosh 文件的"：CREA：TYPE"。 
  
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

