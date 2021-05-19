---
title: 搜索邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9e8d4639-7507-4d98-b56f-a65be369dc40
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7240f49a15fdaea4d1f30dae578d25c3f2c1c0f3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426035"
---
# <a name="searching-a-message-store"></a><span data-ttu-id="2a0d7-103">搜索邮件存储</span><span class="sxs-lookup"><span data-stu-id="2a0d7-103">Searching a message store</span></span>

<span data-ttu-id="2a0d7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2a0d7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2a0d7-105">客户端应用程序可以搜索一个或多个文件夹，查找与搜索条件匹配的邮件。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-105">Client applications can search through one or more folders looking for messages that match search criteria.</span></span> <span data-ttu-id="2a0d7-106">最直接的搜索技术涉及应用限制来定义条件，将结果放入搜索结果文件夹，该文件夹是为此搜索或之前的搜索显式创建的。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-106">The most straightforward search technique involves applying a restriction to define criteria and placing the results into a search-results folder, created explicitly for this search or for a prior search.</span></span> <span data-ttu-id="2a0d7-107">并非所有邮件存储都支持此技术。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-107">Not all message stores support this technique.</span></span> 

<span data-ttu-id="2a0d7-108">若要确定你使用的邮件存储是否支持使用搜索结果文件夹，请调用 [其 IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索 **PR \_ STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-108">To determine whether or not the message store you are using supports using search-results folders, call its [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span> <span data-ttu-id="2a0d7-109">如果STORE_SEARCH_OK，则支持搜索。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-109">If the STORE_SEARCH_OK flag is set, searching is supported.</span></span> <span data-ttu-id="2a0d7-110">如果未设置，则需要其他方法，如手动检查目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-110">If it is not set, you'll need an alternate approach such as manually inspecting the target folders.</span></span>
  
### <a name="to-search-one-or-more-folders-in-a-message-store"></a><span data-ttu-id="2a0d7-111">搜索邮件存储中的一个或多个文件夹</span><span class="sxs-lookup"><span data-stu-id="2a0d7-111">To search one or more folders in a message store</span></span>
  
1. <span data-ttu-id="2a0d7-112">如果你有上一次搜索中的搜索结果文件夹，请跳到步骤 2。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-112">If you have a search-results folder from a previous search, skip to step 2.</span></span> <span data-ttu-id="2a0d7-113">否则，创建搜索结果文件夹：</span><span class="sxs-lookup"><span data-stu-id="2a0d7-113">Otherwise, to create a search-results folder:</span></span>
    
    1. <span data-ttu-id="2a0d7-114">通过调用邮件存储的[IMAPIProp：：GetProps](imapiprop-getprops.md)方法并请求 PR_FINDER_ENTRYID ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) ，检索搜索结果根文件夹的条目标识符。 </span><span class="sxs-lookup"><span data-stu-id="2a0d7-114">Retrieve the entry identifier for the search-results root folder by calling the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method and requesting **PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)).</span></span>
        
    2. <span data-ttu-id="2a0d7-115">调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 以打开由 PR_FINDER_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-115">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) to open the folder represented by PR_FINDER_ENTRYID.</span></span> 
        
    3. <span data-ttu-id="2a0d7-116">调用文件夹的 [IMAPIFolder：：CreateFolder](imapifolder-createfolder.md) 方法以创建一个设置有FOLDER_SEARCH文件夹。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-116">Call the folder's [IMAPIFolder::CreateFolder](imapifolder-createfolder.md) method to create a search-results folder with the FOLDER_SEARCH flag set.</span></span> 
    
2. <span data-ttu-id="2a0d7-117">构建用于保留搜索条件的限制。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-117">Build a restriction to hold your search criteria.</span></span> 
    
3. <span data-ttu-id="2a0d7-118">创建表示要搜索的文件夹的条目标识符数组。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-118">Create an array of entry identifiers that represent the folders to search.</span></span> <span data-ttu-id="2a0d7-119">如果之前已使用搜索结果文件夹，并且您希望搜索相同的文件夹，则无需执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-119">This step is unnecessary if the search-results folder has been used before and you want to search the same folders.</span></span>
    
4. <span data-ttu-id="2a0d7-120">调用搜索结果文件夹 [的 IMAPIContainer：：SetSearchCriteria](imapicontainer-setsearchcriteria.md) 方法，将  _lpContainerList_ 指向条目标识符数组，  _将 lpRestriction_ 指向限制。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-120">Call the search-results folder's [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method, pointing  _lpContainerList_ to the entry identifier array and  _lpRestriction_ to the restriction.</span></span> 
    
5. <span data-ttu-id="2a0d7-121">如果已使用邮件存储注册搜索完成通知，请等待通知到达。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-121">If you have registered for search complete notifications with the message store, wait for the notification to arrive.</span></span>
    
6. <span data-ttu-id="2a0d7-122">通过调用搜索结果文件夹的 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法访问其内容表来查看搜索结果。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-122">View the results of the search by calling the search-results folder's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to access its contents table.</span></span> 
    
7. <span data-ttu-id="2a0d7-123">调用内容表的 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法来检索满足搜索条件的消息。</span><span class="sxs-lookup"><span data-stu-id="2a0d7-123">Call the contents table's [IMAPITable::QueryRows](imapitable-queryrows.md) method to retrieve the messages that satisfy the search criteria.</span></span> 
    

