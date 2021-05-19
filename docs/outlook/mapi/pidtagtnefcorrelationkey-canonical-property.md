---
title: PidTagTnefCorrelationKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTnefCorrelationKey
api_type:
- COM
ms.assetid: a7f05c8c-59b4-4d5b-8e70-ebcde5f2ed45
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e38cf93523c14d2d58c48e24a79249674298b4b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341949"
---
# <a name="pidtagtnefcorrelationkey-canonical-property"></a>PidTagTnefCorrelationKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个值，该值将传输中性封装格式 (TNEF) 邮件关联。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TNEF_CORRELATION_KEY  <br/> |
|标识符:  <br/> |0x007F  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

建议 TNEF 附件子对象公开此属性。 此属性确定入站 TNEF 文件是否属于它所附加到的邮件。 它主要由传输提供程序和网关使用。
  
在出站邮件上，传输提供程序应计算该邮件特有的二进制值，或使用满足唯一性要求的现有值，如邮件标识符。 传输提供程序应在此属性中存储此值，然后调用 [ITnef：：AddProps](itnef-addprops.md) 方法来封装它。 同一值还应存储在提供程序定义的传输信封中，如邮件头。 
  
在入站邮件上，传输提供程序应调用 [ITnef：：ExtractProps](itnef-extractprops.md) 方法来解压缩 TNEF 附件，然后将此属性与传输信封中存储的值进行比较。 如果值匹配，则应该正常处理 TNEF，即，应该使用从 TNEF 附件中提取的所有属性。 如果值不匹配，应忽略 TNEF 附件的所有属性。 如果未设置此属性，则 TNEF 文件应视为属于此消息，并且应该使用从中提取的其他属性。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端和服务器之间数据传输的顺序和流。
    
[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码和解码为有效的流表示形式。
    
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

