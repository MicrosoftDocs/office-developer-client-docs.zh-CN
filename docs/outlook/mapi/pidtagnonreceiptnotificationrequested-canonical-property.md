---
title: PidTagNonReceiptNotificationRequested 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNonReceiptNotificationRequested
api_type:
- HeaderDef
ms.assetid: 747f7ba8-42d3-4be3-9908-269e9a347c7f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0c6b56a786ea794587e140c9555cc88cd862b489
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329307"
---
# <a name="pidtagnonreceiptnotificationrequested-canonical-property"></a>PidTagNonReceiptNotificationRequested 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果邮件发件人想要通知指定收件人的非接收通知, 则该参数为 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_NON_RECEIPT_NOTIFICATION_REQUESTED  <br/> |
|标识符:  <br/> |0x0C06  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>注解

如果此属性包含 FALSE 且**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性包含 TRUE, 则服务提供程序可以重写**PR_NON_RECEIPT_NOTIFICATION_REQUESTED**属性并生成未送达报告。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

