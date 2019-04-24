---
title: PidTagAttachMimeTag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachMimeTag
api_type:
- HeaderDef
ms.assetid: cbc4585d-f970-4b22-ac08-d7fc91bff3d3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f05fa0816db3b412329372ad392c673c240eb59e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327242"
---
# <a name="pidtagattachmimetag-canonical-property"></a>PidTagAttachMimeTag 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关多用途 Internet 邮件扩展 (MIME) 附件的格式信息。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_MIME_TAG、PR_ATTACH_MIME_TAG_A、PR_ATTACH_MIME_TAG_W  <br/> |
|标识符:  <br/> |0x370E  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

如果**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 属性包含值**OID_MIMETAG**, 则传输提供程序应查看这些属性以确定如何设置附件格式。 
  
这些属性是从入站 MIME 标头的 Content type 参数中复制的。 字符串的组成定义在 RFC 1521 文档中。 格式为类型/子类型, 如应用程序/二进制或文本/纯文本。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[毫秒-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)
  
> 指定权限管理编码邮件的属性。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

