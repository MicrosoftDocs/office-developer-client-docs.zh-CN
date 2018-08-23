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
ms.openlocfilehash: ade74b13811445c39c73f778b6de49b67b59093b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587556"
---
# <a name="pidtagipmsubtreeentryid-canonical-property"></a>PidTagIpmSubtreeEntryId 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含消息存储库文件夹树中的人际邮件 (IPM) 文件夹子树的根的项标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IPM_SUBTREE_ENTRYID  <br/> |
|标识符：  <br/> |0x35E0  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Folder  <br/> |
   
## <a name="remarks"></a>注解

此属性表示 IPM 层次结构的根。 IPM 客户端不应显示不支持此属性表示的文件夹的子文件夹的任何文件夹。
  
## <a name="related-resources"></a>相关资源

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

