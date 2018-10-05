---
title: PidTagConflictItems 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagConflictItems
api_type:
- HeaderDef
ms.assetid: 0d147827-f0e2-dcc1-4427-c4a2f48ca801
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 83940d9239bc172d5fab76232f6644f0e89033b2
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386724"
---
# <a name="pidtagconflictitems-canonical-property"></a>PidTagConflictItems 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个或多个条目都已参与自动冲突解决中的项的 Id。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONFLICT_ITEMS  <br/> |
|标识符：  <br/> |0x1098  <br/> |
|属性类型  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |ICS  <br/> |
   
## <a name="remarks"></a>说明

标准支持自动冲突解决的 Microsoft Outlook 项目的类型包括以下类型的标准项： 约会项目、 联系人项目、 日记项目、 邮件项目、 会议项目、 粘滞便笺项目和任务项。 项目属于邮件类派生的其中一种标准的项目类型还支持自动冲突解决。 在 Microsoft Outlook 2003 和 Microsoft Office Outlook 2007 中，当 Outlook 同步项目，并考虑存在可能产生的副本可能不包含所有的基本数据，Outlook 存储**冲突**的冲突副本**同步问题**文件夹下的文件夹。 
  
> [!NOTE]
> **同步问题**及其子文件夹处于隐藏状态的直到您单击**转到**菜单上的**文件夹列表**。 
  
项目公开**PR_CONFLICT_ITEMS**属性，如果它是支持自动冲突解决项类型之一，赢得解决冲突，或者被由于冲突解决放在**冲突**文件夹。 在其中放置项目的文件夹确定**PR_CONFLICT_ITEMS**的内容。 如果项目位于之外**冲突**文件夹中，某些文件夹和项目公开**PR_CONFLICT_ITEMS**属性，项必须具有赢冲突解决，和**PR_CONFLICT_ITEMS**将包含的一个或多个条目 Id指定在冲突解决中丢失的那些项目。 如果项目位于**冲突**文件夹和项目公开**PR_CONFLICT_ITEMS**属性，此项必须丢失冲突解决中，并且**PR_CONFLICT_ITEMS**会包含赢得冲突中的项目的条目 ID解决方法。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 同步服务器和客户端之间的消息对象数据的句柄。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[关于 MAPI 添加件](about-mapi-additions.md)
  
[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

