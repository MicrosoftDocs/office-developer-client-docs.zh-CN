---
title: PidTagScheduleInfoFreeBusyMerged 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusyMerged
api_type:
- COM
ms.assetid: 3ebfccb6-967a-4f8e-9d94-94c50ba65438
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0e1fbab53589a4ebf8681d5fe738ad625d31c18f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778337"
---
# <a name="pidtagscheduleinfofreebusymerged-canonical-property"></a>PidTagScheduleInfoFreeBusyMerged 规范属性

  
  
**适用于**： Outlook 
  
包含为其设置的忙/闲状态的时间为繁忙或 OOF。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_FREEBUSY_MERGED  <br/> |
|标识符：  <br/> |0x6850  <br/> |
|数据类型：  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>说明

此属性中不包含暂定的忙/闲信息的类型的事件。 格式、 computation 和此属性的限制是那些**PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) 相同，但参考标记 OOF 或关联的日历闲的约会。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)
  
> 发布的用户或资源的可用性。
    
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

