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
  
包含一个值, 该值将传输中性封装格式 (TNEF) 附件与邮件关联起来。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TNEF_CORRELATION_KEY  <br/> |
|标识符:  <br/> |0x007F  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>注解

建议 TNEF 附件子对象公开此属性。 此属性确定入站 TNEF 文件是否属于它所附加到的邮件。 它主要由传输提供程序和网关使用。
  
在出站邮件中, 传输提供程序应计算该邮件的唯一的二进制值, 或使用满足唯一性要求的现有值, 例如邮件标识符。 传输提供程序应将此值存储在此属性中, 然后调用[ITnef:: AddProps](itnef-addprops.md)方法将其封装。 相同的值还应存储在传输信封中, 在提供商定义的位置 (如邮件头) 中。 
  
在入站邮件中, 传输提供程序应调用[ITnef:: ExtractProps](itnef-extractprops.md)方法以 decapsulate TNEF 附件, 然后将此属性与存储在传输信封中的值进行比较。 如果值匹配, TNEF 应正常处理, 也就是说, 应使用从 TNEF 附件提取的所有属性。 如果值不匹配, 应忽略 TNEF 附件中的所有属性。 如果未设置此属性, 则 TNEF 文件应被视为属于此邮件, 并且应使用从该邮件中提取的其他属性。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端与服务器之间的数据传输的顺序和流。
    
[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码并解码为高效流表示形式。
    
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

