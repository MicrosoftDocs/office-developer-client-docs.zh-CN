---
title: PidTagRuleProvider 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleProvider
api_type:
- COM
ms.assetid: 64f80a03-9ba4-495a-9666-b3a909335cb6
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5456e0abffd1ac25983809d32fde88644eaa01cb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778291"
---
# <a name="pidtagruleprovider-canonical-property"></a>PidTagRuleProvider 规范属性

  
  
**适用于**： Outlook 
  
包含的应用程序设置规则的名称。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_RULE_PROVIDER，PR_RULE_PROVIDER_A，PR_RULE_PROVIDER_W  <br/> |
|标识符:  <br/> |0x6681  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>备注

延迟操作需要这些属性来标识的代码必须解释和执行规则操作。
  
规则存储邮箱和文件夹是拥有这些规则提供程序字符串的应用程序相关联。 规则提供程序设置，并处理规则表中的规则。 它还提供了一种如果设置此类规则处理所有延迟的操作。 信息存储隐式创建延迟的操作。 移动或复制到其他存储的操作，如果提供程序设置的延迟的操作规则，它必须提供一个处理程序以执行操作时触发规则并创建延迟的操作。
  
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
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

