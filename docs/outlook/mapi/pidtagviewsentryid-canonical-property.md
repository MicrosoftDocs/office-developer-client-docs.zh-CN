---
title: PidTagViewsEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagViewsEntryId
api_type:
- COM
ms.assetid: 8350a37c-6f42-4bef-82e0-35aa12b09fcf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7d261ac0e9aaf36f2333b04b45edfaf8e24fa30d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427309"
---
# <a name="pidtagviewsentryid-canonical-property"></a>PidTagViewsEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用户定义的 Views 文件夹的条目标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_VIEWS_ENTRYID  <br/> |
|标识符:  <br/> |0x35E5  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 邮件存储  <br/> |
   
## <a name="remarks"></a>备注

通用视图文件夹包含一组预定义的标准视图说明符，而视图文件夹包含由消息传递用户定义的说明符。 这些文件夹在 IPM 层次结构中的 (消息中) ，可以保留许多视图说明符，每个视图说明符都存储为一封邮件。 客户端应用程序可以选择合并这两组说明符，并使它们同时可用。
  
## <a name="related-resources"></a>相关资源

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

