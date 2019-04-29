---
title: PidTagIpmSubtreeEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmSubtreeEntryId
api_type:
- HeaderDef
ms.assetid: 5763fc78-5192-4162-be27-4aadc7ed65bc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 815685696dfc93bb6241f608ca0157e87e758e7b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412728"
---
# <a name="pidtagipmsubtreeentryid-canonical-property"></a>PidTagIpmSubtreeEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件存储的文件夹树中人际邮件 (IPM) 文件夹子树的根的条目标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IPM_SUBTREE_ENTRYID  <br/> |
|标识符:  <br/> |0x35E0  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Folder  <br/> |
   
## <a name="remarks"></a>说明

此属性表示 IPM 层次结构的根。 IPM 客户端不应显示此属性所代表的文件夹的子文件夹的任何文件夹。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

