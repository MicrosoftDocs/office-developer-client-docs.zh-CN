---
title: 通过书签设置表位置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 56ab37f9-5aa6-4e9d-9dc8-b3d95aa19f35
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f43e3a7e3376cb437620204a29aed9fb732d3427
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564092"
---
# <a name="setting-a-table-position-with-a-bookmark"></a><span data-ttu-id="9d2da-103">通过书签设置表位置</span><span class="sxs-lookup"><span data-stu-id="9d2da-103">Setting a Table Position with a Bookmark</span></span>

  
  
<span data-ttu-id="9d2da-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9d2da-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9d2da-105">书签是指示表中的特定位置的资源。</span><span class="sxs-lookup"><span data-stu-id="9d2da-105">A bookmark is a resource that indicates a particular location in a table.</span></span> <span data-ttu-id="9d2da-106">设置书签使得以后，一种功能，可以显著提高性能的表操作返回的位置。</span><span class="sxs-lookup"><span data-stu-id="9d2da-106">Setting a bookmark makes it possible to return to a position at a later time, a feature that can significantly improve the performance of table operations.</span></span> <span data-ttu-id="9d2da-107">MAPI 定义三个标准书签：</span><span class="sxs-lookup"><span data-stu-id="9d2da-107">MAPI defines three standard bookmarks:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9d2da-108">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="9d2da-108">BOOKMARK_CURRENT</span></span>  <br/> |<span data-ttu-id="9d2da-109">指向表中的当前行。</span><span class="sxs-lookup"><span data-stu-id="9d2da-109">Points to the current row in a table.</span></span>  <br/> |
|<span data-ttu-id="9d2da-110">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="9d2da-110">BOOKMARK_BEGINNING</span></span>  <br/> |<span data-ttu-id="9d2da-111">指向表中的第一行。</span><span class="sxs-lookup"><span data-stu-id="9d2da-111">Points to the first row in a table.</span></span>  <br/> |
|<span data-ttu-id="9d2da-112">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="9d2da-112">BOOKMARK_END</span></span>  <br/> |<span data-ttu-id="9d2da-113">点的最后一个表格中的行。</span><span class="sxs-lookup"><span data-stu-id="9d2da-113">Points to the last row in a table.</span></span>  <br/> |
   
<span data-ttu-id="9d2da-114">表实施支持这些标准书签所需，而且还可以支持其他人。</span><span class="sxs-lookup"><span data-stu-id="9d2da-114">Table implementers are required to support these standard bookmarks and can also support others.</span></span> <span data-ttu-id="9d2da-115">但是，因为资源是有限书签是资源以及书签用户应释放它们尽快。</span><span class="sxs-lookup"><span data-stu-id="9d2da-115">However, because bookmarks are resources and resources are limited, bookmark users should free them as soon as possible.</span></span> 
  
 <span data-ttu-id="9d2da-116">**在表当前位置设置书签**</span><span class="sxs-lookup"><span data-stu-id="9d2da-116">**To set a bookmark at the current table position**</span></span>
  
- <span data-ttu-id="9d2da-117">调用[IMAPITable::CreateBookmark](imapitable-createbookmark.md)。</span><span class="sxs-lookup"><span data-stu-id="9d2da-117">Call [IMAPITable::CreateBookmark](imapitable-createbookmark.md).</span></span> <span data-ttu-id="9d2da-118">偶尔会有内存不足，无法分配新书签，导致**CreateBookmark**返回 MAPI_E_UNABLE_TO_COMPLETE 错误值。</span><span class="sxs-lookup"><span data-stu-id="9d2da-118">Occasionally there will be insufficient memory available to allocate the new bookmark, causing **CreateBookmark** to return the MAPI_E_UNABLE_TO_COMPLETE error value.</span></span> 
    
 <span data-ttu-id="9d2da-119">**以释放书签**</span><span class="sxs-lookup"><span data-stu-id="9d2da-119">**To free a bookmark**</span></span>
  
- <span data-ttu-id="9d2da-120">调用[IMAPITable::FreeBookmark](imapitable-freebookmark.md)。</span><span class="sxs-lookup"><span data-stu-id="9d2da-120">Call [IMAPITable::FreeBookmark](imapitable-freebookmark.md).</span></span>
    
 <span data-ttu-id="9d2da-121">**若要将光标移到的书签的位置**</span><span class="sxs-lookup"><span data-stu-id="9d2da-121">**To move the cursor to a bookmarked position**</span></span>
  
- <span data-ttu-id="9d2da-122">调用[IMAPITable::SeekRow](imapitable-seekrow.md)。</span><span class="sxs-lookup"><span data-stu-id="9d2da-122">Call [IMAPITable::SeekRow](imapitable-seekrow.md).</span></span> <span data-ttu-id="9d2da-123">**SeekRow**建立 BOOKMARK_CURRENT 位置的新值。</span><span class="sxs-lookup"><span data-stu-id="9d2da-123">**SeekRow** establishes a new value for the BOOKMARK_CURRENT position.</span></span> <span data-ttu-id="9d2da-124">**SeekRow**可，例如，若要从当前位置定位表 10 行或重新开始开头。</span><span class="sxs-lookup"><span data-stu-id="9d2da-124">**SeekRow** can be used, for example, to position a table ten rows from the current position or to start over at the beginning.</span></span> <span data-ttu-id="9d2da-125">客户端或服务提供商可以查找到当前，从开始，或结束的表或任何其他相关联的预定义的书签的位置。</span><span class="sxs-lookup"><span data-stu-id="9d2da-125">Clients or service providers can seek to the current, beginning, or end of a table, or any other position that is associated with a predefined bookmark.</span></span> <span data-ttu-id="9d2da-126">它们可以移动中向前或向后和限制操作到指定的行数。</span><span class="sxs-lookup"><span data-stu-id="9d2da-126">They can move in either a forward or backward direction and limit the operation to a specified number of rows.</span></span> <span data-ttu-id="9d2da-127">一般来说，呼叫者应寻求通过与**SeekRow**; 不能超过 50 行[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)应与更大的行数。</span><span class="sxs-lookup"><span data-stu-id="9d2da-127">As a rule, callers should seek through no more than 50 rows with **SeekRow**; [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) should be used with larger numbers of rows.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="9d2da-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d2da-128">See also</span></span>



[<span data-ttu-id="9d2da-129">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="9d2da-129">MAPI Tables</span></span>](mapi-tables.md)

