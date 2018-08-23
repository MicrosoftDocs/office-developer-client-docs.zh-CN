---
title: 关于存储区 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 166a8e60-e09d-7473-b61b-35d78a863192
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: d72df30eab5fde4288b5feba1d7045da05117bde
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579373"
---
# <a name="about-the-store-api"></a>关于存储区 API

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
存储 API 提供了 miscellaneous 存储功能存储提供程序。 它提供了以下定义、 数据类型、 属性和接口。
  
定义：
  
- [存储区 API 常量](mapi-constants.md)
    
数据类型：
  
- **[INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md)**
    
- **[MSCAP_SELECTOR](mscap_selector.md)**
    
命名的属性：
  
- **[ArchiveSourceSupportMask](archivesourcesupportmask.md)**
    
- **[CrawlSourceSupportMask](crawlsourcesupportmask.md)**
    
- **[显示服务器文件夹大小](display-server-folder-sizes-property.md)**
    
- **[隐藏会议更新选项](hide-meeting-update-option-property.md)**
    
- **[使存储类型专用](make-store-type-private-property.md)**
    
- **[NoFolderScan](nofolderscan.md)**
    
> [!NOTE]
> 不需要的任何功能提供这些命名属性的存储提供程序可以简单地忽略它们并不在**IMAPIProp**接口中实现支持。 启动 Microsoft Outlook 2003 Service Pack 1 中提供了这些属性，因为将其添加到 Microsoft Outlook 的早期版本中存储不起作用。 如果不存在，或其值为**false**，则将忽略它们。 
  
属性：
  
- **[PR_ADDITIONAL_REN_ENTRYIDS](pidtagadditionalrenentryids-canonical-property.md)**
    
- **[PR_PROVIDER_ITEMID](pidtagprovideritemid-canonical-property.md)**
    
- **[PR_PROVIDER_PARENT_ITEMID](pidtagproviderparentitemid-canonical-property.md)**
    
- **[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)**
    
接口：
  
- **[IFolderSupport](ifoldersupportiunknown.md)**
    
- **[IMSCapabilities](imscapabilitiesiunknown.md)**
    
- **[IProxyStoreObject](iproxystoreobject.md)**
    
## <a name="registering-stores-for-indexing"></a>注册的索引的存储

MAPI 协议处理程序检查 Windows 注册表中以便它应该索引搜索目的的存储。 想要编制索引的存储提供程序必须在 Windows 注册表中注册。 有关注册为进行索引在 Outlook 2013 或 Outlook 2010 中的存储提供程序的详细信息，请参阅[有关注册存储索引](about-registering-stores-for-indexing.md)。
  
## <a name="indexing-stores"></a>索引的存储区

MAPI 存储提供程序可以选择允许 MAPI 协议处理程序在存储中的爬网和索引的邮件或将通知发送到索引器中，仅当邮件编制索引。 有关基于通知的索引的详细信息，请参阅[About Notification-Based 存储索引](about-notification-based-store-indexing.md)。
  

