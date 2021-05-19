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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a1ad209ff127a34d7da5ca8dbe1f4a6656d32876
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409452"
---
# <a name="imapitablefreebookmark"></a><span data-ttu-id="1ccc4-103">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="1ccc4-103">IMAPITable::FreeBookmark</span></span>

  
  
<span data-ttu-id="1ccc4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1ccc4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1ccc4-105">释放与书签关联的内存。</span><span class="sxs-lookup"><span data-stu-id="1ccc4-105">Releases the memory associated with a bookmark.</span></span>
  
```cpp
HRESULT FreeBookmark(
BOOKMARK bkPosition
);
```

## <a name="parameters"></a><span data-ttu-id="1ccc4-106">参数</span><span class="sxs-lookup"><span data-stu-id="1ccc4-106">Parameters</span></span>

 <span data-ttu-id="1ccc4-107">_bkPosition_</span><span class="sxs-lookup"><span data-stu-id="1ccc4-107">_bkPosition_</span></span>
  
> <span data-ttu-id="1ccc4-108">[in]要释放的书签，通过调用 [IMAPITable：：CreateBookmark](imapitable-createbookmark.md) 方法创建。</span><span class="sxs-lookup"><span data-stu-id="1ccc4-108">[in] The bookmark to be freed, created by calling the [IMAPITable::CreateBookmark](imapitable-createbookmark.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1ccc4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1ccc4-109">Return value</span></span>

<span data-ttu-id="1ccc4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ccc4-110">S_OK</span></span> 
  
> <span data-ttu-id="1ccc4-111">已成功释放书签。</span><span class="sxs-lookup"><span data-stu-id="1ccc4-111">The bookmark was successfully freed.</span></span>
    
<span data-ttu-id="1ccc4-112">MAPI_E_INVALID_BOOKMARK</span><span class="sxs-lookup"><span data-stu-id="1ccc4-112">MAPI_E_INVALID_BOOKMARK</span></span> 
  
> <span data-ttu-id="1ccc4-113">指定的书签不存在。</span><span class="sxs-lookup"><span data-stu-id="1ccc4-113">The specified bookmark does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1ccc4-114">备注</span><span class="sxs-lookup"><span data-stu-id="1ccc4-114">Remarks</span></span>

<span data-ttu-id="1ccc4-115">**IMAPITable：：FreeBookmark** 方法释放不再需要的书签。</span><span class="sxs-lookup"><span data-stu-id="1ccc4-115">The **IMAPITable::FreeBookmark** method releases a bookmark that is no longer needed.</span></span> <span data-ttu-id="1ccc4-116">此调用后书签不再有效。</span><span class="sxs-lookup"><span data-stu-id="1ccc4-116">The bookmark is no longer valid after this call.</span></span> <span data-ttu-id="1ccc4-117">每当从内存中释放表时，也将释放其所有关联的书签。</span><span class="sxs-lookup"><span data-stu-id="1ccc4-117">Whenever a table is released from memory, all of its associated bookmarks are also released.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="1ccc4-118">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="1ccc4-118">Notes to implementers</span></span>

<span data-ttu-id="1ccc4-119">如果调用方传递  _bkPosition_ 参数中的三个预定义书签之一，则忽略请求并返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="1ccc4-119">If the caller passes one of the three predefined bookmarks in the  _bkPosition_ parameter, ignore the request and return S_OK.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1ccc4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ccc4-120">See also</span></span>



[<span data-ttu-id="1ccc4-121">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="1ccc4-121">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="1ccc4-122">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1ccc4-122">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

