---
title: 关于存储 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 166a8e60-e09d-7473-b61b-35d78a863192
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: fb9b0a4c8ac1a2f41a0fddcd746dba5fc4bae1a2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405553"
---
# <a name="about-the-store-api"></a><span data-ttu-id="ec125-103">关于存储 API</span><span class="sxs-lookup"><span data-stu-id="ec125-103">About the Store API</span></span>

  
  
<span data-ttu-id="ec125-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ec125-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ec125-105">应用商店 API 为存储提供程序提供杂项存储功能。</span><span class="sxs-lookup"><span data-stu-id="ec125-105">The Store API provides miscellaneous store functionality to store providers.</span></span> <span data-ttu-id="ec125-106">它提供以下定义、数据类型、属性和接口。</span><span class="sxs-lookup"><span data-stu-id="ec125-106">It provides the following defintions, data types, properties, and interfaces.</span></span>
  
<span data-ttu-id="ec125-107">定义：</span><span class="sxs-lookup"><span data-stu-id="ec125-107">Definitions:</span></span>
  
- [<span data-ttu-id="ec125-108">应用商店 API 的常量</span><span class="sxs-lookup"><span data-stu-id="ec125-108">Constants for the Store API</span></span>](mapi-constants.md)
    
<span data-ttu-id="ec125-109">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ec125-109">Data types:</span></span>
  
