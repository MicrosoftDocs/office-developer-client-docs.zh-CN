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
# <a name="bookmark"></a><span data-ttu-id="ac98d-103">书签</span><span class="sxs-lookup"><span data-stu-id="ac98d-103">BOOKMARK</span></span>

  
  
<span data-ttu-id="ac98d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ac98d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ac98d-105">定义用于记住表中某个位置的书签数据。</span><span class="sxs-lookup"><span data-stu-id="ac98d-105">Defines bookmarks data for remembering a position in a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ac98d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ac98d-106">Header file:</span></span>  <br/> |<span data-ttu-id="ac98d-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ac98d-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="ac98d-108">相关方法:</span><span class="sxs-lookup"><span data-stu-id="ac98d-108">Related methods:</span></span>  <br/> |<span data-ttu-id="ac98d-109">[IMAPITable:: CreateBookmark](imapitable-createbookmark.md)[IMAPITable:: FreeBookmark](imapitable-freebookmark.md)</span><span class="sxs-lookup"><span data-stu-id="ac98d-109">[IMAPITable::CreateBookmark](imapitable-createbookmark.md)[IMAPITable::FreeBookmark](imapitable-freebookmark.md)</span></span> <br/> |
   
```cpp
typedef ULONG_PTR BOOKMARK;
```

## <a name="remarks"></a><span data-ttu-id="ac98d-110">说明</span><span class="sxs-lookup"><span data-stu-id="ac98d-110">Remarks</span></span>

<span data-ttu-id="ac98d-111">MAPI 定义了三个书签, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="ac98d-111">MAPI defines three bookmarks, listed as follows:</span></span>
  
<span data-ttu-id="ac98d-112">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="ac98d-112">BOOKMARK_BEGINNING</span></span> 
  
> <span data-ttu-id="ac98d-113">记住表的起始位置。</span><span class="sxs-lookup"><span data-stu-id="ac98d-113">Remembers the starting position of the table.</span></span> 
    
<span data-ttu-id="ac98d-114">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="ac98d-114">BOOKMARK_CURRENT</span></span> 
  
> <span data-ttu-id="ac98d-115">记住表的当前位置。</span><span class="sxs-lookup"><span data-stu-id="ac98d-115">Remembers the current position of the table.</span></span>
    
<span data-ttu-id="ac98d-116">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="ac98d-116">BOOKMARK_END</span></span> 
  
> <span data-ttu-id="ac98d-117">记住表的结束位置。</span><span class="sxs-lookup"><span data-stu-id="ac98d-117">Remembers the ending position of the table.</span></span>
    
<span data-ttu-id="ac98d-118">客户端可以创建其他书签来记住其他表位置。</span><span class="sxs-lookup"><span data-stu-id="ac98d-118">Clients can create other bookmarks for remembering other table positions.</span></span> <span data-ttu-id="ac98d-119">书签仅在表打开时有效。</span><span class="sxs-lookup"><span data-stu-id="ac98d-119">Bookmarks are valid only when the table is open.</span></span> <span data-ttu-id="ac98d-120">客户端必须释放已创建的任何书签, 然后再关闭相关联的表。</span><span class="sxs-lookup"><span data-stu-id="ac98d-120">Clients must free any bookmarks that they have created before closing the associated table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ac98d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac98d-121">See also</span></span>



[<span data-ttu-id="ac98d-122">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="ac98d-122">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="ac98d-123">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="ac98d-123">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
  
[<span data-ttu-id="ac98d-124">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="ac98d-124">IMAPITable::FreeBookmark</span></span>](imapitable-freebookmark.md)
  
[<span data-ttu-id="ac98d-125">IMAPITable::SeekRow</span><span class="sxs-lookup"><span data-stu-id="ac98d-125">IMAPITable::SeekRow</span></span>](imapitable-seekrow.md)


[<span data-ttu-id="ac98d-126">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="ac98d-126">MAPI Data Types</span></span>](mapi-data-types.md)

