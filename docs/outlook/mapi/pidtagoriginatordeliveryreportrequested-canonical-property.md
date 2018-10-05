---
title: PidTagOriginatorDeliveryReportRequested 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginatorDeliveryReportRequested
api_type:
- COM
ms.assetid: 4461b35d-e2b9-41ff-b079-31bfef02e2bb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a92ee13e571032c050f69677d9daba8dad7aea3c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395495"
---
# <a name="pidtagoriginatordeliveryreportrequested-canonical-property"></a>PidTagOriginatorDeliveryReportRequested 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果邮件发件人请求特定收件人从邮件系统的送达报告之前消息置于消息存储库中，包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |邮件已被阅读  <br/> |
|标识符：  <br/> |0x0023  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MIME  <br/> |
   
## <a name="remarks"></a>说明

此属性用于直接在邮件系统中处理已发送的邮件。 在这种情况下，邮件还必须提供**PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) 属性设置为 FALSE。
  
上一条消息设置的**邮件已被阅读**属性是一种方法传递状态报告请求的所有收件人。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

