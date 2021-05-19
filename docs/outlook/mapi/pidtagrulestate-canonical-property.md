---
title: PidTagRuleState 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleState
api_type:
- COM
ms.assetid: f62f3055-b855-4203-aa5c-6ba28b58c6f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a0e15462cd3dc14c93155e34e47b7caac2c04087
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338610"
---
# <a name="pidtagrulestate-canonical-property"></a>PidTagRuleState 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
解释为指定规则状态的标志的位掩码组合的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RULE_STATE  <br/> |
|标识符:  <br/> |0x6677  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>备注

下表定义了此属性的可能值。
  
EN (ST_ENABLED、位掩码0x00000001) 
  
> 规则已启用以执行。 如果未设置此标志，则服务器在评估规则时必须跳过此规则。
    
ER (ST_ERROR、位掩码0x00000002) 
  
> 服务器在处理规则时遇到错误。
    
OF (ST_ONLY_WHEN_OOF、位掩码0x00000004) 
  
> 仅在用户对邮箱设置 Out of Office (OOF) 时执行规则。 此标志不得在公用文件夹规则中设置。
    
HI (ST_KEEP_OOF_HIST、位掩码0x00000008) 
  
> 此标志不得在公用文件夹规则中设置。
    
EL (ST_EXIT_LEVEL、位掩码0x00000010) 
  
> 规则评估将在执行此规则后结束，但评估"外出"规则Office除外。
    
SCL (ST_SKIP_IF_SCL_IS_SAFE位掩码0x00000020) 
  
> 可能会跳过此规则的评估。
    
PE (ST_RULE_PARSE_ERROR、位掩码0x00000040) 
  
> 服务器在解析客户端提供的规则数据时遇到错误。
    
X
  
> 此协议未使用。 客户端不得修改此位。
    
有关标记与ST_ONLY_WHEN_OOF ST_EXIT_LEVEL交互的注意事项： 
  
在邮箱上设置"out of Office"状态，且规则条件计算结果为 TRUE 时， 
  
AND：
  
- 规则已设置ST_EXIT_LEVEL标志，并且未ST_ONLY_WHEN_OOF该标志。 然后，服务器不得评估未设置标志ST_ONLY_WHEN_OOF规则，并且必须评估已设置ST_ONLY_WHEN_OOF规则。
    
或者：
  
- 规则同时设置了 ST_EXIT_LEVEL 和 ST_ONLY_WHEN_OOF 标志。 然后，服务器不得评估任何后续规则。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)
  
> 在服务器上处理传入电子邮件。
    
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

