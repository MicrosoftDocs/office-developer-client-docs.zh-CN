---
title: PidLidValidFlagStringProof 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidValidFlagStringProof
api_type:
- COM
ms.assetid: e5a94968-7e84-4faf-8104-9ea36d35fa1a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dfe3b57c246e247eda365bed46af2e0f35f0e54b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315384"
---
# <a name="pidlidvalidflagstringproof-canonical-property"></a>PidLidValidFlagStringProof 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证**dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 属性的值是否由知道**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) 属性值的代理设置。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidValidFlagStringProof  <br/> |
|属性集:  <br/> |PSETID_Common  <br/> |
|长 ID (盖子):  <br/> |0x000085BF  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>注解

在非可发送对象 (收到的邮件和非邮件对象) 中, 客户端应在修改**dispidRequest**时将此值设置为**PR_MESSAGE_DELIVERY_TIME**的值。
  
由于发件人无法预测**PR_MESSAGE_DELIVERY_TIME**的值, 如果此属性的值等于**PR_MESSAGE_DELIVERY_TIME**的值, 则可以确定**dispidRequest**的值不是来自邮件的发件人。 客户端可以根据客户端的特定安全策略, 决定如何根据此比较的结果向最终用户显示**dispidRequest**的值。 如果由于**dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)) 值的存在而忽略**dispidRequest**的值, 则必须忽略此属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定与标记相关的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[PidTagMessageDeliveryTime 规范属性](pidtagmessagedeliverytime-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

