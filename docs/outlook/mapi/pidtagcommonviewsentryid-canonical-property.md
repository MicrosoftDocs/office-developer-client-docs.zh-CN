---
title: PidTagCommonViewsEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagCommonViewsEntryId
api_type:
- HeaderDef
ms.assetid: cd9e6a46-2112-4663-891e-5e57b22c0950
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7449e59227b147d34c2329175d0251dbb9c427b6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581340"
---
# <a name="pidtagcommonviewsentryid-canonical-property"></a>PidTagCommonViewsEntryId 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含预定义的公共视图文件夹的项标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_COMMON_VIEWS_ENTRYID  <br/> |
|标识符：  <br/> |0x35E6  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Outlook 应用程序  <br/> |
   
## <a name="remarks"></a>注解

公共视图文件夹包含一组预定义的标准视图说明符，而视图文件夹包含由消息的用户定义的说明符。 这些文件夹，不可见人际邮件 (IPM) 层次结构中，可以包含多个视图说明符，每个存储为邮件。 客户端应用程序可以选择合并两个说明符集并使其同时可用。 
  
视图的详细信息，请参阅[查看文件夹](mapi-view-folders.md)。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagDefaultViewEntryId 规范属性](pidtagdefaultviewentryid-canonical-property.md)
  
[PidTagViewsEntryId 规范属性](pidtagviewsentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

