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
ms.openlocfilehash: 760196668ffb3c486803f27b50ff809177e8e6f3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588613"
---
# <a name="pidtagtnefcorrelationkey-canonical-property"></a>PidTagTnefCorrelationKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个值，对应一条消息的传输中性封装格式 (TNEF) 附件。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TNEF_CORRELATION_KEY  <br/> |
|标识符：  <br/> |0x007f 来  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>注解

建议 TNEF 附件子对象公开此属性。 此属性确定的入站的 TNEF 文件属于附加到邮件。 主要由传输提供程序和网关使用它。
  
对出站邮件传输提供程序应计算对该邮件，唯一的二进制值或使用现有值满足唯一性要求，如消息标识符。 传输提供程序应将此值存储在此属性，然后调用它封装的[ITnef::AddProps](itnef-addprops.md)方法。 相同的值还应存储在提供程序，如邮件头定义的位置中的传输信封。 
  
对入站邮件传输提供程序应呼叫确实 TNEF 附件[ITnef::ExtractProps](itnef-extractprops.md)方法，然后将此属性存储在传输信封中的值进行比较。 如果值匹配，通常应处理 TNEF，即，应使用 TNEF 附件从提取的所有属性。 如果值不匹配，应忽略 TNEF 附件中的所有属性。 如果未设置此属性，应考虑 TNEF 文件属于此消息，并应从其提取的其他属性。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理顺序和客户端和服务器之间的数据传输的流。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 进行编码和解码为有效的流表示形式的消息和附件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

