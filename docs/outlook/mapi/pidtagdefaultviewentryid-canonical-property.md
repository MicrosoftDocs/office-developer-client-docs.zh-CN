---
title: PidTagDefaultViewEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefaultViewEntryId
api_type:
- HeaderDef
ms.assetid: 1b4e82ed-c207-4828-8a5b-0ef312962355
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6d284782de86b603e6bbe190931a85cd9196c88b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393514"
---
# <a name="pidtagdefaultviewentryid-canonical-property"></a>PidTagDefaultViewEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含某个文件夹的默认视图的项的标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEFAULT_VIEW_ENTRYID  <br/> |
|标识符：  <br/> |0x3616  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>说明

此属性是应设置为初始视图的文件夹视图的项标识符。 如果"Normal"视图是要用作初始视图，则不需要设置属性。
  
客户端应用程序可以获取此属性在打开时文件夹和实现显著提高性能。 此属性可以作为快捷方式，用于获取默认视图，而不是打开的关联的内容表并提交限制。
  
在复制文件夹时， [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)方法的服务提供程序实现可以复制此属性。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹的操作。
    
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

