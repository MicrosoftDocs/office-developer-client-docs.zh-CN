---
title: 关于Notification-Based存储索引
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: b3685890-117c-9acc-e19f-cf22a349a088
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3dd551dd0c1ea229381e5dd01c5cf6fa04790c30
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409172"
---
# <a name="about-notification-based-store-indexing"></a>关于Notification-Based存储索引

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 存储提供程序可以指定 MAPI 协议处理程序是否对存储中的邮件进行爬网和编制索引，或者当有消息要编制索引时，存储是否向索引器发送通知。 后者称为基于通知的索引，支持基于通知的索引的存储区称为推送器存储。
  
支持基于通知的索引的存储区提供程序设置 STORE_PUSHER_OK **属性中的****[PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** 标记。 MAPI 协议处理程序或客户端可以获取 PR_STORE_SUPPORT_MASK **属性来确定** 存储的特征。 
  
每当有附件、文件夹或邮件要编制索引时，存储提供程序都会生成 MAPI 统一资源定位器 (URL) 标识要编制索引的对象并将其发送到索引器。 此 MAPI URL 采用 Unicode 编码，并且必须唯一地将对象标识到 MAPI 协议处理程序。 有关 MAPI URL 详细信息，请参阅 [关于 MAPI URL for Notification-Based Indexing](about-mapi-urls-for-notification-based-indexing.md)。
  
因为在推送器存储中发生关闭之前，索引器不能始终索引所有内容，所以推送器存储必须保留需要推送的项。 当存储提供程序发送有关需要编制索引的对象的通知时，它会在 **[NOTIFICATION](notification.md)** 结构的 **ulEventType** 成员中指定通知类型 **fnevIndexing。** **通知** 结构的 **info** 成员包含 **[EXTENDED_NOTIFICATION](extended_notification.md)** 结构。 存储提供程序标识 PR_SEARCH_OWNER_ID **[中的过程](pidtagsearchownerid-canonical-property.md)** 。 它还标识 INDEX_SEARCH_PUSHER_PROCESS 结构中的过程 [](index_search_pusher_process.md)，并作为 EXTENDED_NOTIFICATION 结构的 **pbEventParameters** 成员 **传递此信息。** 如果进程关闭或崩溃，MAPI 协议处理程序将能够立即检测该情况并停止索引推送器存储。 
  
## <a name="see-also"></a>另请参阅



[关于存储 API](about-the-store-api.md)
  
[MAPI 常量](mapi-constants.md)

