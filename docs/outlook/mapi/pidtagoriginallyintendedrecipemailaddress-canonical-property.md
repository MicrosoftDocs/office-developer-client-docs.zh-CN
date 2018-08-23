---
title: PidTagOriginallyIntendedRecipEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginallyIntendedRecipEmailAddress
api_type:
- COM
ms.assetid: 6a85b695-731a-4401-9c9c-fda6bc308558
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f4adbdfc041ebe5213c384db98343baa82af5b05
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572723"
---
# <a name="pidtagoriginallyintendedrecipemailaddress-canonical-property"></a>PidTagOriginallyIntendedRecipEmailAddress 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含自动转发邮件的最初预期接收人的电子邮件地址。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS，PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS_A，PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS_W  <br/> |
|标识符：  <br/> |0x007C  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |Server  <br/> |
   
## <a name="remarks"></a>注解

这些属性是在最初预期的邮件收件人的地址属性的示例。 它们必须已转发邮件的自动代理设置。
  
这些属性对应于 X.400 报告每个收件人属性。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

