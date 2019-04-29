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
  
层次结构表包含有关邮件存储区中的文件夹或通讯簿容器中的容器的信息。 层次结构表中的每一行都包含一组列, 其中包含一个文件夹或通讯簿容器的相关信息。 层次结构表主要由客户端使用, 并由邮件存储提供程序实现, 以显示文件夹和子文件夹树, 并由通讯簿提供程序实现, 以显示通讯簿中的容器树。 无法保留子容器的容器 (由其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中缺少 AB_SUBCONTAINERS 标志表示) 不实现层次结构表。
  
可通过调用来访问层次结构表:
  
- [IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md)。
    
    - 和
    
- [IMAPIProp:: OpenProperty](imapiprop-openproperty.md)将**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 作为属性标记, 将 IID_IMAPITable 作为接口标识符进行传递。
    
容器和文件夹必须支持这两种方法来检索表属性。 服务提供商仅支持一种访问这些表的方式是不可接受的, 因为客户端希望能够做出选择。 
  
> [!IMPORTANT]
> 不能保证存储提供程序遵循为层次结构表指定的排序顺序集。 
  
对**IMAPIProp:: OpenProperty**的调用需要通过打开其对应的属性**PR_CONTAINER_HIERARCHY**来访问层次结构表。 [! 注意] 尽管无法通过文件夹或容器的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法检索**PR_CONTAINER_HIERARCHY** , 但它包含在由[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法返回的属性标记数组中。 
  
 **PR_CONTAINER_HIERARCHY**还可用于包含或排除复制操作中的层次结构表。 如果客户端在*lpExcludeProps*参数中为[IMAPIProp:: CopyTo](imapiprop-copyto.md)在复制操作中指定了**PR_CONTAINER_HIERARCHY** , 则新的文件夹或容器将不支持原始文件夹或容器的层次结构表。 
  
以下属性构成了层次结构表中所需的列集:
  
|||
|:-----|:-----|
|**PR_COMMENT**([PidTagComment](pidtagcomment-canonical-property.md))  <br/> |**PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md))  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |**PR_STATUS**([PidTagStatus](pidtagstatus-canonical-property.md))  <br/> |
   
 **PR_DISPLAY_NAME**包含应显示在层次结构显示中的容器或文件夹的名称。 
  
 **PR_ENTRYID**是与此容器或文件夹相关联的条目标识符。 它应为长期条目标识符。 客户端和 MAPI 可以将此条目标识符传递给**OpenEntry** , 以打开容器或文件夹, 并通过调用[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)来查看其内容。 
  
 **PR_DEPTH**是一个数值, 指示此容器或文件夹的缩进级别, 其中零为最高级别。 容器或文件夹所在的层次结构中的深度越深, 其**PR_DEPTH**属性的值就越高。 客户端使用**PR_DEPTH**属性来适当地显示层次结构表, 以便用户可以清楚地看到父关系和子关系。 容器或文件夹深度始终相对于实现层次结构表的容器或文件夹。 
  
 对于通讯簿层次结构表和 MAPI_FOLDER (对于文件夹层次结构表), **PR_OBJECT_TYPE**始终设置为 MAPI_ABCONT。 
  
 **PR_DISPLAY_TYPE**是一个数字值, 它与容器或文件夹在层次结构表中的显示方式相关。 它主要用于显示目的, 以在容器或文件夹的类型之间进行区分。 许多邮件存储和通讯簿提供程序将图标用于不同的显示类型。 提供程序需要提供这些图标;MAPI 不提供默认值。 
  
MAPI 为**PR_DISPLAY_TYPE**定义了多个值, 有些值对与通讯簿容器的层次结构表一起使用的文件夹和其他值有效。 通常情况下, 文件夹的**PR_DISPLAY_TYPE**设置为 DT_FOLDER, 以指示默认的文件夹图标、DT_FOLDER_LINK 指示表示指向另一个文件夹的链接的图标, 或 DT_FOLDER_SPECIAL 指示特定于应用程序的图标。 DT_FOLDER_LINK 与搜索结果文件夹一起使用。 
  
除了这些必需的列之外, 通讯簿层次结构表必须包含**PR_CONTAINER_FLAGS**属性。 **PR_CONTAINER_FLAGS**指示有关层次结构中的容器的各种属性, 并用于区分一个容器与另一个容器。 
  
通讯簿层次结构表的可选属性是**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 属性。
  
邮件存储区层次结构表在其必需的列集中包含这些属性:
  
- **PR_FOLDER_TYPE**([PidTagFolderType](pidtagfoldertype-canonical-property.md))
    
- **PR_SUBFOLDERS**([PidTagSubfolders](pidtagsubfolders-canonical-property.md))
    
- **PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))
    
- **PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))
    
通讯簿提供程序必须支持其层次结构表实现中的以下**IMAPITable**方法, 因为它们是 MAPI 集成通讯簿所必需的: 
  
|||
|:-----|:-----|
|[IMAPITable::QueryColumns](imapitable-querycolumns.md) <br/> |[IMAPITable::QueryPosition](imapitable-queryposition.md) <br/> |
|[IMAPITable::SeekRow](imapitable-seekrow.md) <br/> |[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) <br/> |
|[IMAPITable::FindRow](imapitable-findrow.md) <br/> |[IMAPITable::Restrict](imapitable-restrict.md) <br/> |
|[IMAPITable::CreateBookmark](imapitable-createbookmark.md) <br/> |[IMAPITable::FreeBookmark](imapitable-freebookmark.md) <br/> |
|[IMAPITable::QueryRows](imapitable-queryrows.md) <br/> | <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

