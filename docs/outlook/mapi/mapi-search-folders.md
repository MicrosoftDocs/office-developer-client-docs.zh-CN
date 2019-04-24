---
title: MAPI 搜索文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 36c14d91-77f7-43a3-8d87-d50bcc21fad7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c1d7f67458852319587d98831d031b2c3a131871
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357671"
---
# <a name="mapi-search-folders"></a><span data-ttu-id="166d5-103">MAPI 搜索文件夹</span><span class="sxs-lookup"><span data-stu-id="166d5-103">MAPI Search Folders</span></span>

  
  
<span data-ttu-id="166d5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="166d5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="166d5-105">搜索结果文件夹保留了指向常规文件夹中的邮件的链接, 而不是实际的邮件。</span><span class="sxs-lookup"><span data-stu-id="166d5-105">A search-results folder holds links to messages in generic folders rather than the actual messages.</span></span> <span data-ttu-id="166d5-106">客户端通过调用[IMAPIFolder:: CreateFolder](imapifolder-createfolder.md)方法并将 FOLDER_SEARCH 作为_ulFolderType_参数来创建搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="166d5-106">Clients create a search-results folder by calling the [IMAPIFolder::CreateFolder](imapifolder-createfolder.md) method with FOLDER_SEARCH as the  _ulFolderType_ parameter.</span></span> <span data-ttu-id="166d5-107">客户端通过设置和应用搜索条件来填充搜索结果文件夹—使用特定特征筛选出邮件的规则。</span><span class="sxs-lookup"><span data-stu-id="166d5-107">Clients fill a search-results folder by setting up and applying search criteria — rules that filter out messages with particular characteristics.</span></span> <span data-ttu-id="166d5-108">使用[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法设置搜索条件。</span><span class="sxs-lookup"><span data-stu-id="166d5-108">Search criteria are set up with the [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method.</span></span> <span data-ttu-id="166d5-109">客户端生成一个或多个[SRestriction](srestriction.md)结构以表示要应用的搜索条件并将其传递给**SetSearchCriteria**。</span><span class="sxs-lookup"><span data-stu-id="166d5-109">Clients build one or more [SRestriction](srestriction.md) structures to represent the search criteria to be applied and pass them to **SetSearchCriteria**.</span></span> <span data-ttu-id="166d5-110">**SetSearchCriteria**还指定指示搜索域的文件夹列表和一组用于控制如何执行搜索的标志。</span><span class="sxs-lookup"><span data-stu-id="166d5-110">**SetSearchCriteria** also specifies a list of folders that indicate the search domain and a set of flags that control how the search is performed.</span></span> 
  
 <span data-ttu-id="166d5-111">**SetSearchCriteria**标识与指定的限制匹配的邮件。</span><span class="sxs-lookup"><span data-stu-id="166d5-111">**SetSearchCriteria** identifies the messages that match the specified restriction.</span></span> <span data-ttu-id="166d5-112">选定的邮件 (满足条件的邮件) 将显示为搜索结果文件夹中的链接。</span><span class="sxs-lookup"><span data-stu-id="166d5-112">The selected messages (the ones that satisfy the criteria) are displayed as links in the search-results folder.</span></span> <span data-ttu-id="166d5-113">当客户端调用[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法访问搜索结果文件夹的内容表时, 所选的邮件将显示在表中。</span><span class="sxs-lookup"><span data-stu-id="166d5-113">When the client calls the [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to access the contents table of the search-results folder, the selected messages are displayed in the table.</span></span> <span data-ttu-id="166d5-114">搜索的内容表格-结果文件夹包含与通用文件夹的内容表格相同的列。</span><span class="sxs-lookup"><span data-stu-id="166d5-114">Contents tables for search-results folders contain the same columns as contents tables for generic folders.</span></span> <span data-ttu-id="166d5-115">但是, 对于搜索结果文件夹, **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性指定链接的邮件所在的文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="166d5-115">However, for search-results folders, the **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) property specifies the entry identifier of the folder where the linked message resides.</span></span> <span data-ttu-id="166d5-116">搜索-结果文件夹不被视为父文件夹。</span><span class="sxs-lookup"><span data-stu-id="166d5-116">Search-results folders are not considered parent folders.</span></span>
  
<span data-ttu-id="166d5-117">搜索-结果文件夹具有以下限制:</span><span class="sxs-lookup"><span data-stu-id="166d5-117">Search-results folders have the following limits:</span></span>
  
- <span data-ttu-id="166d5-118">可以修改搜索结果文件夹内容的唯一方法是通过调用**SetSearchCriteria**。</span><span class="sxs-lookup"><span data-stu-id="166d5-118">The only way that the contents of a search-results folder can be modified is through a call to **SetSearchCriteria**.</span></span> <span data-ttu-id="166d5-119">有关实现**SetSearchCriteria**的详细信息, 请参阅知识库文章[260322: 如何使用 SetSearchCriteria 方法搜索文件夹](https://go.microsoft.com/fwlink/?LinkId=123603)。</span><span class="sxs-lookup"><span data-stu-id="166d5-119">For more information about the implementation of **SetSearchCriteria**, see Knowledge Base article [260322: How To Search Folders with the SetSearchCriteria Method](https://go.microsoft.com/fwlink/?LinkId=123603).</span></span>
    
- <span data-ttu-id="166d5-120">无法将邮件移动或复制到搜索结果文件夹中。</span><span class="sxs-lookup"><span data-stu-id="166d5-120">Messages cannot be moved or copied into search-results folders.</span></span>
    
- <span data-ttu-id="166d5-121">搜索-结果文件夹不能包含子文件夹。</span><span class="sxs-lookup"><span data-stu-id="166d5-121">Search-results folders cannot contain subfolders.</span></span> 
    
- <span data-ttu-id="166d5-122">客户端无法将搜索结果文件夹设为搜索的主题。</span><span class="sxs-lookup"><span data-stu-id="166d5-122">Clients cannot make a search-results folder the subject of a search.</span></span>
    
<span data-ttu-id="166d5-123">但是, 可以修改搜索结果文件夹的属性并使用它删除邮件。</span><span class="sxs-lookup"><span data-stu-id="166d5-123">It is possible, however, to modify the properties of a search-results folder and use it to delete a message.</span></span> <span data-ttu-id="166d5-124">从搜索结果文件夹中删除邮件时, 该邮件实际上会从实际文件夹中删除。</span><span class="sxs-lookup"><span data-stu-id="166d5-124">When a message is deleted from a search-results folder, it is actually deleted from the real folder.</span></span> <span data-ttu-id="166d5-125">但是, 删除搜索结果文件夹本身对内部的邮件没有影响;它们保留在其通用文件夹中。</span><span class="sxs-lookup"><span data-stu-id="166d5-125">However, deleting the search-results folder itself has no impact on the messages inside; they remain in their generic folders.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="166d5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="166d5-126">See also</span></span>



[<span data-ttu-id="166d5-127">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="166d5-127">MAPI Folders</span></span>](mapi-folders.md)

