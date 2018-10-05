---
title: PidTagExtendedRuleMessageActions 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExtendedRuleMessageActions
api_type:
- HeaderDef
ms.assetid: 1cf277d4-76ec-4902-9e54-f1780cee49bf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 70f09d6db5940fcb9b980cc839988113bd3a3e2e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399185"
---
# <a name="pidtagextendedrulemessageactions-canonical-property"></a>PidTagExtendedRuleMessageActions 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关文件夹关联的信息 （从故障） 消息中使用的命名属性的其他信息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EXTENDED_RULE_MSG_ACTIONS  <br/> |
|标识符：  <br/> |0x0E99  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Rules  <br/> |
   
## <a name="remarks"></a>说明

此属性必须设置对从故障邮件。 此属性的作用相同作为**PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md))，但包含版本的规则，以及规则操作中, 存储的命名的属性的其他信息，以及有关为操作的信息此规则执行。 用来包含操作的操作任何的缓冲区部分中包含的所有字符串值都必须为 Unicode 格式。
  
有关此二进制属性的格式的信息，请参阅[[MS OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范的参考正在
    
[[MS OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)
  
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

