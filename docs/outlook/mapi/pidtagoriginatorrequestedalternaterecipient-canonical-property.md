---
title: PidTagOriginatorRequestedAlternateRecipient 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginatorRequestedAlternateRecipient
api_type:
- COM
ms.assetid: c85b7862-18bc-4e17-94db-9097e0ac4a02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 45cd0e8a95f908d7ef56d03b3ecab5d5df5bcae1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437859"
---
# <a name="pidtagoriginatorrequestedalternaterecipient-canonical-property"></a>PidTagOriginatorRequestedAlternateRecipient 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含发件人指定的备用收件人的条目标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINATOR_REQUESTED_ALTERNATE_RECIPIENT  <br/> |
|标识符:  <br/> |0x0C09  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MIME  <br/> |
   
## <a name="remarks"></a>备注

此属性用于自动前向邮件。 如果不允许自动前向或尚未指定备用收件人，应生成未送达报告。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

