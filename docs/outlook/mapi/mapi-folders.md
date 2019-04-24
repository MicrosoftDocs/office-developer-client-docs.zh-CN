---
title: MAPI 文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8fac3c92-d2f5-479e-a368-ca82bddd8e30
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6c00dce9ec489ca2b886f3e51551ba57e9eeea33
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331561"
---
# <a name="mapi-folders"></a>MAPI 文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
文件夹是用作邮件的基本组织单位的 MAPI 对象。 层次结构排列, 文件夹可以包含邮件和其他文件夹。 文件夹使查找和处理邮件变得更加容易。
  
文件夹实现[IMAPIFolder](imapifolderimapicontainer.md)接口, 该接口间接继承自通过[IMAPIContainer](imapicontainerimapiprop.md)和[IMAPIProp](imapipropiunknown.md)接口的**IUnknown**接口。 客户端使用**IMAPIFolder**创建、复制和删除邮件和文件夹、检索和设置邮件状态以及设置或清除邮件的阅读标志。 尽管支持邮件存储提供程序以支持**IMAPIFolder**中的所有方法, 但某些方法会导致邮件存储提供程序可能想要避免的复杂程度。 MAPI 通过在[IMAPISupport](imapisupportiunknown.md)接口中实施一些更复杂的文件夹功能来保存邮件存储提供程序。 例如, 邮件存储提供程序可以调用支持对象中的 copy 方法并获得相同的结果, 而不是实现自己的 copy 方法。 
  
有三种类型的文件夹:
  
- 根文件夹。
    
- 通用文件夹。
    
- 搜索文件夹。
    
每个邮件存储至少具有一个根文件夹。 根文件夹显示在层次结构的顶部, 包含邮件和其他文件夹。 无法移动、复制、重命名或删除根文件夹。 每个邮件存储区只有一个根文件夹。
  
大多数其他文件夹是常规文件夹。 与根文件夹一样, 通用文件夹包含邮件和其他文件夹。 与根文件夹不同, 可以对它们进行移动、复制、重命名和删除。 可以在根文件夹或其他通用文件夹中创建通用文件夹。 当客户端在另一个文件夹中创建通用文件夹时, 新的文件夹称为子文件夹或子文件夹。 将在其中放置新文件夹的文件夹称为新文件夹的父文件夹。 具有相同父文件夹的通用文件夹称为 "同辈文件夹"。 同辈和非同辈文件夹都可能具有唯一的名称, 具体取决于邮件存储提供程序。 如果客户端尝试在同一父文件夹中创建两个名称相同的文件夹, 则需要同级文件夹具有唯一名称的邮件存储提供程序将返回错误值 MAPI_E_COLLISION。 
  
"搜索文件夹" 包含与一组预定义条件相匹配的邮件的链接。 由于搜索文件夹包含链接而不是实际邮件, 因此它们实际上是只读的。 用户不能包含其他文件夹, 也不能将邮件或文件夹移动或复制到其中。 他们不能在其中创建新邮件;它们本身不能被移动、复制或重命名。 从搜索文件夹中删除邮件时, 该邮件实际上从包含该邮件的文件夹中删除。
  
文件夹类型存储在**PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md)) 属性中。 每个文件夹均将此属性设置为 FOLDER_GENERIC、FOLDER_ROOT 或 FOLDER_SEARCH, 具体取决于其类型。
  
每个文件夹都有一个条目标识符和一个记录键。 条目标识符 ( **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))) 由客户端和服务提供商用于打开文件夹。 record 关键字**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 是一个二进制值, 用于将文件夹与其他文件夹进行比较。 
  
文件夹具有用于标识相关文件夹和邮件存储区的其他属性。 以下属性是必需的:
  
- **PR_PARENT_ENTRYID**([PidTagParentEntryId](pidtagparententryid-canonical-property.md))
    
- **PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))
    
- **PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))
    
某些文件夹支持**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性, 该属性描述了用户可以执行的操作的类型。 例如, **PR_ACCESS**的有效设置之一是 MAPI_ACCESS_DELETE, 这表示可以删除该文件夹。 另一个设置 MAPI_ACCESS_MODIFY, 指示文件夹应可修改。 
  
有关所需的文件夹属性的完整列表, 请参阅[IMAPIFolder](imapifolderimapicontainer.md)接口。 
  
## <a name="see-also"></a>另请参阅



[MAPI 应用程序开发](mapi-application-development.md)