- <span data-ttu-id="ec125-110">**[INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-110">**[INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md)**</span></span>
    
- <span data-ttu-id="ec125-111">**[MSCAP_SELECTOR](mscap_selector.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-111">**[MSCAP_SELECTOR](mscap_selector.md)**</span></span>
    
<span data-ttu-id="ec125-112">命名属性：</span><span class="sxs-lookup"><span data-stu-id="ec125-112">Named Properties:</span></span>
  
- <span data-ttu-id="ec125-113">**[ArchiveSourceSupportMask](archivesourcesupportmask.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-113">**[ArchiveSourceSupportMask](archivesourcesupportmask.md)**</span></span>
    
- <span data-ttu-id="ec125-114">**[CrawlSourceSupportMask](crawlsourcesupportmask.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-114">**[CrawlSourceSupportMask](crawlsourcesupportmask.md)**</span></span>
    
- <span data-ttu-id="ec125-115">**[显示服务器文件夹大小](display-server-folder-sizes-property.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-115">**[Display Server Folder Sizes](display-server-folder-sizes-property.md)**</span></span>
    
- <span data-ttu-id="ec125-116">**[隐藏会议更新选项](hide-meeting-update-option-property.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-116">**[Hide Meeting Update Option](hide-meeting-update-option-property.md)**</span></span>
    
- <span data-ttu-id="ec125-117">**[使应用商店类型成为私有](make-store-type-private-property.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-117">**[Make Store Type Private](make-store-type-private-property.md)**</span></span>
    
- <span data-ttu-id="ec125-118">**[NoFolderScan](nofolderscan.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-118">**[NoFolderScan](nofolderscan.md)**</span></span>
    
> [!NOTE]
> <span data-ttu-id="ec125-119">不需要这些命名属性提供的任何功能的存储提供程序可以忽略它们，而不是 **在 IMAPIProp** 接口中实现支持。</span><span class="sxs-lookup"><span data-stu-id="ec125-119">Store providers that do not require any of the functionality offered by these named properties can simply ignore them and not implement support in the **IMAPIProp** interface.</span></span> <span data-ttu-id="ec125-120">由于这些属性从 Microsoft Outlook 2003 Service Pack 1 开始提供，因此将它们添加到 Microsoft Outlook 早期版本的应用商店不起作用。</span><span class="sxs-lookup"><span data-stu-id="ec125-120">Because these properties are provided starting in Microsoft Outlook 2003 Service Pack 1, adding them to a store in an earlier version of Microsoft Outlook has no effect.</span></span> <span data-ttu-id="ec125-121">如果它们不存在或其值为 false ，则忽略 **它们**。</span><span class="sxs-lookup"><span data-stu-id="ec125-121">They are ignored if they do not exist or if their value is **false**.</span></span> 
  
<span data-ttu-id="ec125-122">属性：</span><span class="sxs-lookup"><span data-stu-id="ec125-122">Properties:</span></span>
  
- <span data-ttu-id="ec125-123">**[PR_ADDITIONAL_REN_ENTRYIDS](pidtagadditionalrenentryids-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-123">**[PR_ADDITIONAL_REN_ENTRYIDS](pidtagadditionalrenentryids-canonical-property.md)**</span></span>
    
- <span data-ttu-id="ec125-124">**[PR_PROVIDER_ITEMID](pidtagprovideritemid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-124">**[PR_PROVIDER_ITEMID](pidtagprovideritemid-canonical-property.md)**</span></span>
    
- <span data-ttu-id="ec125-125">**[PR_PROVIDER_PARENT_ITEMID](pidtagproviderparentitemid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-125">**[PR_PROVIDER_PARENT_ITEMID](pidtagproviderparentitemid-canonical-property.md)**</span></span>
    
- <span data-ttu-id="ec125-126">**[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-126">**[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)**</span></span>
    
<span data-ttu-id="ec125-127">接口：</span><span class="sxs-lookup"><span data-stu-id="ec125-127">Interfaces:</span></span>
  
- <span data-ttu-id="ec125-128">**[IFolderSupport](ifoldersupportiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-128">**[IFolderSupport](ifoldersupportiunknown.md)**</span></span>
    
- <span data-ttu-id="ec125-129">**[IMSCapabilities](imscapabilitiesiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-129">**[IMSCapabilities](imscapabilitiesiunknown.md)**</span></span>
    
- <span data-ttu-id="ec125-130">**[IProxyStoreObject](iproxystoreobject.md)**</span><span class="sxs-lookup"><span data-stu-id="ec125-130">**[IProxyStoreObject](iproxystoreobject.md)**</span></span>
    
## <a name="registering-stores-for-indexing"></a><span data-ttu-id="ec125-131">注册存储以编制索引</span><span class="sxs-lookup"><span data-stu-id="ec125-131">Registering Stores for Indexing</span></span>

<span data-ttu-id="ec125-132">MAPI 协议处理程序Windows注册表中查找出于搜索目的应编制索引的存储区。</span><span class="sxs-lookup"><span data-stu-id="ec125-132">The MAPI Protocol Handler checks the Windows registry for stores that it should index for search purposes.</span></span> <span data-ttu-id="ec125-133">必须在注册表中注册要编制索引Windows提供程序。</span><span class="sxs-lookup"><span data-stu-id="ec125-133">Store providers that want to be indexed must be registered in the Windows registry.</span></span> <span data-ttu-id="ec125-134">有关在 Outlook 2013 或 Outlook 2010 中注册存储提供程序以编制索引的信息，请参阅关于为索引注册[存储](about-registering-stores-for-indexing.md)。</span><span class="sxs-lookup"><span data-stu-id="ec125-134">For more information about registering store providers for indexing in Outlook 2013 or Outlook 2010, see [About Registering Stores for Indexing](about-registering-stores-for-indexing.md).</span></span>
  
## <a name="indexing-stores"></a><span data-ttu-id="ec125-135">索引存储</span><span class="sxs-lookup"><span data-stu-id="ec125-135">Indexing Stores</span></span>

<span data-ttu-id="ec125-136">MAPI 存储提供程序可以选择允许 MAPI 协议处理程序对存储中的邮件进行爬网和编制索引，或者仅在有要编制索引的消息时向索引器发送通知。</span><span class="sxs-lookup"><span data-stu-id="ec125-136">MAPI store providers can choose to allow the MAPI Protocol Handler to crawl and index messages in the store, or send notifications to the indexer only when there are messages to be indexed.</span></span> <span data-ttu-id="ec125-137">有关基于通知的索引功能详细信息，请参阅关于Notification-Based [存储索引](about-notification-based-store-indexing.md)。</span><span class="sxs-lookup"><span data-stu-id="ec125-137">For more information about notifications-based indexing, see [About Notification-Based Store Indexing](about-notification-based-store-indexing.md).</span></span>
  

