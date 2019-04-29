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
# <a name="searching-a-message-store"></a><span data-ttu-id="84ffd-103">搜索邮件存储</span><span class="sxs-lookup"><span data-stu-id="84ffd-103">Searching a message store</span></span>

<span data-ttu-id="84ffd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="84ffd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="84ffd-105">客户端应用程序可以在一个或多个文件夹中搜索, 以查找与搜索条件相匹配的邮件。</span><span class="sxs-lookup"><span data-stu-id="84ffd-105">Client applications can search through one or more folders looking for messages that match search criteria.</span></span> <span data-ttu-id="84ffd-106">最简单的搜索技术涉及到应用限制以定义条件并将结果放入搜索结果文件夹中 (为此搜索显式创建) 或之前的搜索。</span><span class="sxs-lookup"><span data-stu-id="84ffd-106">The most straightforward search technique involves applying a restriction to define criteria and placing the results into a search-results folder, created explicitly for this search or for a prior search.</span></span> <span data-ttu-id="84ffd-107">并非所有邮件存储区都支持此技术。</span><span class="sxs-lookup"><span data-stu-id="84ffd-107">Not all message stores support this technique.</span></span> 

<span data-ttu-id="84ffd-108">若要确定您使用的邮件存储库是否支持使用搜索结果文件夹, 请调用其[IMAPIProp:: GetProps](imapiprop-getprops.md)方法检索 " **\_PR STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))" 属性。</span><span class="sxs-lookup"><span data-stu-id="84ffd-108">To determine whether or not the message store you are using supports using search-results folders, call its [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span> <span data-ttu-id="84ffd-109">如果设置了 STORE_SEARCH_OK 标志, 则支持搜索。</span><span class="sxs-lookup"><span data-stu-id="84ffd-109">If the STORE_SEARCH_OK flag is set, searching is supported.</span></span> <span data-ttu-id="84ffd-110">如果未设置, 则需要另一种方法, 如手动检查目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="84ffd-110">If it is not set, you'll need an alternate approach such as manually inspecting the target folders.</span></span>
  
### <a name="to-search-one-or-more-folders-in-a-message-store"></a><span data-ttu-id="84ffd-111">搜索邮件存储区中的一个或多个文件夹</span><span class="sxs-lookup"><span data-stu-id="84ffd-111">To search one or more folders in a message store</span></span>
  
1. <span data-ttu-id="84ffd-112">如果您的搜索结果文件夹来自以前的搜索, 请跳至步骤2。</span><span class="sxs-lookup"><span data-stu-id="84ffd-112">If you have a search-results folder from a previous search, skip to step 2.</span></span> <span data-ttu-id="84ffd-113">否则, 若要创建搜索结果文件夹, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="84ffd-113">Otherwise, to create a search-results folder:</span></span>
    
    1. <span data-ttu-id="84ffd-114">通过调用邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法和请求**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)), 检索搜索结果根文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="84ffd-114">Retrieve the entry identifier for the search-results root folder by calling the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method and requesting **PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)).</span></span>
        
    2. <span data-ttu-id="84ffd-115">调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)以打开 PR_FINDER_ENTRYID 所代表的文件夹。</span><span class="sxs-lookup"><span data-stu-id="84ffd-115">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) to open the folder represented by PR_FINDER_ENTRYID.</span></span> 
        
    3. <span data-ttu-id="84ffd-116">调用文件夹的[IMAPIFolder:: CreateFolder](imapifolder-createfolder.md)方法来创建 FOLDER_SEARCH 标志集的搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="84ffd-116">Call the folder's [IMAPIFolder::CreateFolder](imapifolder-createfolder.md) method to create a search-results folder with the FOLDER_SEARCH flag set.</span></span> 
    
2. <span data-ttu-id="84ffd-117">建立限制以保留你的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="84ffd-117">Build a restriction to hold your search criteria.</span></span> 
    
3. <span data-ttu-id="84ffd-118">创建表示要搜索的文件夹的项标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="84ffd-118">Create an array of entry identifiers that represent the folders to search.</span></span> <span data-ttu-id="84ffd-119">如果以前使用过搜索结果文件夹, 并且您希望在相同的文件夹中搜索, 则不需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="84ffd-119">This step is unnecessary if the search-results folder has been used before and you want to search the same folders.</span></span>
    
4. <span data-ttu-id="84ffd-120">调用搜索结果文件夹的[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法, 将_lpContainerList_指向条目标识符数组, 并_lpRestriction_到限制。</span><span class="sxs-lookup"><span data-stu-id="84ffd-120">Call the search-results folder's [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method, pointing  _lpContainerList_ to the entry identifier array and  _lpRestriction_ to the restriction.</span></span> 
    
5. <span data-ttu-id="84ffd-121">如果已使用邮件存储区注册了搜索完成通知, 请等待通知到达。</span><span class="sxs-lookup"><span data-stu-id="84ffd-121">If you have registered for search complete notifications with the message store, wait for the notification to arrive.</span></span>
    
6. <span data-ttu-id="84ffd-122">通过调用搜索结果文件夹的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法访问其内容表, 查看搜索结果。</span><span class="sxs-lookup"><span data-stu-id="84ffd-122">View the results of the search by calling the search-results folder's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to access its contents table.</span></span> 
    
7. <span data-ttu-id="84ffd-123">调用内容表的[IMAPITable:: QueryRows](imapitable-queryrows.md)方法以检索满足搜索条件的邮件。</span><span class="sxs-lookup"><span data-stu-id="84ffd-123">Call the contents table's [IMAPITable::QueryRows](imapitable-queryrows.md) method to retrieve the messages that satisfy the search criteria.</span></span> 
    

