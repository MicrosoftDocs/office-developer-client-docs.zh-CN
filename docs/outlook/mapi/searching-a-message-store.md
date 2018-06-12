---
title: 搜索的消息存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9e8d4639-7507-4d98-b56f-a65be369dc40
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 90ed7da43d7f9e5e8b5f3024f1eee99a2d7a2b5c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778717"
---
# <a name="searching-a-message-store"></a><span data-ttu-id="4877f-103">搜索的消息存储</span><span class="sxs-lookup"><span data-stu-id="4877f-103">Searching a message store</span></span>

<span data-ttu-id="4877f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4877f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4877f-105">客户端应用程序可以搜索通过查找与搜索条件匹配的消息的一个或多个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4877f-105">Client applications can search through one or more folders looking for messages that match search criteria.</span></span> <span data-ttu-id="4877f-106">最简单的搜索技术涉及应用定义条件限制，并将结果放到搜索结果文件夹中，此搜索或以前搜索明确创建。</span><span class="sxs-lookup"><span data-stu-id="4877f-106">The most straightforward search technique involves applying a restriction to define criteria and placing the results into a search-results folder, created explicitly for this search or for a prior search.</span></span> <span data-ttu-id="4877f-107">并非所有的消息存储库支持这种技术。</span><span class="sxs-lookup"><span data-stu-id="4877f-107">Not all message stores support this technique.</span></span> 

<span data-ttu-id="4877f-108">若要确定是否消息存储库使用支持使用搜索结果文件夹，调用来检索其[IMAPIProp::GetProps](imapiprop-getprops.md)方法**PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="4877f-108">To determine whether or not the message store you are using supports using search-results folders, call its [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span> <span data-ttu-id="4877f-109">如果设置了 STORE_SEARCH_OK 标志，搜索则支持。</span><span class="sxs-lookup"><span data-stu-id="4877f-109">If the STORE_SEARCH_OK flag is set, searching is supported.</span></span> <span data-ttu-id="4877f-110">如果它未设置，您将需要手动检查的目标文件夹如另一种方法。</span><span class="sxs-lookup"><span data-stu-id="4877f-110">If it is not set, you'll need an alternate approach such as manually inspecting the target folders.</span></span>
  
### <a name="to-search-one-or-more-folders-in-a-message-store"></a><span data-ttu-id="4877f-111">消息存储区中搜索一个或多个文件夹</span><span class="sxs-lookup"><span data-stu-id="4877f-111">To search one or more folders in a message store</span></span>
  
1. <span data-ttu-id="4877f-112">如果您有从前一个搜索的搜索结果文件夹，请跳到步骤 2。</span><span class="sxs-lookup"><span data-stu-id="4877f-112">If you have a search-results folder from a previous search, skip to step 2.</span></span> <span data-ttu-id="4877f-113">否则为若要创建一个搜索结果文件夹：</span><span class="sxs-lookup"><span data-stu-id="4877f-113">Otherwise, to create a search-results folder:</span></span>
    
    1. <span data-ttu-id="4877f-114">通过调用的消息存储[IMAPIProp::GetProps](imapiprop-getprops.md)方法并请求**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 检索搜索结果的根文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4877f-114">Retrieve the entry identifier for the search-results root folder by calling the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method and requesting **PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)).</span></span>
        
    2. <span data-ttu-id="4877f-115">调用[IMsgStore::OpenEntry](imsgstore-openentry.md)以打开由 PR_FINDER_ENTRYID 文件夹。</span><span class="sxs-lookup"><span data-stu-id="4877f-115">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) to open the folder represented by PR_FINDER_ENTRYID.</span></span> 
        
    3. <span data-ttu-id="4877f-116">调用该文件夹的[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)方法，以创建具有设置了 FOLDER_SEARCH 标志的搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="4877f-116">Call the folder's [IMAPIFolder::CreateFolder](imapifolder-createfolder.md) method to create a search-results folder with the FOLDER_SEARCH flag set.</span></span> 
    
2. <span data-ttu-id="4877f-117">生成用于存放您的搜索条件的限制。</span><span class="sxs-lookup"><span data-stu-id="4877f-117">Build a restriction to hold your search criteria.</span></span> 
    
3. <span data-ttu-id="4877f-118">创建一个表示要搜索的文件夹的项标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="4877f-118">Create an array of entry identifiers that represent the folders to search.</span></span> <span data-ttu-id="4877f-119">此步骤是不必要的如果已使用搜索结果文件夹之前，并且您希望搜索相同的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4877f-119">This step is unnecessary if the search-results folder has been used before and you want to search the same folders.</span></span>
    
4. <span data-ttu-id="4877f-120">调用的搜索结果文件夹[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法， _lpContainerList_指向条目标识符数组和_lpRestriction_限制。</span><span class="sxs-lookup"><span data-stu-id="4877f-120">Call the search-results folder's [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method, pointing  _lpContainerList_ to the entry identifier array and  _lpRestriction_ to the restriction.</span></span> 
    
5. <span data-ttu-id="4877f-121">如果您的消息存储与搜索完成通知注册，等待要进入的通知。</span><span class="sxs-lookup"><span data-stu-id="4877f-121">If you have registered for search complete notifications with the message store, wait for the notification to arrive.</span></span>
    
6. <span data-ttu-id="4877f-122">通过调用文件夹的[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法访问其内容表的搜索结果中查看搜索结果。</span><span class="sxs-lookup"><span data-stu-id="4877f-122">View the results of the search by calling the search-results folder's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to access its contents table.</span></span> 
    
7. <span data-ttu-id="4877f-123">调用内容表的[IMAPITable::QueryRows](imapitable-queryrows.md)方法，以检索满足搜索条件的邮件。</span><span class="sxs-lookup"><span data-stu-id="4877f-123">Call the contents table's [IMAPITable::QueryRows](imapitable-queryrows.md) method to retrieve the messages that satisfy the search criteria.</span></span> 
    

