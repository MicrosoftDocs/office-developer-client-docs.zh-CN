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
ms.openlocfilehash: 519ee2b91275e4253845afa35a9a80470071966d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778297"
---
# <a name="pidtagrulestate-canonical-property"></a>PidTagRuleState 规范属性

  
  
**适用于**： Outlook 
  
解释指定规则的状态标志的位掩码组合为一个值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RULE_STATE  <br/> |
|标识符：  <br/> |0x6677  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>说明

下表定义了此属性的可能值。
  
EN （ST_ENABLED、 位掩码 0x00000001）
  
> 执行启用规则。 如果未设置此标志，服务器在计算规则时必须跳过此规则。
    
紧急 （ST_ERROR、 位掩码 0x00000002:uc）
  
> 服务器遇到错误处理规则。
    
(ST_ONLY_WHEN_OOF，位掩码 0x00000004)
  
> 仅当用户邮箱上设置外出 (OOF) 状态时，才执行规则。 未必须在公用文件夹规则中设置此标志。
    
你好 （ST_KEEP_OOF_HIST、 位掩码 0x00000008）
  
> 未必须在公用文件夹规则中设置此标志。
    
EL （ST_EXIT_LEVEL、 位掩码 0x00000010）
  
> 规则评估将结束后执行此规则的外出规则评估除外。
    
SCL （ST_SKIP_IF_SCL_IS_SAFE、 位掩码 0x00000020）
  
> 可能会跳过此规则的评估。
    
PE （ST_RULE_PARSE_ERROR、 位掩码 0x00000040）
  
> 服务器遇到错误分析所提供由客户端规则数据。
    
X
  
> 未使用此协议。 由客户端不能修改此位。
    
请注意上 ST_ONLY_WHEN_OOF 和 ST_EXIT_LEVEL 之间的交互标志： 
  
当邮箱，设置"外出"状态和一个规则条件的计算结果为 TRUE， 
  
和：
  
- 规则已设置了 ST_EXIT_LEVEL 标记，并且没有设置 ST_ONLY_WHEN_OOF 标志。 然后，服务器必须不会评估后续规则不具有 ST_ONLY_WHEN_OOF 标记集和必须评估设置 ST_ONLY_WHEN_OOF 标志的后续规则。
    
OR:
  
- 规则均具有的 ST_EXIT_LEVEL 和 ST_ONLY_WHEN_OOF 设置的标志。 然后，服务器必须不会评估任何后续规则。
    
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

