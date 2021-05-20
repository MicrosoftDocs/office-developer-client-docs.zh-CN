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
ms.openlocfilehash: 2a1461f0c7196cd425d9736f5837b742bedd4fb5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428366"
---
# <a name="hierarchy-tables"></a>层次结构表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
层次结构表包含有关邮件存储中的文件夹或通讯簿容器中的容器的信息。 层次结构表的每一行都包含一组列，其中包含有关一个文件夹或通讯簿容器的信息。 层次结构表主要由客户端使用，由邮件存储提供程序实现以显示文件夹和子文件夹的树，由通讯簿提供程序实现以显示通讯簿中的容器树。 无法容纳子容器的容器（如 PR_CONTAINER_FLAGS ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中缺少 **AB_SUBCONTAINERS** 标志所示）不实现层次结构表。
  
可以通过调用访问层次结构表：
  
- [IMAPIContainer：：GetHierarchyTable](imapicontainer-gethierarchytable.md)。
    
    - 或 -
    
- [IMAPIProp：：OpenProperty PR_CONTAINER_HIERARCHY (](imapiprop-openproperty.md) [PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 作为属性标记，IID_IMAPITable作为接口标识符。 
    
容器和文件夹必须支持检索表属性这两种技术。 服务提供商仅支持一种访问这些表的方法是无法接受的，因为客户端希望有选择。 
  
> [!IMPORTANT]
> 存储提供程序不保证遵守为层次结构表指定的排序顺序。 
  
对 **IMAPIProp：：OpenProperty** 的调用涉及通过打开其对应的属性 （即 PR_CONTAINER_HIERARCHY） **来访问层次结构表**。 尽管 **PR_CONTAINER_HIERARCHY** 文件夹或容器的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法检索数据，但它包含在 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法返回的属性标记数组中。 
  
 **PR_CONTAINER_HIERARCHY** 还可用于在复制操作中包括或排除层次结构表。 如果客户端在复制操作PR_CONTAINER_HIERARCHY [IMAPIProp：：CopyTo](imapiprop-copyto.md)的 *lpExcludeProps* 参数中指定值，则新文件夹或容器将不支持原始文件夹或容器的层次结构表。 
  
以下属性将包含层次结构表中所需的列集：
  
|||
|:-----|:-----|
|**PR_COMMENT (** [PidTagComment](pidtagcomment-canonical-property.md))   <br/> |**PR_DEPTH (** [PidTagDepth](pidtagdepth-canonical-property.md))   <br/> |
|**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |**PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md))   <br/> |
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md))   <br/> |
|**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |**PR_STATUS (** [PidTagStatus](pidtagstatus-canonical-property.md))   <br/> |
   
 **PR_DISPLAY_NAME** 包含在层次结构的显示中应显示的容器或文件夹的名称。 
  
 **PR_ENTRYID** 与此容器或文件夹关联的条目标识符。 它应该是长期条目标识符。 客户端和 MAPI 可以将此条目标识符传递到 **OpenEntry** 以打开容器或文件夹，并通过调用 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md)查看其内容。 
  
 **PR_DEPTH** 是一个数值，指示此容器或文件夹的缩进级别，其中零是顶层。 容器或文件夹所在的层次结构越深，其 PR_DEPTH **属性的值越高** 。 客户端使用 **PR_DEPTH** 属性适当地显示层次结构表，以便用户可以清楚地查看父和子关系。 容器或文件夹深度始终相对于实现层次结构表的容器或文件夹。 
  
 **PR_OBJECT_TYPE** 对于通讯簿层次结构MAPI_ABCONT表始终设置为 MAPI_FOLDER，而文件夹层次结构表设置为 MAPI_FOLDER。 
  
 **PR_DISPLAY_TYPE** 是一个数值，与容器或文件夹在层次结构表中的显示方式相关。 它主要用于显示目的，以在视觉上区分容器或文件夹的类型。 许多邮件存储和通讯簿提供程序为不同的显示类型使用图标。 由提供程序提供这些图标;MAPI 不提供默认值。 
  
MAPI 为 PR_DISPLAY_TYPE定义许多值，其中一些值对文件夹有效，其他值用于通讯簿容器的层次结构表。 通常，文件夹的 **PR_DISPLAY_TYPE** 设置为 DT_FOLDER 以指示默认文件夹图标，DT_FOLDER_LINK 指示表示指向其他文件夹的链接的图标，或 DT_FOLDER_SPECIAL 指示特定于应用程序的图标。 DT_FOLDER_LINK用于搜索结果文件夹。 
  
除了这些必需的列之外，通讯簿层次结构表还必须包含 **PR_CONTAINER_FLAGS** 属性。 **PR_CONTAINER_FLAGS** 指示有关层次结构中容器的各种属性，并用于区分一个容器和另一个容器。 
  
通讯簿层次结构表的可选属性是 PR_AB_PROVIDER_ID ( [PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 属性。
  
邮件存储层次结构表在所需的列集包含以下属性：
  
- **PR_FOLDER_TYPE (** [PidTagFolderType)](pidtagfoldertype-canonical-property.md)
    
- **PR_SUBFOLDERS (** [PidTagSubfolders](pidtagsubfolders-canonical-property.md)) 
    
- **PR_CONTENT_COUNT (** [PidTagContentCount](pidtagcontentcount-canonical-property.md)) 
    
- **PR_CONTENT_UNREAD (** [PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md)) 
    
通讯簿提供程序必须在其层次结构表实现中支持以下 **IMAPITable** 方法，因为它们是 MAPI 集成通讯簿所需的： 
  
|||
|:-----|:-----|
|[IMAPITable::QueryColumns](imapitable-querycolumns.md) <br/> |[IMAPITable::QueryPosition](imapitable-queryposition.md) <br/> |
|[IMAPITable::SeekRow](imapitable-seekrow.md) <br/> |[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) <br/> |
|[IMAPITable::FindRow](imapitable-findrow.md) <br/> |[IMAPITable::Restrict](imapitable-restrict.md) <br/> |
|[IMAPITable::CreateBookmark](imapitable-createbookmark.md) <br/> |[IMAPITable::FreeBookmark](imapitable-freebookmark.md) <br/> |
|[IMAPITable::QueryRows](imapitable-queryrows.md) <br/> | <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

