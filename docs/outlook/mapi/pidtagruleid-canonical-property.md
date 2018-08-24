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
ms.openlocfilehash: 2831e31e8139dd2348c2deffa6da41793d0a3f4b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576244"
---
# <a name="pidtagruleid-canonical-property"></a>PidTagRuleId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定首次创建规则时，消息服务器将生成的每个规则的唯一标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RULE_ID  <br/> |
|标识符：  <br/> |0x6674  <br/> |
|数据类型：  <br/> |PT_I8  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>注解

客户端不能指定此属性时创建一个新规则，但必须指定时修改或删除规则。
  
如果删除规则，传递客户端必须仅属性为**PR_RULE_ID** ，并不应将传递中任何其他属性。 服务器必须忽略此属性之外的属性。 当添加规则中**PR_RULE_ID**, 不传递客户端，必须时，它必须**PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md))、 **PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md)) 和**PR_RULE_PROVIDER** ([中传递PidTagRuleProvider](pidtagruleprovider-canonical-property.md)) 属性。 修改的规则时, 客户端中**PR_RULE_ID**必须经过，并应传入需要进行修改的属性的其余部分。 
  
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



[PidTagRuleCondition 规范属性](pidtagrulecondition-canonical-property.md)
  
[PidTagRuleActions 规范属性](pidtagruleactions-canonical-property.md)
  
[PidTagRuleProvider 规范属性](pidtagruleprovider-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

