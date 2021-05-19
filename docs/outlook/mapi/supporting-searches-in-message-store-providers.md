---
title: 支持邮件存储提供程序中的搜索
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30a3fe28-31ca-4eb8-9353-f75f6d339dc7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 545047e90346b0f8e4a88eabcb20573f663f6d02
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425384"
---
# <a name="supporting-searches-in-message-store-providers"></a>支持邮件存储提供程序中的搜索

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序通常具有一些专用于在邮件存储中搜索邮件的用户界面组件。 搜索条件通过[IMAPIContainer：：SetSearchCriteria](imapicontainer-setsearchcriteria.md)和[IMAPIContainer：：GetSearchCriteria](imapicontainer-getsearchcriteria.md)方法在[IMAPIContainer ： IMAPIProp](imapicontainerimapiprop.md)接口中指定。 
  
客户端使用邮件存储对象的 PR_FINDER_ENTRYID  ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 属性标识邮件存储中包含搜索结果文件夹的根文件夹。 搜索结果文件夹通常是邮件存储顶层的文件夹，该文件夹不是 IPM 文件夹树的一部分，因此处于隐藏状态。
  
邮件存储提供程序是使用永久搜索结果文件夹，还是当客户端打开存储在 PR_FINDER_ENTRYID **属性中的** 条目标识符时创建一个文件夹是一个实现详细信息。 邮件存储提供程序使用创建邮件存储时创建的永久文件夹稍微容易一些，因为这样做可以避免在打开任何文件夹时检查条目标识符以查看是否创建搜索结果文件夹的复杂性。 但是，并非所有邮件存储提供程序都可以这样做;值得注意的是，通常不允许为旧版数据库提供 MAPI 接口的只读邮件存储或存储，或者无法在基础存储机制中创建永久性搜索结果文件夹。 
  
## <a name="see-also"></a>另请参阅



[邮件存储功能](message-store-features.md)

