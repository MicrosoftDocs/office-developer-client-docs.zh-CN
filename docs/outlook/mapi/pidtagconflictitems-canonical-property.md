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
  
包含自动冲突解决中涉及的项目的一个或多个条目 id。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONFLICT_ITEMS  <br/> |
|标识符:  <br/> |0x1098  <br/> |
|属性类型  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |用作  <br/> |
   
## <a name="remarks"></a>注解

支持自动冲突解决的标准 Microsoft Outlook 项目的类型包括以下标准项类型: 约会项、联系人项、日记项、邮件项、会议项、便笺项和任务项。 属于从这些标准项目类型之一派生的邮件类的项目也支持自动冲突解决。 在 microsoft Outlook 2003 和 microsoft Office outlook 2007 中, 当 Outlook 同步项目并认为生成的副本可能不包含所有重要数据时, outlook 会将冲突副本存储在**冲突**中文件夹中的 "**同步问题**" 文件夹下。 
  
> [!NOTE]
> 除非您单击 "**转到**" 菜单上的 "**文件夹列表**", 否则**同步问题**及其子文件夹将被隐藏。 
  
如果项目类型是支持自动冲突解决的项目类型之一, 已赢得冲突解决, 或者由于冲突解决而被置于**冲突**文件夹中, 则该项目会公开**PR_CONFLICT_ITEMS**属性。 放置项的文件夹将决定**PR_CONFLICT_ITEMS**的内容。 如果项位于 "**冲突**" 文件夹之外的某个文件夹中, 并且该项公开了**PR_CONFLICT_ITEMS**属性, 则该项目必须赢得冲突解决, 并且**PR_CONFLICT_ITEMS**将包含一个或多个条目 id冲突解决中丢失的那些项目。 如果项位于 "**冲突**" 文件夹中, 并且该项公开了**PR_CONFLICT_ITEMS**属性, 则此项必须已丢失冲突解决, 并且**PR_CONFLICT_ITEMS**将包含冲突中赢得的项的条目 ID。办法. 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理服务器和客户端之间的同步邮件对象数据。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[关于 MAPI 添加件](about-mapi-additions.md)
  
[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

