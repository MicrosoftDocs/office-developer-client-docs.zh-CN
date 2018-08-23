---
title: PidTagDiscreteValues 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDiscreteValues
api_type:
- HeaderDef
ms.assetid: 958f3cf7-953a-43f4-9102-ad35edf5e813
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f1aa54c3364185d322137ef41f6aface31c5c556
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587416"
---
# <a name="pidtagdiscretevalues-canonical-property"></a>PidTagDiscreteValues 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含 TRUE，则原件报表适用的通讯组列表，而不是整个列表仅为离散成员。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DISCRETE_VALUES  <br/> |
|标识符：  <br/> |0x0E0E  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 非可传送  <br/> |
   
## <a name="remarks"></a>注解

邮件无法传递给一个或多个成员的通讯组列表时，将原件报告中使用此属性。 其目的是限制重新传输尝试只有的单个成员和不是作为一个整体的通讯组列表。 
  
原件报告收件人表包含条目的所有收件人添加到其消息无法送达，以及通讯组列表中，如果有，它们属于。 传输提供程序应将此属性设置为 TRUE 为每个通讯组列表项，它应**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))、 和复制**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))， **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 从**PR_ORIGINAL_DISPLAY_NAME** ([PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md))、 **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 和**PR_ORIGINAL_SEARCH_KEY** ([通讯组列表PidTagOriginalSearchKey](pidtagoriginalsearchkey-canonical-property.md)) 的每个成员的通讯组列表的属性。 
  
 不应为通讯组列表之外任何原件报告收件人条目设置**PR_DISCRETE_VALUES** 。 
  
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

