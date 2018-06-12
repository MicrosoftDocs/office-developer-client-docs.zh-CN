---
title: 在消息存储提供程序支持搜索
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30a3fe28-31ca-4eb8-9353-f75f6d339dc7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0cd8bbe14e6af020ec5c93cd46a24853d1c8401c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778925"
---
# <a name="supporting-searches-in-message-store-providers"></a>在消息存储提供程序支持搜索

  
  
**适用于**： Outlook 
  
客户端应用程序通常具有一些专用于搜索消息存储区中的邮件的用户界面组件。 搜索条件中指定[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)通过[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)和[IMAPIContainer::GetSearchCriteria](imapicontainer-getsearchcriteria.md)方法的接口。 
  
客户端使用的消息存储对象**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 属性可确定包含搜索结果的文件夹的邮件存储区中的根文件夹。 搜索结果文件夹通常是最高级别不属于 IPM 文件夹树和，因此，隐藏的消息存储的一个文件夹。
  
消息存储提供程序是否使用一个永久的搜索结果文件夹，或创建一个客户端打开存储在**PR_FINDER_ENTRYID**属性中的项标识符时实现详细信息。 ア ネ 较更方便地消息存储提供程序，用于创建时创建的消息存储，因为这样可避免出现的错误检查的项标识符，每当打开任何文件夹以查看是否创建的永久文件夹搜索结果文件夹。 不过，并非所有的消息存储提供程序可以实现的;值得注意的是，只读消息存储或通常提供指向旧的数据库的 MAPI 接口的存储不允许使用或不能基础存储机制中创建一个永久的搜索结果的文件夹。 
  
## <a name="see-also"></a>另请参阅



[消息存储功能](message-store-features.md)

