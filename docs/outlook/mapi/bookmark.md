---
title: BOOKMARK
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
ms.openlocfilehash: be41a9916b6b231d5715cf18fe2b0d804434f2ea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594479"
---
# <a name="bookmark"></a><span data-ttu-id="38574-103">BOOKMARK</span><span class="sxs-lookup"><span data-stu-id="38574-103">BOOKMARK</span></span>

  
  
<span data-ttu-id="38574-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38574-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38574-105">定义书签数据记住表中的位置。</span><span class="sxs-lookup"><span data-stu-id="38574-105">Defines bookmarks data for remembering a position in a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="38574-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="38574-106">Header file:</span></span>  <br/> |<span data-ttu-id="38574-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="38574-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="38574-108">相关的方法：</span><span class="sxs-lookup"><span data-stu-id="38574-108">Related methods:</span></span>  <br/> |<span data-ttu-id="38574-109">[IMAPITable::CreateBookmark](imapitable-createbookmark.md)[IMAPITable::FreeBookmark](imapitable-freebookmark.md)</span><span class="sxs-lookup"><span data-stu-id="38574-109">[IMAPITable::CreateBookmark](imapitable-createbookmark.md)[IMAPITable::FreeBookmark](imapitable-freebookmark.md)</span></span> <br/> |
   
```cpp
typedef ULONG_PTR BOOKMARK;
```

## <a name="remarks"></a><span data-ttu-id="38574-110">注解</span><span class="sxs-lookup"><span data-stu-id="38574-110">Remarks</span></span>

<span data-ttu-id="38574-111">MAPI 定义三个书签，列出，如下所示：</span><span class="sxs-lookup"><span data-stu-id="38574-111">MAPI defines three bookmarks, listed as follows:</span></span>
  
<span data-ttu-id="38574-112">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="38574-112">BOOKMARK_BEGINNING</span></span> 
  
> <span data-ttu-id="38574-113">记住表的起始位置。</span><span class="sxs-lookup"><span data-stu-id="38574-113">Remembers the starting position of the table.</span></span> 
    
<span data-ttu-id="38574-114">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="38574-114">BOOKMARK_CURRENT</span></span> 
  
> <span data-ttu-id="38574-115">记住表的当前位置。</span><span class="sxs-lookup"><span data-stu-id="38574-115">Remembers the current position of the table.</span></span>
    
<span data-ttu-id="38574-116">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="38574-116">BOOKMARK_END</span></span> 
  
> <span data-ttu-id="38574-117">记住表的结束位置。</span><span class="sxs-lookup"><span data-stu-id="38574-117">Remembers the ending position of the table.</span></span>
    
<span data-ttu-id="38574-118">客户端可以创建其他书签记忆其他表的位置。</span><span class="sxs-lookup"><span data-stu-id="38574-118">Clients can create other bookmarks for remembering other table positions.</span></span> <span data-ttu-id="38574-119">书签是仅当打开表时才有效。</span><span class="sxs-lookup"><span data-stu-id="38574-119">Bookmarks are valid only when the table is open.</span></span> <span data-ttu-id="38574-120">客户端必须释放他们关闭关联的表之前创建的所有书签。</span><span class="sxs-lookup"><span data-stu-id="38574-120">Clients must free any bookmarks that they have created before closing the associated table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="38574-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38574-121">See also</span></span>



[<span data-ttu-id="38574-122">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="38574-122">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="38574-123">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="38574-123">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
  
[<span data-ttu-id="38574-124">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="38574-124">IMAPITable::FreeBookmark</span></span>](imapitable-freebookmark.md)
  
[<span data-ttu-id="38574-125">IMAPITable::SeekRow</span><span class="sxs-lookup"><span data-stu-id="38574-125">IMAPITable::SeekRow</span></span>](imapitable-seekrow.md)


[<span data-ttu-id="38574-126">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="38574-126">MAPI Data Types</span></span>](mapi-data-types.md)

