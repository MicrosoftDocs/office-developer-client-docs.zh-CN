---
title: PidTagOwnStoreEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOwnStoreEntryId
api_type:
- COM
ms.assetid: 6a82ee90-10a1-49e0-8f3a-a2cd9f490f99
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 16a23c4e711bf9f7b670dff8b3e8f65371aa6bda
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427372"
---
# <a name="pidtagownstoreentryid-canonical-property"></a>PidTagOwnStoreEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含传输的紧密耦合邮件存储的条目标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_OWN_STORE_ENTRYID  <br/> |
|标识符:  <br/> |0x3E06  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |邮件存储属性  <br/> |
   
## <a name="remarks"></a>备注

此属性指定紧密耦合存储（如果存在）的条目标识符。 例如，传输提供程序可以指定专用文件夹存储条目标识符，以便 MAPI 后台处理程序可以将传输提供程序连接到存储。
  
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

