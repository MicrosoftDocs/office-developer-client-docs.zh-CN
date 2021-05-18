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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421842"
---
# <a name="mapi-folders"></a>MAPI 文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
文件夹是 MAPI 对象，充当邮件的基本组织单位。 文件夹可以按层次结构排列，可以包含邮件和其他文件夹。 通过文件夹，可以更轻松地查找和处理邮件。
  
文件夹实现 [IMAPIFolder](imapifolderimapicontainer.md)接口，该接口通过 [IMAPIContainer](imapicontainerimapiprop.md)和 [IMAPIProp](imapipropiunknown.md)接口间接继承自 **IUnknown** 接口。 客户端使用 **IMAPIFolder** 创建、复制和删除邮件和文件夹，检索和设置邮件状态，以及设置或清除邮件的阅读标志。 尽管邮件存储提供程序需要支持 **IMAPIFolder** 中所有方法，但某些方法会引入邮件存储提供程序可能想要避免的复杂性级别。 MAPI 通过实现 IMAPISupport 接口中的某些更复杂的文件夹功能来保存邮件 [存储提供程序的一些](imapisupportiunknown.md) 工作。 例如，邮件存储提供程序可以调用支持对象中的复制方法并获取相同的结果，而不是实现自己的复制方法。 
  
有三种类型的文件夹：
  
- 根文件夹。
    
- 常规文件夹。
    
- 搜索文件夹。
    
每个邮件存储都至少有一个根文件夹。 根文件夹显示在层次结构的顶部，并包含邮件和其他文件夹。 无法移动、复制、重命名或删除根文件夹。 每个邮件存储只有一个根文件夹。
  
大多数其他文件夹都是常规文件夹。 与根文件夹一样，常规文件夹包含邮件和其他文件夹。 与根文件夹不同，可以移动、复制、重命名和删除它们。 可以在根文件夹或其他常规文件夹中创建泛型文件夹。 当客户端在另一个文件夹中创建泛型文件夹时，新文件夹称为子文件夹或子文件夹。 放置新文件夹的文件夹称为新文件夹的父文件夹。 具有相同的父文件夹的通用文件夹称为同级文件夹。 同级和非同级文件夹的名称可能唯一，也可能没有，具体取决于邮件存储提供程序。 当客户端尝试在同一父文件夹中创建两个同名的文件夹时，要求同级文件夹具有唯一名称的邮件存储提供程序将返回错误值 MAPI_E_COLLISION。 
  
搜索文件夹包含指向匹配一组预定义条件的邮件的链接。 由于搜索文件夹包含链接而不是实际邮件，因此它们实际上为只读。 它们不能包含其他文件夹，也不能将邮件或文件夹移动或复制到其中。 他们无法创建新邮件;它们本身无法移动、复制或重命名。 从搜索文件夹中删除邮件时，实际上会从包含该邮件的文件夹中删除该邮件。
  
文件夹类型存储在[PidTagFolderType PR_FOLDER_TYPE (PidTagFolderType) ](pidtagfoldertype-canonical-property.md)中。  每个文件夹的此属性都设置为 FOLDER_GENERIC、FOLDER_ROOT 或 FOLDER_SEARCH，具体取决于其类型。
  
每个文件夹都有一个条目标识符和一个记录密钥。 客户端和 **服务提供商PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) 条目标识符来打开文件夹。 记录键 **（PR_RECORD_KEY (** [PidTagRecordKey](pidtagrecordkey-canonical-property.md)) ）是一个二进制值，用于将文件夹与其他文件夹进行比较。 
  
文件夹具有用于标识相关文件夹和邮件存储的其他属性。 以下属性是必需的：
  
- **PR_PARENT_ENTRYID (** [PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 
    
- **PR_STORE_ENTRYID (** [PidTagStoreEntryId)](pidtagstoreentryid-canonical-property.md)
    
- **PR_STORE_RECORD_KEY (** [PidTagStoreRecordKey)](pidtagstorerecordkey-canonical-property.md)
    
某些文件夹支持 **PR_ACCESS (** [PidTagAccess](pidtagaccess-canonical-property.md)) 属性，该属性描述用户可以执行的操作的类型。 例如，其中一个PR_ACCESS设置MAPI_ACCESS_DELETE，指示可以删除文件夹。 另一MAPI_ACCESS_MODIFY设置（即 ，指示文件夹应可修改）。 
  
有关所需文件夹属性的完整列表，请参阅 [IMAPIFolder](imapifolderimapicontainer.md) 接口。 
  
## <a name="see-also"></a>另请参阅



[MAPI 应用程序开发](mapi-application-development.md)

