---
title: PidTagRuleLevel 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleLevel
api_type:
- COM
ms.assetid: b1a30543-250d-4afb-87f2-448d90ee7cf9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3de5093f1fa395b1fba061f88a9b67b5dedf4740
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359526"
---
# <a name="pidtagrulelevel-canonical-property"></a>PidTagRuleLevel 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含规则的退出级别。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RULE_LEVEL  <br/> |
|标识符:  <br/> |0x6683  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>注解

如果设置此属性, 则客户端必须在0x00000000 中传递。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历项目代表另一个用户操作时与之进行交互的方法。
    
[[毫秒-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)
  
> 在服务器上操纵传入电子邮件。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

