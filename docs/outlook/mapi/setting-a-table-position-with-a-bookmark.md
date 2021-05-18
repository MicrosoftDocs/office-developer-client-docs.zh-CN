---
title: 使用书签设置表格位置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 56ab37f9-5aa6-4e9d-9dc8-b3d95aa19f35
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f0b041cecca92c0ced32631c67c72fcafdab2a16
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422458"
---
# <a name="setting-a-table-position-with-a-bookmark"></a><span data-ttu-id="7ef43-103">使用书签设置表格位置</span><span class="sxs-lookup"><span data-stu-id="7ef43-103">Setting a Table Position with a Bookmark</span></span>

  
  
<span data-ttu-id="7ef43-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ef43-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ef43-105">书签是一种资源，用于指示表格中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="7ef43-105">A bookmark is a resource that indicates a particular location in a table.</span></span> <span data-ttu-id="7ef43-106">通过设置书签，可以在以后返回到一个位置，这是一项可显著提高表操作性能的功能。</span><span class="sxs-lookup"><span data-stu-id="7ef43-106">Setting a bookmark makes it possible to return to a position at a later time, a feature that can significantly improve the performance of table operations.</span></span> <span data-ttu-id="7ef43-107">MAPI 定义三个标准书签：</span><span class="sxs-lookup"><span data-stu-id="7ef43-107">MAPI defines three standard bookmarks:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7ef43-108">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="7ef43-108">BOOKMARK_CURRENT</span></span>  <br/> |<span data-ttu-id="7ef43-109">指向表格中的当前行。</span><span class="sxs-lookup"><span data-stu-id="7ef43-109">Points to the current row in a table.</span></span>  <br/> |
|<span data-ttu-id="7ef43-110">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="7ef43-110">BOOKMARK_BEGINNING</span></span>  <br/> |<span data-ttu-id="7ef43-111">指向表格中的第一行。</span><span class="sxs-lookup"><span data-stu-id="7ef43-111">Points to the first row in a table.</span></span>  <br/> |
|<span data-ttu-id="7ef43-112">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="7ef43-112">BOOKMARK_END</span></span>  <br/> |<span data-ttu-id="7ef43-113">指向表格中的最后一行。</span><span class="sxs-lookup"><span data-stu-id="7ef43-113">Points to the last row in a table.</span></span>  <br/> |
   
<span data-ttu-id="7ef43-114">表实现程序需要支持这些标准书签，并且还可以支持其他书签。</span><span class="sxs-lookup"><span data-stu-id="7ef43-114">Table implementers are required to support these standard bookmarks and can also support others.</span></span> <span data-ttu-id="7ef43-115">但是，由于书签是资源和资源受到限制，因此书签用户应尽快释放它们。</span><span class="sxs-lookup"><span data-stu-id="7ef43-115">However, because bookmarks are resources and resources are limited, bookmark users should free them as soon as possible.</span></span> 
  
 <span data-ttu-id="7ef43-116">**在当前表格位置设置书签**</span><span class="sxs-lookup"><span data-stu-id="7ef43-116">**To set a bookmark at the current table position**</span></span>
  
- <span data-ttu-id="7ef43-117">调用 [IMAPITable：：CreateBookmark](imapitable-createbookmark.md)。</span><span class="sxs-lookup"><span data-stu-id="7ef43-117">Call [IMAPITable::CreateBookmark](imapitable-createbookmark.md).</span></span> <span data-ttu-id="7ef43-118">有时，内存不足，无法分配新书签，从而导致 **CreateBookmark** 返回MAPI_E_UNABLE_TO_COMPLETE错误值。</span><span class="sxs-lookup"><span data-stu-id="7ef43-118">Occasionally there will be insufficient memory available to allocate the new bookmark, causing **CreateBookmark** to return the MAPI_E_UNABLE_TO_COMPLETE error value.</span></span> 
    
 <span data-ttu-id="7ef43-119">**释放书签**</span><span class="sxs-lookup"><span data-stu-id="7ef43-119">**To free a bookmark**</span></span>
  
- <span data-ttu-id="7ef43-120">调用 [IMAPITable：：FreeBookmark](imapitable-freebookmark.md)。</span><span class="sxs-lookup"><span data-stu-id="7ef43-120">Call [IMAPITable::FreeBookmark](imapitable-freebookmark.md).</span></span>
    
 <span data-ttu-id="7ef43-121">**将光标移到书签位置**</span><span class="sxs-lookup"><span data-stu-id="7ef43-121">**To move the cursor to a bookmarked position**</span></span>
  
- <span data-ttu-id="7ef43-122">调用 [IMAPITable：：SeekRow](imapitable-seekrow.md)。</span><span class="sxs-lookup"><span data-stu-id="7ef43-122">Call [IMAPITable::SeekRow](imapitable-seekrow.md).</span></span> <span data-ttu-id="7ef43-123">**SeekRow** 为搜索位置建立BOOKMARK_CURRENT值。</span><span class="sxs-lookup"><span data-stu-id="7ef43-123">**SeekRow** establishes a new value for the BOOKMARK_CURRENT position.</span></span> <span data-ttu-id="7ef43-124">**例如，SeekRow** 可用于将表格从当前位置放置十行或从头开始放置。</span><span class="sxs-lookup"><span data-stu-id="7ef43-124">**SeekRow** can be used, for example, to position a table ten rows from the current position or to start over at the beginning.</span></span> <span data-ttu-id="7ef43-125">客户端或服务提供商可以查找表的当前、开头或结尾，或者与预定义书签关联的任何其他位置。</span><span class="sxs-lookup"><span data-stu-id="7ef43-125">Clients or service providers can seek to the current, beginning, or end of a table, or any other position that is associated with a predefined bookmark.</span></span> <span data-ttu-id="7ef43-126">它们可以向前或向后移动，并且操作限制为指定的行数。</span><span class="sxs-lookup"><span data-stu-id="7ef43-126">They can move in either a forward or backward direction and limit the operation to a specified number of rows.</span></span> <span data-ttu-id="7ef43-127">一般来说，调用方使用 **SeekRow** 搜索的行数不应超过 50 个; [IMAPITable：：SeekRowApprox](imapitable-seekrowapprox.md) 应该与更多的行一起使用。</span><span class="sxs-lookup"><span data-stu-id="7ef43-127">As a rule, callers should seek through no more than 50 rows with **SeekRow**; [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) should be used with larger numbers of rows.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="7ef43-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ef43-128">See also</span></span>



[<span data-ttu-id="7ef43-129">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="7ef43-129">MAPI Tables</span></span>](mapi-tables.md)

