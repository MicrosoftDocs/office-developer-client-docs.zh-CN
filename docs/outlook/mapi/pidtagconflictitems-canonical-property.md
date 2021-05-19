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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338015"
---
# <a name="pidtagconflictitems-canonical-property"></a>PidTagConflictItems 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含自动冲突解决中涉及的项目的一个或多个条目 ID。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONFLICT_ITEMS  <br/> |
|标识符:  <br/> |0x1098  <br/> |
|属性类型  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |ICS  <br/> |
   
## <a name="remarks"></a>备注

支持自动冲突解决的标准 Microsoft Outlook项目类型包括以下标准项目类型：约会项目、联系人项目、日记项目、邮件项目、会议项目、便笺项目和任务项目。 属于派生自其中一个标准项目类型的邮件类的项目还支持自动冲突解决。 在 Microsoft Outlook 2003 和 Microsoft Office Outlook 2007 中，当 Outlook 同步项目并考虑结果副本可能不包含所有必需数据时，Outlook 将冲突副本存储在"同步问题"文件夹下的 **"冲突**"文件夹中。  
  
> [!NOTE]
> **在单击"** 开始"菜单上的"文件夹列表"之前，将隐藏"同步问题 **"****及其子文件夹**。 
  
如果项目 **是支持自动冲突解决的项目** 类型之一、在冲突解决中获胜或由于冲突解决而放置在"冲突"文件夹中，则该项目将公开 PR_CONFLICT_ITEMS 属性。 项目放置在其中的文件夹决定了项目 **PR_CONFLICT_ITEMS。** 如果项目位于"冲突"文件夹外的其他文件夹中，并且该项目公开 **了 PR_CONFLICT_ITEMS** 属性，则该项目必须获得冲突解决 **，PR_CONFLICT_ITEMS** 将包含冲突解决中丢失的项目的一个或多个条目 ID。 如果项目位于"冲突"文件夹中，并且该项目公开 **了 PR_CONFLICT_ITEMS** 属性，则此项目必须已失去冲突解决 **，PR_CONFLICT_ITEMS** 将包含在冲突解决中赢得的项目的条目 ID。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理在服务器和客户端之间同步邮件对象数据。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[关于 MAPI 添加件](about-mapi-additions.md)
  
[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

