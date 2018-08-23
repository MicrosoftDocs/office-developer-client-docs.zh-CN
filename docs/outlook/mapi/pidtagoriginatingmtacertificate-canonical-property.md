---
title: PidTagOriginatingMtaCertificate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginatingMtaCertificate
api_type:
- COM
ms.assetid: f6b7ff0c-19a0-4cad-8868-c05397fcebf4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e2f4b1fda57eb74e0573834c6e8fb443acf7ab12
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563903"
---
# <a name="pidtagoriginatingmtacertificate-canonical-property"></a>PidTagOriginatingMtaCertificate 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
发出邮件的邮件传输代理 (MTA) 中包含的标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINATING_MTA_CERTIFICATE  <br/> |
|标识符：  <br/> |0x0E25  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Server  <br/> |
   
## <a name="remarks"></a>注解

此属性，如果设置，可在发送邮件已发送邮件文件夹中。
  
此属性对应于 X.400 报告每封邮件属性。
  
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

