---
title: PidTagScheduleInfoDelegateEntryIds 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoDelegateEntryIds
api_type:
- COM
ms.assetid: c178a4e4-6f4c-409c-9db3-f6338bd4f40f
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 8ea60fb989cd85b23e6dd9302bc03a9b5befd20f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778322"
---
# <a name="pidtagscheduleinfodelegateentryids-canonical-property"></a>PidTagScheduleInfoDelegateEntryIds 规范属性

  
  
**适用于**： Outlook 
  
包含的代理人的**Entryid** 。 
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_SCHDINFO_DELEGATE_ENTRYIDS  <br/> |
|标识符:  <br/> |0x6845  <br/> |
|数据类型：  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>备注

每个条目都必须包含每个代理人的通讯簿条目的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的值。 此属性必须设置委托信息对象中。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。
    
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

