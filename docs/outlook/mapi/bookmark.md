---
title: 书签
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.BOOKMARK
api_type:
- COM
ms.assetid: 678bdc52-3404-48b2-9154-64ce2a941555
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 069cb41ceac70a2eaaa08440e43745605890f071
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418132"
---
# <a name="bookmark"></a><span data-ttu-id="d983b-103">书签</span><span class="sxs-lookup"><span data-stu-id="d983b-103">BOOKMARK</span></span>

  
  
<span data-ttu-id="d983b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d983b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d983b-105">定义书签数据以记住表格中的位置。</span><span class="sxs-lookup"><span data-stu-id="d983b-105">Defines bookmarks data for remembering a position in a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d983b-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d983b-106">Header file:</span></span>  <br/> |<span data-ttu-id="d983b-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d983b-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="d983b-108">相关方法：</span><span class="sxs-lookup"><span data-stu-id="d983b-108">Related methods:</span></span>  <br/> |<span data-ttu-id="d983b-109">[IMAPITable：：CreateBookmark](imapitable-createbookmark.md)[IMAPITable：：FreeBookmark](imapitable-freebookmark.md)</span><span class="sxs-lookup"><span data-stu-id="d983b-109">[IMAPITable::CreateBookmark](imapitable-createbookmark.md)[IMAPITable::FreeBookmark](imapitable-freebookmark.md)</span></span> <br/> |
   
```cpp
typedef ULONG_PTR BOOKMARK;
```

## <a name="remarks"></a><span data-ttu-id="d983b-110">备注</span><span class="sxs-lookup"><span data-stu-id="d983b-110">Remarks</span></span>

<span data-ttu-id="d983b-111">MAPI 定义三个书签，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d983b-111">MAPI defines three bookmarks, listed as follows:</span></span>
  
<span data-ttu-id="d983b-112">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="d983b-112">BOOKMARK_BEGINNING</span></span> 
  
> <span data-ttu-id="d983b-113">记住表的起始位置。</span><span class="sxs-lookup"><span data-stu-id="d983b-113">Remembers the starting position of the table.</span></span> 
    
<span data-ttu-id="d983b-114">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="d983b-114">BOOKMARK_CURRENT</span></span> 
  
> <span data-ttu-id="d983b-115">记住表的当前位置。</span><span class="sxs-lookup"><span data-stu-id="d983b-115">Remembers the current position of the table.</span></span>
    
<span data-ttu-id="d983b-116">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="d983b-116">BOOKMARK_END</span></span> 
  
> <span data-ttu-id="d983b-117">记住表的结束位置。</span><span class="sxs-lookup"><span data-stu-id="d983b-117">Remembers the ending position of the table.</span></span>
    
<span data-ttu-id="d983b-118">客户端可以创建其他书签来记住其他表格位置。</span><span class="sxs-lookup"><span data-stu-id="d983b-118">Clients can create other bookmarks for remembering other table positions.</span></span> <span data-ttu-id="d983b-119">书签仅在表格打开时有效。</span><span class="sxs-lookup"><span data-stu-id="d983b-119">Bookmarks are valid only when the table is open.</span></span> <span data-ttu-id="d983b-120">在关闭关联表之前，客户端必须释放已创建的任何书签。</span><span class="sxs-lookup"><span data-stu-id="d983b-120">Clients must free any bookmarks that they have created before closing the associated table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d983b-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d983b-121">See also</span></span>



[<span data-ttu-id="d983b-122">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="d983b-122">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="d983b-123">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="d983b-123">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
  
[<span data-ttu-id="d983b-124">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="d983b-124">IMAPITable::FreeBookmark</span></span>](imapitable-freebookmark.md)
  
[<span data-ttu-id="d983b-125">IMAPITable::SeekRow</span><span class="sxs-lookup"><span data-stu-id="d983b-125">IMAPITable::SeekRow</span></span>](imapitable-seekrow.md)


[<span data-ttu-id="d983b-126">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="d983b-126">MAPI Data Types</span></span>](mapi-data-types.md)

