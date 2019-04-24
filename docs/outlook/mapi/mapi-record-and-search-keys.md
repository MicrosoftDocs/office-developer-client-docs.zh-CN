---
title: MAPI 记录和搜索关键字
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: caa7b7f3-a5a1-4f07-98c9-22652ecd5d21
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b1b4c0087cecd9164fc96ce7c5b5415f75dbfb03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328131"
---
# <a name="mapi-record-and-search-keys"></a>MAPI 记录和搜索关键字

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
记录键和搜索键是分配给多个 MAPI 对象的二进制标识符。 与对象的条目标识符不同的是, 它的记录或搜索键可直接比较并传输。 
  
## <a name="record-keys"></a>记录键

记录键用于比较两个对象。 邮件存储和通讯簿对象必须具有记录关键字, 这些关键字存储在其**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性中。 由于记录键标识的是对象而不是其数据, 因此对象的每个实例都有一个唯一的 record 关键字。 文件夹和邮件的记录密钥的范围是邮件存储区。 通讯簿容器、邮件用户和通讯组列表的作用域是 MAPI 提供的用于集成通讯簿的一组顶级容器。
  
记录键可以复制到其他资源中。 例如, 两个不同邮件存储区中的不同邮件可以具有相同的记录密钥。 这与长期条目标识符不同;由于长期条目标识符包含对服务提供程序的引用, 因此它们具有更宽的作用域。 邮件存储的记录密钥在范围内与长期条目标识符相似;它在所有邮件存储区提供程序中应是唯一的。 为了确保这种唯一性, 邮件存储提供程序通常会将其记录密钥设置为其**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性和唯一的邮件存储区的标识符的值。
  
## <a name="search-keys"></a>搜索键

搜索关键字用于比较两个对象中的数据。 对象的搜索关键字存储在其**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中。 由于搜索关键字代表对象的数据而不是对象本身, 因此具有相同数据的两个不同对象可以具有相同的搜索关键字。 例如, 在复制对象时, 原始对象及其副本都具有相同的数据和相同的搜索关键字。
  
邮件和邮件用户具有搜索关键字。 邮件的搜索关键字是邮件数据的唯一标识符。 邮件存储区提供程序在邮件创建时提供邮件的**PR_SEARCH_KEY**属性。 通讯簿条目的搜索关键字是通过其地址类型 (**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))) 和 address (**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))) 计算得出的。 如果通讯簿条目是可写的, 则在使用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法设置地址类型和地址并使用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法保存条目之前, 其搜索关键字可能不可用。 当这些地址属性发生更改时, 在使用**SaveChanges**调用提交更改之前, 相应的搜索关键字可能不会与新值同步。 
  
对象的记录键的值可以与它的搜索键的值相同或不同, 具体取决于服务提供程序。 某些服务提供程序对对象的搜索关键字、记录键和条目标识符使用相同的值。 其他服务提供程序为其每个对象的标识符分配唯一值。 
  
## <a name="see-also"></a>另请参阅



[MAPI 应用程序开发](mapi-application-development.md)

