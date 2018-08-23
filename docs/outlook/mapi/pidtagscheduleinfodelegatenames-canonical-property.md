---
title: PidTagScheduleInfoDelegateNames 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoDelegateNames
api_type:
- COM
ms.assetid: 592d9c78-4487-4c68-8ae7-4cd3d6265685
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 06462f992ec640992b95b89a618e7d82290eeeef
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574501"
---
# <a name="pidtagscheduleinfodelegatenames-canonical-property"></a>PidTagScheduleInfoDelegateNames 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含的代理人的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_DELEGATE_NAMES，PR_SCHDINFO_DELEGATE_NAMES_A，PR_SCHDINFO_DELEGATE_NAMES_W  <br/> |
|标识符：  <br/> |0x6844  <br/> |
|数据类型：  <br/> |PT_MV_STRING8 PT_MV_UNICODE  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>注解

这些属性中的每个条目都必须包含的每个代理人的通讯簿**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值。
  
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
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

