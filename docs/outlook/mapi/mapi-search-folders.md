---
title: MAPI 搜索文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 36c14d91-77f7-43a3-8d87-d50bcc21fad7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e74767f4b3a19442beac5f9c9ac375286bb47c81
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776312"
---
# <a name="mapi-search-folders"></a><span data-ttu-id="cfe5d-103">MAPI 搜索文件夹</span><span class="sxs-lookup"><span data-stu-id="cfe5d-103">MAPI Search Folders</span></span>

  
  
<span data-ttu-id="cfe5d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cfe5d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cfe5d-105">搜索结果文件夹包含链接到泛型文件夹中的邮件，而不是实际的邮件。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-105">A search-results folder holds links to messages in generic folders rather than the actual messages.</span></span> <span data-ttu-id="cfe5d-106">客户端通过调用带 FOLDER_SEARCH 作为_ulFolderType_参数的[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)方法创建一个搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-106">Clients create a search-results folder by calling the [IMAPIFolder::CreateFolder](imapifolder-createfolder.md) method with FOLDER_SEARCH as the  _ulFolderType_ parameter.</span></span> <span data-ttu-id="cfe5d-107">客户端通过设置并应用搜索条件填充的搜索结果文件夹 — 筛选出与特定的特征的邮件的规则。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-107">Clients fill a search-results folder by setting up and applying search criteria — rules that filter out messages with particular characteristics.</span></span> <span data-ttu-id="cfe5d-108">使用[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法设置搜索条件。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-108">Search criteria are set up with the [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method.</span></span> <span data-ttu-id="cfe5d-109">客户端构建表示搜索条件以应用并将它们传递给**SetSearchCriteria**的一个或多个[SRestriction](srestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-109">Clients build one or more [SRestriction](srestriction.md) structures to represent the search criteria to be applied and pass them to **SetSearchCriteria**.</span></span> <span data-ttu-id="cfe5d-110">**SetSearchCriteria**还指定指示搜索域的文件夹的列表和一组标志将如何执行搜索该控件。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-110">**SetSearchCriteria** also specifies a list of folders that indicate the search domain and a set of flags that control how the search is performed.</span></span> 
  
 <span data-ttu-id="cfe5d-111">**SetSearchCriteria**标识符合指定的限制的邮件。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-111">**SetSearchCriteria** identifies the messages that match the specified restriction.</span></span> <span data-ttu-id="cfe5d-112">所选的邮件 （满足条件的那些） 显示为搜索结果文件夹中的链接。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-112">The selected messages (the ones that satisfy the criteria) are displayed as links in the search-results folder.</span></span> <span data-ttu-id="cfe5d-113">当客户端调用[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法来访问内容表中的搜索结果文件夹时，表中显示选定的邮件。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-113">When the client calls the [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to access the contents table of the search-results folder, the selected messages are displayed in the table.</span></span> <span data-ttu-id="cfe5d-114">为搜索结果文件夹内容表包含相同的泛型文件夹内容表格列。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-114">Contents tables for search-results folders contain the same columns as contents tables for generic folders.</span></span> <span data-ttu-id="cfe5d-115">但是，对于搜索结果文件夹， **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性指定链接的消息所在的文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-115">However, for search-results folders, the **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) property specifies the entry identifier of the folder where the linked message resides.</span></span> <span data-ttu-id="cfe5d-116">搜索结果文件夹不被认为是父文件夹。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-116">Search-results folders are not considered parent folders.</span></span>
  
<span data-ttu-id="cfe5d-117">搜索结果文件夹具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="cfe5d-117">Search-results folders have the following limits:</span></span>
  
- <span data-ttu-id="cfe5d-118">可以修改搜索结果文件夹的内容的唯一方法是通过调用**SetSearchCriteria**。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-118">The only way that the contents of a search-results folder can be modified is through a call to **SetSearchCriteria**.</span></span> <span data-ttu-id="cfe5d-119">有关**SetSearchCriteria**实现的详细信息，请参阅知识库文章[260322： 如何对搜索文件夹与 SetSearchCriteria 方法](http://go.microsoft.com/fwlink/?LinkId=123603)。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-119">For more information about the implementation of **SetSearchCriteria**, see Knowledge Base article [260322: How To Search Folders with the SetSearchCriteria Method](http://go.microsoft.com/fwlink/?LinkId=123603).</span></span>
    
- <span data-ttu-id="cfe5d-120">无法移动或复制到文件夹中搜索结果的消息。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-120">Messages cannot be moved or copied into search-results folders.</span></span>
    
- <span data-ttu-id="cfe5d-121">搜索结果文件夹不能包含子文件夹。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-121">Search-results folders cannot contain subfolders.</span></span> 
    
- <span data-ttu-id="cfe5d-122">客户端不能进行的搜索结果文件夹搜索的主题。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-122">Clients cannot make a search-results folder the subject of a search.</span></span>
    
<span data-ttu-id="cfe5d-123">它是可能的但是，修改搜索结果文件夹的属性和使用它来删除一条消息。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-123">It is possible, however, to modify the properties of a search-results folder and use it to delete a message.</span></span> <span data-ttu-id="cfe5d-124">从搜索结果文件夹中删除一条消息后，它是实际删除从实际的文件夹。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-124">When a message is deleted from a search-results folder, it is actually deleted from the real folder.</span></span> <span data-ttu-id="cfe5d-125">但是，删除搜索结果文件夹本身时不会影响; 内的消息它们保留在其泛型文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cfe5d-125">However, deleting the search-results folder itself has no impact on the messages inside; they remain in their generic folders.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cfe5d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfe5d-126">See also</span></span>



[<span data-ttu-id="cfe5d-127">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="cfe5d-127">MAPI Folders</span></span>](mapi-folders.md)

