---
title: 关于存储 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 166a8e60-e09d-7473-b61b-35d78a863192
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: fb9b0a4c8ac1a2f41a0fddcd746dba5fc4bae1a2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405553"
---
# <a name="about-the-store-api"></a>关于存储 API

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
应用商店 API 为存储提供程序提供杂项存储功能。 它提供以下定义、数据类型、属性和接口。
  
定义：
  
- [应用商店 API 的常量](mapi-constants.md)
    
数据类型：
  
- **[INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md)**
    
- **[MSCAP_SELECTOR](mscap_selector.md)**
    
命名属性：
  
- **[ArchiveSourceSupportMask](archivesourcesupportmask.md)**
    
- **[CrawlSourceSupportMask](crawlsourcesupportmask.md)**
    
- **[显示服务器文件夹大小](display-server-folder-sizes-property.md)**
    
- **[隐藏会议更新选项](hide-meeting-update-option-property.md)**
    
- **[使应用商店类型成为私有](make-store-type-private-property.md)**
    
- **[NoFolderScan](nofolderscan.md)**
    
> [!NOTE]
> 不需要这些命名属性提供的任何功能的存储提供程序可以忽略它们，而不是 **在 IMAPIProp** 接口中实现支持。 由于这些属性从 Microsoft Outlook 2003 Service Pack 1 开始提供，因此将它们添加到 Microsoft Outlook 早期版本的应用商店不起作用。 如果它们不存在或其值为 false ，则忽略 **它们**。 
  
属性：
  
- **[PR_ADDITIONAL_REN_ENTRYIDS](pidtagadditionalrenentryids-canonical-property.md)**
    
- **[PR_PROVIDER_ITEMID](pidtagprovideritemid-canonical-property.md)**
    
- **[PR_PROVIDER_PARENT_ITEMID](pidtagproviderparentitemid-canonical-property.md)**
    
- **[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)**
    
接口：
  
- **[IFolderSupport](ifoldersupportiunknown.md)**
    
- **[IMSCapabilities](imscapabilitiesiunknown.md)**
    
- **[IProxyStoreObject](iproxystoreobject.md)**
    
## <a name="registering-stores-for-indexing"></a>注册存储以编制索引

MAPI 协议处理程序Windows注册表中查找出于搜索目的应编制索引的存储区。 必须在注册表中注册要编制索引Windows提供程序。 有关在 Outlook 2013 或 Outlook 2010 中注册存储提供程序以编制索引的信息，请参阅关于为索引注册[存储](about-registering-stores-for-indexing.md)。
  
## <a name="indexing-stores"></a>索引存储

MAPI 存储提供程序可以选择允许 MAPI 协议处理程序对存储中的邮件进行爬网和编制索引，或者仅在有要编制索引的消息时向索引器发送通知。 有关基于通知的索引功能详细信息，请参阅关于Notification-Based [存储索引](about-notification-based-store-indexing.md)。
  

