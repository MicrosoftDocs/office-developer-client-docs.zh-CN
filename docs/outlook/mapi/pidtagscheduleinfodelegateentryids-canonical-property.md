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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b2adde7c5ecc75fda25b94d005fabfcd705d5d07
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321292"
---
# <a name="pidtagscheduleinfodelegateentryids-canonical-property"></a>PidTagScheduleInfoDelegateEntryIds 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 **委托的 EntryID。** 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_DELEGATE_ENTRYIDS  <br/> |
|标识符:  <br/> |0x6845  <br/> |
|数据类型：  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>备注

每个条目必须包含每个代理通讯簿PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的值。  此属性必须在委托信息对象中设置。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

