---
title: 支持在邮件存储提供程序中进行搜索
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30a3fe28-31ca-4eb8-9353-f75f6d339dc7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 545047e90346b0f8e4a88eabcb20573f663f6d02
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349586"
---
# <a name="supporting-searches-in-message-store-providers"></a>支持在邮件存储提供程序中进行搜索

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序通常有一些用户界面组件专门用于搜索邮件存储区中的邮件。 搜索条件是通过[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)和[IMAPIContainer:: GetSearchCriteria](imapicontainer-getsearchcriteria.md)方法在[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)接口中指定的。 
  
客户端使用邮件存储对象的**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 属性来标识邮件存储区中包含搜索结果的文件夹的根文件夹。 搜索结果文件夹通常是邮件存储区中不属于 IPM 文件夹树的顶层的文件夹, 因此是隐藏的。
  
当客户端打开存储在**PR_FINDER_ENTRYID**属性中的条目标识符时, 您的邮件存储提供程序是否使用永久搜索结果文件夹或创建一个该文件夹, 这是一个实现详细信息。 您的邮件存储提供程序使用在创建邮件库时创建的永久文件夹有些容易, 因为这样做可以避免在打开任何文件夹时检查条目标识符, 以查看是否创建搜索结果文件夹。 但是, 并不是所有的邮件存储提供程序都可以这样做;特别是, 只读邮件存储或为旧版数据库提供 MAPI 接口的存储通常不允许, 或者无法在基础存储机制中创建永久搜索结果文件夹。 
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

