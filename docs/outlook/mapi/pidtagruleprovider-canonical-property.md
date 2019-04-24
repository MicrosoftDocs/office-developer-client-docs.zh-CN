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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 19889a1f48a6088f0d5ad224f7e9189b112622fa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280603"
---
# <a name="pidtagruleprovider-canonical-property"></a>PidTagRuleProvider 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含设置规则的应用程序的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RULE_PROVIDER、PR_RULE_PROVIDER_A、PR_RULE_PROVIDER_W  <br/> |
|标识符:  <br/> |0x6681  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>注解

延迟操作需要这些属性来标识必须解释和执行规则操作的代码。
  
存储在邮箱和文件夹中的规则与通过规则提供程序字符串拥有它们的应用程序相关联。 规则提供程序设置并处理规则表中的规则。 它还提供了一种方法来处理任何延迟操作 (如果设置了此类规则)。 延迟操作由信息存储隐式创建。 对于对不同存储的移动或复制操作, 如果提供程序设置了延迟操作规则, 则它必须提供一个处理程序, 以便在触发规则和创建延迟操作时执行该操作。
  
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

