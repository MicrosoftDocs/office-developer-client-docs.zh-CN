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
ms.openlocfilehash: 80c76242df409dbea1b60e423629b5b219e1d57d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777890"
---
# <a name="pidtagnonreceiptnotificationrequested-canonical-property"></a>PidTagNonReceiptNotificationRequested 规范属性

  
  
**适用于**： Outlook 
  
如果邮件发件人的指定收件人的非回执通知，包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_NON_RECEIPT_NOTIFICATION_REQUESTED  <br/> |
|标识符：  <br/> |0x0C06  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>说明

此属性包含 FALSE 并且**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性包含 TRUE，如果服务提供商可以重写**PR_NON_RECEIPT_NOTIFICATION_REQUESTED**属性，并生成未送达报告。 
  
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

