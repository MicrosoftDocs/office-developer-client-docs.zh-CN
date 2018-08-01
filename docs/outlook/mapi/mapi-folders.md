---
title: MAPI 文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8fac3c92-d2f5-479e-a368-ca82bddd8e30
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 88ddfd9e6bb27abfeee9750c71e98d4fad9d1a14
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776233"
---
# <a name="mapi-folders"></a>MAPI 文件夹

  
  
**适用于**： Outlook 
  
文件夹是充当组织的邮件的基本单位的 MAPI 对象。 按层次结构排列，文件夹可以包含邮件和其他文件夹。 文件夹更加轻松地查找和处理邮件。
  
文件夹实现[IMAPIFolder](imapifolderimapicontainer.md)接口，间接继承的**IUnknown**接口，通过[IMAPIContainer](imapicontainerimapiprop.md)和[IMAPIProp](imapipropiunknown.md)接口。 客户端使用**IMAPIFolder**若要创建、 复制和删除邮件和文件夹，用于检索和设置邮件状态和设置或清除邮件阅读的标志。 尽管在**IMAPIFolder**支持所有方法所需消息存储提供程序，但某些方法引入消息存储提供程序可能希望避免的复杂级别。 MAPI 将消息存储提供程序一些工作保存由[IMAPISupport](imapisupportiunknown.md)接口中实现的某些更复杂的文件夹功能。 而不是实现自己的复制方法，例如，消息存储提供程序可以呼叫中的支持对象的复制方法并获取相同的结果。 
  
有三种类型的文件夹：
  
- 根文件夹。
    
- 泛型文件夹。
    
- 搜索文件夹。
    
每个消息存储库具有至少一个根文件夹。 根文件夹层次结构的顶端显示和包含邮件和其他文件夹。 不能移动、 复制、 重命名或删除根文件夹。 没有为每个消息存储库的只有一个根文件夹。
  
大多数其他文件夹是通用的文件夹。 根文件夹，如泛型文件夹包含邮件和其他文件夹。 与不同的根文件夹，他们可以移动、 复制、 重命名，并删除。 可以在根文件夹或其他泛型文件夹中创建通用的文件夹。 当客户端在另一个文件夹中创建通用文件夹时，新文件夹称为子文件夹或子文件夹。 在其中放置新文件夹的文件夹称为新文件夹的父文件夹。 具有相同的父文件夹的通用文件夹称为同级文件夹。 同级和非同级文件夹可能或可能不具有唯一的名称，具体取决于消息存储提供程序。 邮件需要具有唯一的名称时客户端尝试使用同一个父中具有相同名称创建两个文件夹返回错误值 MAPI_E_COLLISION 同级文件夹的存储提供程序。 
  
搜索文件夹包含指向与一组预定义的条件匹配的邮件。 搜索文件夹包含的链接，而不是实际的邮件，因为它们是实际上是只读的。 不能包含其他文件夹或具有邮件或文件夹移动或复制到它们。 不能具有中; 创建的新消息和它们本身不能移动、 复制或重命名。 搜索文件夹中删除一条消息后，它是实际删除从包含邮件的文件夹。
  
文件夹类型存储在**PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md)) 属性。 每个文件夹包含此属性设置为 FOLDER_GENERIC、 FOLDER_ROOT 或 FOLDER_SEARCH，具体取决于其类型。
  
每个文件夹都有一个条目标识符和一个记录密钥。 客户端和服务提供商使用的项标识符， **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))，以打开文件夹。 记录项， **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 是用于比较与其他文件夹的文件夹的二进制值。 
  
文件夹具有其他属性标识相关的文件夹和消息存储库。 需要以下属性：
  
- **PR_PARENT_ENTRYID**([PidTagParentEntryId](pidtagparententryid-canonical-property.md))
    
- **PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))
    
- **PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))
    
有些文件夹支持**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性，其中介绍了用户可以执行的操作的类型。 例如， **PR_ACCESS**的有效设置之一是 MAPI_ACCESS_DELETE，指示可以删除该文件夹。 其他设置，MAPI_ACCESS_MODIFY，指示应可修改的文件夹。 
  
需要的文件夹属性的完整列表，请参阅[IMAPIFolder](imapifolderimapicontainer.md)接口。 
  
## <a name="see-also"></a>另请参阅



[MAPI 应用程序开发](mapi-application-development.md)

