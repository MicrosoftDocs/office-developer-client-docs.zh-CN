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
  
一个值, 它被解释为指定规则状态的标志的位掩码组合。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RULE_STATE  <br/> |
|标识符:  <br/> |0x6677  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>注解

下表定义了此属性的可能值。
  
EN (ST_ENABLED, 位掩码 0x00000001)
  
> 启用该规则以执行。 如果未设置此标志, 则在评估规则时, 服务器必须跳过此规则。
    
ER (ST_ERROR, 位掩码 0x00000002)
  
> 服务器在处理规则时遇到错误。
    
of (ST_ONLY_WHEN_OOF, 位掩码 0x00000004)
  
> 仅当用户在邮箱上设置了外出 (OOF) 状态时, 才会执行该规则。 此标志不得在公用文件夹规则中设置。
    
HI (ST_KEEP_OOF_HIST, 位掩码 0x00000008)
  
> 此标志不得在公用文件夹规则中设置。
    
EL (ST_EXIT_LEVEL, 位掩码 0x00000010)
  
> 规则评估将在执行此规则后结束, 但不会对外出规则进行评估。
    
SCL (ST_SKIP_IF_SCL_IS_SAFE, 位掩码 0x00000020)
  
> 可以跳过此规则的评估。
    
PE (ST_RULE_PARSE_ERROR, 位掩码 0x00000040)
  
> 服务器在分析客户端提供的规则数据时遇到错误。
    
X
  
> 此协议未使用。 客户端不得修改此位。
    
有关 ST_ONLY_WHEN_OOF 和 ST_EXIT_LEVEL 标志之间的交互的说明: 
  
当邮箱上设置了 "外出" 状态, 并且规则条件的计算结果为 TRUE 时, 
  
并
  
- 规则设置了 ST_EXIT_LEVEL 标志, 并且没有设置 ST_ONLY_WHEN_OOF 标志。 然后, 服务器不得评估未设置 ST_ONLY_WHEN_OOF 标志的后续规则, 并且必须评估具有 ST_ONLY_WHEN_OOF 标志集的后续规则。
    
和
  
- 该规则同时设置了 ST_EXIT_LEVEL 和 ST_ONLY_WHEN_OOF 标志。 然后, 服务器不能评估任何后续规则。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)
  
> 在服务器上操纵传入电子邮件。
    
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

