---
title: PidTagDiscardReason 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDiscardReason
api_type:
- HeaderDef
ms.assetid: 5004dc1f-6bd3-4764-b83c-d04d83161dba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8835b7234a209d5cb80a19593632380f6d83826
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593156"
---
# <a name="pidtagdiscardreason-canonical-property"></a>PidTagDiscardReason 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含邮件传输代理 (MTA) 为什么已丢弃的消息的原因。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DISCARD_REASON  <br/> |
|标识符：  <br/> |0x0011  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>注解

此属性中包含的原因是原件报表中使用的邮件。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagNonDeliveryReportReasonCode 规范属性](pidtagnondeliveryreportreasoncode-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

