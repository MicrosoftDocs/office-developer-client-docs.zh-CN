---
title: IMAPITableFreeBookmark
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.FreeBookmark
api_type:
- COM
ms.assetid: 797833f7-8295-41bc-8980-977e5f5e05e8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 36d1518764985c4783d967e263ca5c05d63f935f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588480"
---
# <a name="imapitablefreebookmark"></a><span data-ttu-id="0701c-103">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="0701c-103">IMAPITable::FreeBookmark</span></span>

  
  
<span data-ttu-id="0701c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0701c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0701c-105">释放与一个书签关联的内存。</span><span class="sxs-lookup"><span data-stu-id="0701c-105">Releases the memory associated with a bookmark.</span></span>
  
```cpp
HRESULT FreeBookmark(
BOOKMARK bkPosition
);
```

## <a name="parameters"></a><span data-ttu-id="0701c-106">参数</span><span class="sxs-lookup"><span data-stu-id="0701c-106">Parameters</span></span>

 <span data-ttu-id="0701c-107">_bkPosition_</span><span class="sxs-lookup"><span data-stu-id="0701c-107">_bkPosition_</span></span>
  
> <span data-ttu-id="0701c-108">[in]通过调用[IMAPITable::CreateBookmark](imapitable-createbookmark.md)方法创建可以释放，该书签。</span><span class="sxs-lookup"><span data-stu-id="0701c-108">[in] The bookmark to be freed, created by calling the [IMAPITable::CreateBookmark](imapitable-createbookmark.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0701c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0701c-109">Return value</span></span>

<span data-ttu-id="0701c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0701c-110">S_OK</span></span> 
  
> <span data-ttu-id="0701c-111">已成功释放该书签。</span><span class="sxs-lookup"><span data-stu-id="0701c-111">The bookmark was successfully freed.</span></span>
    
<span data-ttu-id="0701c-112">MAPI_E_INVALID_BOOKMARK</span><span class="sxs-lookup"><span data-stu-id="0701c-112">MAPI_E_INVALID_BOOKMARK</span></span> 
  
> <span data-ttu-id="0701c-113">不存在指定的书签。</span><span class="sxs-lookup"><span data-stu-id="0701c-113">The specified bookmark does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0701c-114">注解</span><span class="sxs-lookup"><span data-stu-id="0701c-114">Remarks</span></span>

<span data-ttu-id="0701c-115">**IMAPITable::FreeBookmark**方法释放不再需要的书签。</span><span class="sxs-lookup"><span data-stu-id="0701c-115">The **IMAPITable::FreeBookmark** method releases a bookmark that is no longer needed.</span></span> <span data-ttu-id="0701c-116">此呼叫后，该书签不再有效。</span><span class="sxs-lookup"><span data-stu-id="0701c-116">The bookmark is no longer valid after this call.</span></span> <span data-ttu-id="0701c-117">从内存中发布一个表时，所有及其关联的书签也将被释放。</span><span class="sxs-lookup"><span data-stu-id="0701c-117">Whenever a table is released from memory, all of its associated bookmarks are also released.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="0701c-118">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="0701c-118">Notes to implementers</span></span>

<span data-ttu-id="0701c-119">如果呼叫者中_bkPosition_参数传递的三个预定义书签之一，忽略的请求，并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0701c-119">If the caller passes one of the three predefined bookmarks in the  _bkPosition_ parameter, ignore the request and return S_OK.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0701c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0701c-120">See also</span></span>



[<span data-ttu-id="0701c-121">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="0701c-121">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="0701c-122">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0701c-122">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

