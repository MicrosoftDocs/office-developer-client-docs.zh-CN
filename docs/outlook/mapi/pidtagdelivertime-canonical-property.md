---
title: PidTagDeliverTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeliverTime
api_type:
- HeaderDef
ms.assetid: da0ad17b-08ac-4c50-ac1d-13062b890dfd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3e9318e396bf195ad701b92372a3136dee7fd0d8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435276"
---
# <a name="pidtagdelivertime-canonical-property"></a>PidTagDeliverTime 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含传递原始邮件的日期和时间。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DELIVER_TIME  <br/> |
|标识符:  <br/> |0x0010  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>说明

此属性是传递报告上的每个收件人的属性, 该属性指示原始邮件传递到为其生成送达报告的邮件用户的时间。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

