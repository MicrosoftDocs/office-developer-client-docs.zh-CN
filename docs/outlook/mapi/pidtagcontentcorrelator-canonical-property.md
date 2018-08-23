---
title: PidTagContentCorrelator 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentCorrelator
api_type:
- HeaderDef
ms.assetid: 0bf78879-2f9f-4c29-b1f4-2f4882d8464d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6398acf71e62157cf5a6eb7e6caf22130fa9f9d0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568803"
---
# <a name="pidtagcontentcorrelator-canonical-property"></a>PidTagContentCorrelator 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含邮件发件人可用于匹配与原始邮件报告的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTENT_CORRELATOR  <br/> |
|标识符：  <br/> |0x0007  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>注解

由原始邮件发件人定义二进制字符串的内容。 如果对传出邮件，此属性的设置应复制到任何响应消息中生成的报告。
  
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

