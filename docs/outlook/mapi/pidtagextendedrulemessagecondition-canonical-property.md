---
title: PidTagExtendedRuleMessageCondition 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExtendedRuleMessageCondition
api_type:
- HeaderDef
ms.assetid: 891851e1-e4a4-4c20-a26c-7223bcca35f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 92008a387bb0130207af012df209a3aa6881d40e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593170"
---
# <a name="pidtagextendedrulemessagecondition-canonical-property"></a>PidTagExtendedRuleMessageCondition 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含有关包含在扩展的规则条件的任何命名属性的信息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EXTENDED_RULE_MSG_CONDITION  <br/> |
|标识符：  <br/> |0x0E9A  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Rules  <br/> |
   
## <a name="remarks"></a>注解

此属性必须设置对从故障邮件。 它**PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md)) 的作用相同，但包含有关使用的命名属性的其他信息。 此条件属性值的任何部分中包含的所有字符串值都必须为 Unicode 格式。
  
有关此二进制属性的格式的信息，请参阅[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)
  
> 处理传入的电子邮件服务器上。
    
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

