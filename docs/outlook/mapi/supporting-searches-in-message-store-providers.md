---
title: 支持在邮件存储区提供程序中进行搜索
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
# <a name="supporting-searches-in-message-store-providers"></a><span data-ttu-id="75447-103">支持在邮件存储区提供程序中进行搜索</span><span class="sxs-lookup"><span data-stu-id="75447-103">Supporting Searches in Message Store Providers</span></span>

  
  
<span data-ttu-id="75447-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="75447-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="75447-105">客户端应用程序通常具有一些专用于搜索消息存储区中的邮件的用户界面组件。</span><span class="sxs-lookup"><span data-stu-id="75447-105">Client applications frequently have some user interface components devoted to searching for messages in a message store.</span></span> <span data-ttu-id="75447-106">搜索条件中指定[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)通过[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)和[IMAPIContainer::GetSearchCriteria](imapicontainer-getsearchcriteria.md)方法的接口。</span><span class="sxs-lookup"><span data-stu-id="75447-106">Search criteria are specified in the [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md) interface by means of the [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) and [IMAPIContainer::GetSearchCriteria](imapicontainer-getsearchcriteria.md) methods.</span></span> 
  
<span data-ttu-id="75447-107">客户端使用的消息存储对象**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 属性可确定包含搜索结果的文件夹的邮件存储区中的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="75447-107">Clients use the message store object's **PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) property to identify the root folder in the message store that contains folders for search results.</span></span> <span data-ttu-id="75447-108">搜索结果文件夹通常是最高级别不属于 IPM 文件夹树和，因此，隐藏的消息存储的一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="75447-108">The search-results folder is often a folder at the top level of the message store that is not part of the IPM folder tree and is, therefore, hidden.</span></span>
  
<span data-ttu-id="75447-109">消息存储提供程序是否使用一个永久的搜索结果文件夹，或创建一个客户端打开存储在**PR_FINDER_ENTRYID**属性中的项标识符时实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="75447-109">Whether your message store provider uses a permanent search-results folder or creates one when a client opens the entry identifier stored in the **PR_FINDER_ENTRYID** property is an implementation detail.</span></span> <span data-ttu-id="75447-110">ア ネ 较更方便地消息存储提供程序，用于创建时创建的消息存储，因为这样可避免出现的错误检查的项标识符，每当打开任何文件夹以查看是否创建的永久文件夹搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="75447-110">It is somewhat easier for your message store provider to use a permanent folder that is created when the message store is created, because doing so avoids the complication of checking the entry identifier whenever any folder is opened to see whether to create a search-results folder.</span></span> <span data-ttu-id="75447-111">不过，并非所有的消息存储提供程序可以实现的;值得注意的是，只读消息存储或通常提供指向旧的数据库的 MAPI 接口的存储不允许使用或不能基础存储机制中创建一个永久的搜索结果的文件夹。</span><span class="sxs-lookup"><span data-stu-id="75447-111">However, not all message store providers can do that; notably, read-only message stores or stores that provide a MAPI interface to a legacy database often are not allowed or are unable to create a permanent search-results folder in the underlying storage mechanism.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="75447-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75447-112">See also</span></span>



[<span data-ttu-id="75447-113">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="75447-113">Message Store Features</span></span>](message-store-features.md)

