---
title: PidTagReceiptTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceiptTime
api_type:
- COM
ms.assetid: 9c6cd2f4-e769-4786-b9cc-c02641fecc4f
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0d0b8f3a394d2ec2239e8ab186d4021b60b00ea4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778121"
---
# <a name="pidtagreceipttime-canonical-property"></a>PidTagReceiptTime 规范属性

  
  
**适用于**： Outlook 
  
包含的日期和时间生成的送达报告。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_RECEIPT_TIME  <br/> |
|标识符:  <br/> |0x002A  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

此属性必须设置消息存储提供程序接收邮件列表并生成报表。 
  
## <a name="related-resources"></a>相关资源

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

