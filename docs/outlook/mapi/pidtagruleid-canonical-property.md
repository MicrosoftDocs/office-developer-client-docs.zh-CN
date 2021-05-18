---
title: PidTagRuleId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleId
api_type:
- COM
ms.assetid: 341e8db0-52b7-4ba7-aaa6-eedf2783b4e8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8d88838893836c550136be9556299258b44e3e49
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359491"
---
# <a name="pidtagruleid-canonical-property"></a>PidTagRuleId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定邮件服务器在首次创建规则时为每条规则生成的唯一标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RULE_ID  <br/> |
|标识符:  <br/> |0x6674  <br/> |
|数据类型：  <br/> |PT_I8  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>备注

客户端在创建新规则时不得指定此属性，但在修改或删除规则时必须指定此属性。
  
删除规则时，客户端必须传递的唯一属性是 **PR_RULE_ID，并且** 不应传递任何其他属性。 服务器必须忽略除此属性外的属性。 添加规则时，客户端不得传递 **PR_RULE_ID，** 它必须传递 **PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md)) 、PR_RULE_ACTIONS ([PidTagRuleActions](pidtagruleactions-canonical-property.md)) 和 **PR_RULE_PROVIDER** ([PidTagRuleProvider](pidtagruleprovider-canonical-property.md)) 属性。 修改规则时，客户端必须PR_RULE_ID，并且应传递需要修改的其余属性。 
  
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



[PidTagRuleCondition 规范属性](pidtagrulecondition-canonical-property.md)
  
[PidTagRuleActions 规范属性](pidtagruleactions-canonical-property.md)
  
[PidTagRuleProvider 规范属性](pidtagruleprovider-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

