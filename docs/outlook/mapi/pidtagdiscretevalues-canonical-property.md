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
ms.openlocfilehash: 6d6974302e3413db3590abbbd3e6567976c6ac72
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404839"
---
# <a name="pidtagdiscretevalues-canonical-property"></a>PidTagDiscreteValues 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果未送达报告仅适用于通讯组列表的离散成员，而不是整个列表，则包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DISCRETE_VALUES  <br/> |
|标识符:  <br/> |0x0E0E  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 不可传输  <br/> |
   
## <a name="remarks"></a>备注

当邮件无法传递到通讯组列表的一个或多个成员时，将在未送达报告中使用此属性。 它的目的是将重新传输尝试限制为仅这些单个成员，而不是整个通讯组列表。 
  
未送达报告的收件人表包含邮件无法传递到的所有收件人的条目，以及这些收件人所属的通讯组列表（如果有）的条目。 传输提供程序应针对每个通讯组列表条目将此属性设置为 TRUE，并且应复制 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 、PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) ， 和 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 从通讯组列表到 **PR_ORIGINAL_DISPLAY_NAME** ([PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md)) 、PR_ORIGINAL_ENTRYID ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 以及该通讯组列表每个成员 PR_ORIGINAL_SEARCH_KEY **(** [PidTagOriginalSearchKey](pidtagoriginalsearchkey-canonical-property.md)) 属性。  
  
 **PR_DISCRETE_VALUES** 通讯组列表外的任何未送达报告收件人条目设置邮件。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

