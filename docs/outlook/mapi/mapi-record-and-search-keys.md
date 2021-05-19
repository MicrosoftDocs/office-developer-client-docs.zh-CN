---
title: MAPI 记录和搜索键
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: caa7b7f3-a5a1-4f07-98c9-22652ecd5d21
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b1b4c0087cecd9164fc96ce7c5b5415f75dbfb03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434562"
---
# <a name="mapi-record-and-search-keys"></a>MAPI 记录和搜索键

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
记录键和搜索键是分配给许多 MAPI 对象的二进制标识符。 与对象的条目标识符不同，其记录或搜索键可以直接比较，也可以传输。 
  
## <a name="record-keys"></a>记录键

记录键用于比较两个对象。 邮件存储和通讯簿对象必须具有记录密钥，这些记录键存储在[PidTagRecordKey PR_RECORD_KEY (PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性中。  由于记录键标识对象而不是其数据，因此对象的每个实例都有一个唯一的记录键。 文件夹和邮件的记录密钥的范围是邮件存储。 通讯簿容器、邮件用户和通讯组列表的范围是 MAPI 提供的用于集成通讯簿的顶级容器集。
  
记录键可以在另一个资源中重复。 例如，两个不同邮件存储中的不同邮件可以具有相同的记录密钥。 这不同于长期条目标识符;因为长期条目标识符包含对服务提供商的引用，所以它们的范围更广。 邮件存储的记录键在作用域中类似于长期条目标识符;它应在所有邮件存储提供程序中是唯一的。 为了确保这种唯一性，邮件存储提供程序通常将记录键设置为一个值，该值是 **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性与邮件存储唯一标识符的组合。
  
## <a name="search-keys"></a>搜索键

搜索键用于比较两个对象的数据。 对象的搜索键存储在该对象的 PR_SEARCH_KEY ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中。  因为搜索键表示对象的数据，而不是对象本身，所以两个具有相同的数据的不同对象可以具有相同的搜索键。 例如，在复制对象时，原始对象及其副本具有相同的数据和相同的搜索键。
  
邮件和消息用户具有搜索键。 邮件的搜索键是邮件数据的唯一标识符。 邮件存储提供程序在邮件 **创建PR_SEARCH_KEY提供** 邮件的托管属性。 通讯簿条目的搜索键从通讯簿条目的地址类型 (**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) ) 和地址 (**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) ) 计算。 如果通讯簿条目是可写的，则除非已使用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法设置了地址类型和地址，并且已使用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法保存了该条目，所以该条目可能不可用。 当这些地址属性发生更改时，在通过 **SaveChanges** 调用提交更改之前，相应的搜索键可能未与新值同步。 
  
对象的记录键的值可以与搜索键的值相同或不同，具体取决于服务提供商。 某些服务提供商对对象的搜索键、记录键和条目标识符使用相同的值。 其他服务提供商为其每个对象的标识符分配唯一值。 
  
## <a name="see-also"></a>另请参阅



[MAPI 应用程序开发](mapi-application-development.md)

