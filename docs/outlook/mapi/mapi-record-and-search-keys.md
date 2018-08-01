---
title: MAPI 记录和搜索键
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: caa7b7f3-a5a1-4f07-98c9-22652ecd5d21
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1e1b05be64029f80ec8a7379ed7b313b9cf645fd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776300"
---
# <a name="mapi-record-and-search-keys"></a>MAPI 记录和搜索键

  
  
**适用于**： Outlook 
  
记录的键和搜索键是分配给多个 MAPI 对象的二进制标识符。 与对象的项标识符，其记录或搜索键直接是相当以及可传送。 
  
## <a name="record-keys"></a>记录的键

记录项用于比较两个对象。 消息存储和地址簿对象都必须具有记录键，存储在其**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性。 由于记录密钥标识对象而不是其数据，每个对象的实例具有唯一的记录关键字。 消息存储库文件夹和邮件的记录密钥的范围。 通讯簿容器、 邮件用户和通讯组列表的范围是一套集成的通讯簿中用于提供 MAPI 的顶级容器。
  
可以在其他资源中复制记录的键。 例如，两个不同的消息存储中的不同消息可以具有相同记录键。 这一点不同于长期条目标识符;长期条目标识符包含服务提供程序的引用，因为具有更大范围。 消息存储记录键处于类似范围为长期条目标识符;它应是唯一的跨所有消息存储提供程序。 若要确保此唯一性，消息存储提供程序通常将其记录项设置为一个值，则它们**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 的属性和消息存储对是唯一的标识符的组合。
  
## <a name="search-keys"></a>搜索键

搜索关键字用于比较两个对象中的数据。 对象的搜索关键字都存储在其**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。 由于搜索键表示对象的数据和对象本身，使用相同的数据的两个不同对象可以具有相同的搜索键。 复制对象时，例如原始对象和其副本具有相同的数据和相同的搜索键。
  
邮件和消息的用户具有搜索键。 搜索关键字消息的消息的数据的唯一标识符。 创建邮件时，消息存储提供程序提供了一条消息**PR_SEARCH_KEY**属性。 通讯簿条目的搜索项从其地址类型 (**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))) 和地址 (**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))) 计算。 如果写通讯簿条目，其搜索键可能不可用，直到的地址类型和地址已设置通过使用[IMAPIProp::SetProps](imapiprop-setprops.md)方法，并使用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法已保存了该条目。 这些地址属性更改时，可能为相应的搜索关键字，无法使用**SaveChanges**呼叫提交更改之前与新的值进行同步。 
  
对象的记录项的值可以是相同或不同于其搜索关键字，具体取决于服务提供商的值。 某些服务提供商对象的搜索关键字、 记录键和项标识符使用相同的值。 其他服务提供程序分配其对象的标识符的每个唯一值。 
  
## <a name="see-also"></a>另请参阅



[MAPI 应用程序开发](mapi-application-development.md)

