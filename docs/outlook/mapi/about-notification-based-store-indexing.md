---
title: 关于基于通知的存储区索引
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: b3685890-117c-9acc-e19f-cf22a349a088
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 338ae3c3c8d8b4037ab0c7b46916e45cf5a8ded2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774470"
---
# <a name="about-notification-based-store-indexing"></a>关于基于通知的存储区索引

  
  
**适用于**： Outlook 
  
MAPI 存储提供程序可以指定的 MAPI 协议处理程序爬网和索引是否消息在存储中，或存储是否要编制索引的邮件时将通知发送到索引器。 后者称为基于通知的索引，并且支持基于通知的索引的存储，称为 pusher 存储区。
  
支持基于通知的索引集**STORE_PUSHER_OK**标志**[PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** 属性中存储提供程序。 MAPI 协议处理程序或客户端可以获取**PR_STORE_SUPPORT_MASK**属性，以确定存储的特征。 
  
每当附件、 文件夹或要编制索引的消息，存储提供程序生成 MAPI 统一资源定位器 (URL) 标识对象编制索引，并将其发送到索引器。 此 MAPI URL 以 Unicode 编码，必须唯一标识到 MAPI 协议处理程序的对象。 有关 MAPI Url 的详细信息，请参阅[有关基于通知索引 MAPI Url](about-mapi-urls-for-notification-based-indexing.md)。
  
索引器始终不能索引所有内容之前关闭发生 pusher 存储区中，因为 pusher 存储必须保留需要推送。 存储提供程序发送通知有关需要编制索引的对象，它在**[通知](notification.md)** 结构的**ulEventType**成员指定通知类型**fnevIndexing** 。 **通知**结构的**信息**成员包含**[EXTENDED_NOTIFICATION](extended_notification.md)** 结构。 存储提供程序标识的**[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)** 属性中的过程。 它还标识[INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md)结构中的过程，并将此信息传递的**pbEventParameters**成员**EXTENDED_NOTIFICATION**结构的一部分。 如果进程关闭或崩溃时，将能够立即检测，并停止索引 pusher 存储 MAPI 协议处理程序。 
  
## <a name="see-also"></a>另请参阅



[关于存储区 API](about-the-store-api.md)
  
[MAPI 常量](mapi-constants.md)

