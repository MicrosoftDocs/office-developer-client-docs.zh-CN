---
title: PidTagFolderType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFolderType
api_type:
- HeaderDef
ms.assetid: 2ab4681e-0013-4ba0-ba26-50517bbf3f5b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7cca884eae2111a94d87cc24a6d30542148ab845
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316315"
---
# <a name="pidtagfoldertype-canonical-property"></a>PidTagFolderType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个指示文件夹类型的常量。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FOLDER_TYPE  <br/> |
|标识符:  <br/> |0x3601  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>备注

此属性可以正好具有下列值之一：
  
FOLDER_GENERIC 
  
> 包含邮件和其他文件夹的通用文件夹。
    
FOLDER_ROOT 
  
> 文件夹层次结构表的根文件夹，即没有父文件夹的文件夹。
    
FOLDER_SEARCH 
  
> 包含搜索结果的文件夹，格式为指向符合搜索条件的邮件的链接。
    
不应将邮件存储的根目录与 IPM 中 iPM (子树) 根混淆。 存储区的根文件夹没有父级，通过调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 方法（具有空条目标识符）获取。 IPM 子树的根文件夹具有父级，通过使用 **OpenEntry** 调用的 **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性的值获取。 
  
MAPI 只允许每个邮件存储一个根文件夹。 此文件夹包含邮件和其他文件夹。 根文件夹的 **PR_PARENT_ENTRYID (** [PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性包含该文件夹自己的条目标识符。
  
搜索结果文件夹中的信息主要存储在其内容表中，其中包含与典型内容表相同的列，以及两个标识找到每封邮件的文件夹的额外列 **：PR_PARENT_DISPLAY** ([PidTagParentDisplay](pidtagparentdisplay-canonical-property.md))  (显示名称、必需的) 和此属性 (条目标识符，可选) 。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹操作。
    
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

