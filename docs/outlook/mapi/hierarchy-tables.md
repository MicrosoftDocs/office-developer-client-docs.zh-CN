---
title: 层次结构表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b8aa6b36-d6e5-4e1f-8ac5-5d6a78a70bf8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 23314418836893b40cbddf3b90bd95ec061a00c4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775090"
---
# <a name="hierarchy-tables"></a>层次结构表

  
  
**适用于**： Outlook 
  
层次结构表包含有关邮件存储区中的文件夹或通讯簿容器中的容器的信息。 层次结构表的每一行包含一组与一个文件夹或通讯簿容器信息的列。 层次结构表主要由客户端使用和消息存储提供程序以显示的文件夹和子文件夹树由实现并由通讯簿提供程序以在通讯簿中显示的容器树实现。 容器不能容纳子容器，由缺少其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中，AB_SUBCONTAINERS 标志不实现层次结构表。
  
可以通过调用访问层次结构表：
  
- [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)。
    
    - 或者-
    
- [IMAPIProp::OpenProperty](imapiprop-openproperty.md)作为属性标记和 IID_IMAPITable 接口标识传递**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))。
    
容器和文件夹必须支持这两种方法，用于检索表属性。 无法接受的服务提供商支持只有一个办法可以访问这些表，因为客户端期望有选择它。 
  
> [!IMPORTANT]
> 存储提供程序不能保证服从设置指定的层次结构表的排序次序。 
  
调用**IMAPIProp::OpenProperty**涉及通过打开及其对应的属性， **PR_CONTAINER_HIERARCHY**访问层次结构表。 尽管**PR_CONTAINER_HIERARCHY**无法检索到的文件夹或容器的[IMAPIProp::GetProps](imapiprop-getprops.md)方法，它包含由[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法返回的属性标记数组。 
  
 **PR_CONTAINER_HIERARCHY**还可以用于中包括或排除层次结构表复制操作。 如果客户端**PR_CONTAINER_HIERARCHY** *lpExcludeProps*参数中指定的[IMAPIProp::CopyTo](imapiprop-copyto.md)复制操作中的新文件夹或容器不支持的原始文件夹或容器的层次结构表。 
  
以下属性组成层次结构表中设置所需的列：
  
|||
|:-----|:-----|
|**PR_COMMENT**([PidTagComment](pidtagcomment-canonical-property.md))  <br/> |**PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md))  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |**PR_STATUS**([PidTagStatus](pidtagstatus-canonical-property.md))  <br/> |
   
 **PR_DISPLAY_NAME**包含容器或应出现在显示的层次结构的文件夹的名称。 
  
 **PR_ENTRYID**是与此容器或文件夹关联的项标识符。 它将是长期的项标识符。 客户端和 MAPI 可以传递给**OpenEntry**打开的容器或文件夹并通过调用[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)查看其内容的此条目标识符。 
  
 **PR_DEPTH**是零正在顶级指示此容器或文件夹的缩进级别的数值。 更深入的容器或文件夹层次结构中位于，其**PR_DEPTH**属性的值越高。 客户端使用**PR_DEPTH**属性，以便用户可以清楚地查看父级和子级关系适当地显示层次结构表。 容器或文件夹深度始终是相对于容器或实现层次结构表的文件夹。 
  
 **PR_OBJECT_TYPE**始终设置为 MAPI_ABCONT 通讯簿层次结构表和 MAPI_FOLDER 的文件夹层次结构表。 
  
 **PR_DISPLAY_TYPE**是一个数值，它与容器或文件夹的层次结构表的显示方式。 它主要用于显示出于，直观地区分类型的容器或文件夹。 许多消息存储和通讯簿提供程序使用不同的显示类型的图标。 由要提供这些图标; 的提供程序MAPI 不会提供默认值。 
  
MAPI 定义**PR_DISPLAY_TYPE**的有效的文件夹和其他人的地址簿容器层次结构表与使用多个值。 通常，某个文件夹的**PR_DISPLAY_TYPE**设置为 DT_FOLDER 以指示默认文件夹图标，DT_FOLDER_LINK 以指示图标表示指向另一个文件夹或 DT_FOLDER_SPECIAL 以指示特定于应用程序的图标。 DT_FOLDER_LINK 用于搜索结果文件夹。 
  
除了这些所需的列，通讯簿层次结构表必须包括**PR_CONTAINER_FLAGS**属性。 **PR_CONTAINER_FLAGS**指示有关容器层次结构中的各种属性，用于区分从另一个容器。 
  
通讯簿层次结构表可选属性是**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 属性。
  
消息存储层次结构表在其所需的列集包含以下属性：
  
- **PR_FOLDER_TYPE**([PidTagFolderType](pidtagfoldertype-canonical-property.md))
    
- **PR_SUBFOLDERS**([PidTagSubfolders](pidtagsubfolders-canonical-property.md))
    
- **PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))
    
- **PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))
    
通讯簿提供程序必须在其层次结构表实现中支持下列**IMAPITable**方法，因为它们所需的 MAPI 集成的通讯簿： 
  
|||
|:-----|:-----|
|[IMAPITable::QueryColumns](imapitable-querycolumns.md) <br/> |[IMAPITable::QueryPosition](imapitable-queryposition.md) <br/> |
|[IMAPITable::SeekRow](imapitable-seekrow.md) <br/> |[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) <br/> |
|[IMAPITable::FindRow](imapitable-findrow.md) <br/> |[IMAPITable::Restrict](imapitable-restrict.md) <br/> |
|[IMAPITable::CreateBookmark](imapitable-createbookmark.md) <br/> |[IMAPITable::FreeBookmark](imapitable-freebookmark.md) <br/> |
|[IMAPITable::QueryRows](imapitable-queryrows.md) <br/> | <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

