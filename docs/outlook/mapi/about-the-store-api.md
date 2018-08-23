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
# <a name="about-the-store-api"></a><span data-ttu-id="53990-103">关于存储区 API</span><span class="sxs-lookup"><span data-stu-id="53990-103">About the Store API</span></span>

  
  
<span data-ttu-id="53990-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53990-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53990-105">存储 API 提供了 miscellaneous 存储功能存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="53990-105">The Store API provides miscellaneous store functionality to store providers.</span></span> <span data-ttu-id="53990-106">它提供了以下定义、 数据类型、 属性和接口。</span><span class="sxs-lookup"><span data-stu-id="53990-106">It provides the following defintions, data types, properties, and interfaces.</span></span>
  
<span data-ttu-id="53990-107">定义：</span><span class="sxs-lookup"><span data-stu-id="53990-107">Definitions:</span></span>
  
- [<span data-ttu-id="53990-108">存储区 API 常量</span><span class="sxs-lookup"><span data-stu-id="53990-108">Constants for the Store API</span></span>](mapi-constants.md)
    
<span data-ttu-id="53990-109">数据类型：</span><span class="sxs-lookup"><span data-stu-id="53990-109">Data types:</span></span>
  
- <span data-ttu-id="53990-110">**[INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-110">**[INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md)**</span></span>
    
- <span data-ttu-id="53990-111">**[MSCAP_SELECTOR](mscap_selector.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-111">**[MSCAP_SELECTOR](mscap_selector.md)**</span></span>
    
<span data-ttu-id="53990-112">命名的属性：</span><span class="sxs-lookup"><span data-stu-id="53990-112">Named Properties:</span></span>
  
- <span data-ttu-id="53990-113">**[ArchiveSourceSupportMask](archivesourcesupportmask.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-113">**[ArchiveSourceSupportMask](archivesourcesupportmask.md)**</span></span>
    
- <span data-ttu-id="53990-114">**[CrawlSourceSupportMask](crawlsourcesupportmask.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-114">**[CrawlSourceSupportMask](crawlsourcesupportmask.md)**</span></span>
    
- <span data-ttu-id="53990-115">**[显示服务器文件夹大小](display-server-folder-sizes-property.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-115">**[Display Server Folder Sizes](display-server-folder-sizes-property.md)**</span></span>
    
- <span data-ttu-id="53990-116">**[隐藏会议更新选项](hide-meeting-update-option-property.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-116">**[Hide Meeting Update Option](hide-meeting-update-option-property.md)**</span></span>
    
- <span data-ttu-id="53990-117">**[使存储类型专用](make-store-type-private-property.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-117">**[Make Store Type Private](make-store-type-private-property.md)**</span></span>
    
- <span data-ttu-id="53990-118">**[NoFolderScan](nofolderscan.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-118">**[NoFolderScan](nofolderscan.md)**</span></span>
    
> [!NOTE]
> <span data-ttu-id="53990-119">不需要的任何功能提供这些命名属性的存储提供程序可以简单地忽略它们并不在**IMAPIProp**接口中实现支持。</span><span class="sxs-lookup"><span data-stu-id="53990-119">Store providers that do not require any of the functionality offered by these named properties can simply ignore them and not implement support in the **IMAPIProp** interface.</span></span> <span data-ttu-id="53990-120">启动 Microsoft Outlook 2003 Service Pack 1 中提供了这些属性，因为将其添加到 Microsoft Outlook 的早期版本中存储不起作用。</span><span class="sxs-lookup"><span data-stu-id="53990-120">Because these properties are provided starting in Microsoft Outlook 2003 Service Pack 1, adding them to a store in an earlier version of Microsoft Outlook has no effect.</span></span> <span data-ttu-id="53990-121">如果不存在，或其值为**false**，则将忽略它们。</span><span class="sxs-lookup"><span data-stu-id="53990-121">They are ignored if they do not exist or if their value is **false**.</span></span> 
  
<span data-ttu-id="53990-122">属性：</span><span class="sxs-lookup"><span data-stu-id="53990-122">Properties:</span></span>
  
- <span data-ttu-id="53990-123">**[PR_ADDITIONAL_REN_ENTRYIDS](pidtagadditionalrenentryids-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-123">**[PR_ADDITIONAL_REN_ENTRYIDS](pidtagadditionalrenentryids-canonical-property.md)**</span></span>
    
- <span data-ttu-id="53990-124">**[PR_PROVIDER_ITEMID](pidtagprovideritemid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-124">**[PR_PROVIDER_ITEMID](pidtagprovideritemid-canonical-property.md)**</span></span>
    
- <span data-ttu-id="53990-125">**[PR_PROVIDER_PARENT_ITEMID](pidtagproviderparentitemid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-125">**[PR_PROVIDER_PARENT_ITEMID](pidtagproviderparentitemid-canonical-property.md)**</span></span>
    
- <span data-ttu-id="53990-126">**[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-126">**[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)**</span></span>
    
<span data-ttu-id="53990-127">接口：</span><span class="sxs-lookup"><span data-stu-id="53990-127">Interfaces:</span></span>
  
- <span data-ttu-id="53990-128">**[IFolderSupport](ifoldersupportiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-128">**[IFolderSupport](ifoldersupportiunknown.md)**</span></span>
    
- <span data-ttu-id="53990-129">**[IMSCapabilities](imscapabilitiesiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-129">**[IMSCapabilities](imscapabilitiesiunknown.md)**</span></span>
    
- <span data-ttu-id="53990-130">**[IProxyStoreObject](iproxystoreobject.md)**</span><span class="sxs-lookup"><span data-stu-id="53990-130">**[IProxyStoreObject](iproxystoreobject.md)**</span></span>
    
## <a name="registering-stores-for-indexing"></a><span data-ttu-id="53990-131">注册的索引的存储</span><span class="sxs-lookup"><span data-stu-id="53990-131">Registering Stores for Indexing</span></span>

<span data-ttu-id="53990-132">MAPI 协议处理程序检查 Windows 注册表中以便它应该索引搜索目的的存储。</span><span class="sxs-lookup"><span data-stu-id="53990-132">The MAPI Protocol Handler checks the Windows registry for stores that it should index for search purposes.</span></span> <span data-ttu-id="53990-133">想要编制索引的存储提供程序必须在 Windows 注册表中注册。</span><span class="sxs-lookup"><span data-stu-id="53990-133">Store providers that want to be indexed must be registered in the Windows registry.</span></span> <span data-ttu-id="53990-134">有关注册为进行索引在 Outlook 2013 或 Outlook 2010 中的存储提供程序的详细信息，请参阅[有关注册存储索引](about-registering-stores-for-indexing.md)。</span><span class="sxs-lookup"><span data-stu-id="53990-134">For more information about registering store providers for indexing in Outlook 2013 or Outlook 2010, see [About Registering Stores for Indexing](about-registering-stores-for-indexing.md).</span></span>
  
## <a name="indexing-stores"></a><span data-ttu-id="53990-135">索引的存储区</span><span class="sxs-lookup"><span data-stu-id="53990-135">Indexing Stores</span></span>

<span data-ttu-id="53990-136">MAPI 存储提供程序可以选择允许 MAPI 协议处理程序在存储中的爬网和索引的邮件或将通知发送到索引器中，仅当邮件编制索引。</span><span class="sxs-lookup"><span data-stu-id="53990-136">MAPI store providers can choose to allow the MAPI Protocol Handler to crawl and index messages in the store, or send notifications to the indexer only when there are messages to be indexed.</span></span> <span data-ttu-id="53990-137">有关基于通知的索引的详细信息，请参阅[About Notification-Based 存储索引](about-notification-based-store-indexing.md)。</span><span class="sxs-lookup"><span data-stu-id="53990-137">For more information about notifications-based indexing, see [About Notification-Based Store Indexing](about-notification-based-store-indexing.md).</span></span>
  

