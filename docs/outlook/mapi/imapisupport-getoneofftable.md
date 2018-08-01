---
title: IMAPISupportGetOneOffTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetOneOffTable
api_type:
- COM
ms.assetid: 6800fd3a-aa43-45fe-9cc2-102d0ef43edf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 51cd838164e3de28ab33d6ab8a08a021360f3183
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775606"
---
# <a name="imapisupportgetoneofftable"></a><span data-ttu-id="5aeb7-103">IMAPISupport::GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="5aeb7-103">IMAPISupport::GetOneOffTable</span></span>

  
  
<span data-ttu-id="5aeb7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5aeb7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5aeb7-105">返回到 MAPI 一次性表格 （所有通讯都簿提供程序支持创建新的收件人的模板的列表） 的指针。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-105">Returns a pointer to the MAPI one-off table (a list of templates that all address book providers support for creating new recipients).</span></span>
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="5aeb7-106">参数</span><span class="sxs-lookup"><span data-stu-id="5aeb7-106">Parameters</span></span>

 <span data-ttu-id="5aeb7-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5aeb7-107">_ulFlags_</span></span>
  
> <span data-ttu-id="5aeb7-108">[in]位掩码的标志，用于控制字符串列的类型。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-108">[in] A bitmask of flags that controls the type of the string columns.</span></span> <span data-ttu-id="5aeb7-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="5aeb7-109">The following flag can be set:</span></span>
    
<span data-ttu-id="5aeb7-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5aeb7-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5aeb7-111">字符串列的 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="5aeb7-112">如果未设置 MAPI_UNICODE 标志，字符串列的 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
 <span data-ttu-id="5aeb7-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="5aeb7-113">_lppTable_</span></span>
  
> <span data-ttu-id="5aeb7-114">[输出]指向一次性表格的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-114">[out] A pointer to a pointer to the one-off table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5aeb7-115">返回值</span><span class="sxs-lookup"><span data-stu-id="5aeb7-115">Return value</span></span>

<span data-ttu-id="5aeb7-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="5aeb7-116">S_OK</span></span> 
  
> <span data-ttu-id="5aeb7-117">已成功检索一次性表。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-117">The one-off table was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5aeb7-118">说明</span><span class="sxs-lookup"><span data-stu-id="5aeb7-118">Remarks</span></span>

<span data-ttu-id="5aeb7-119">对于通讯簿提供程序支持对象实现**IMAPISupport::GetOneOffTable**方法。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-119">The **IMAPISupport::GetOneOffTable** method is implemented for address book provider support objects.</span></span> <span data-ttu-id="5aeb7-120">通讯簿提供程序调用**GetOneOffTable**检索模板，用于创建新的收件人的完整列表。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-120">Address book providers call **GetOneOffTable** to retrieve the complete list of templates for creating new recipients.</span></span> <span data-ttu-id="5aeb7-121">此表包含会话中处于活动状态的通讯簿提供程序支持的模板，以及 MAPI 支持的模板。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-121">This table includes templates that address book providers that are active in the session support, as well as templates that MAPI supports.</span></span> 
  
<span data-ttu-id="5aeb7-122">新创建的收件人可用于解决一条消息，也可以添加到通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-122">The newly created recipients can be used to address a message or can be added to an address book container.</span></span>
  
<span data-ttu-id="5aeb7-123">一次性表中所需的列组成的属性的列表，请参阅[一次性表](one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-123">For a list of the properties that make up the required column set in one-off tables, see [One-Off Tables](one-off-tables.md).</span></span>
  
<span data-ttu-id="5aeb7-124">_UlFlags_参数中设置 MAPI_UNICODE 标志会影响从[IMAPITable::QueryColumns](imapitable-querycolumns.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-124">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> <span data-ttu-id="5aeb7-125">此标志还将控制[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-125">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5aeb7-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5aeb7-126">Notes to callers</span></span>

<span data-ttu-id="5aeb7-127">如果您已注册接收到此一次性表的更改的通知，您还将收到与其他提供程序的一次性表的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-127">If you are registered to receive notifications of changes to this one-off table, you will also receive notifications of changes to other providers' one-off tables.</span></span> <span data-ttu-id="5aeb7-128">根据这些通知，您可以支持在当前会话过程中添加的新地址类型。</span><span class="sxs-lookup"><span data-stu-id="5aeb7-128">Based on these notifications, you can support new address types that are added during the current session.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5aeb7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5aeb7-129">See also</span></span>



[<span data-ttu-id="5aeb7-130">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="5aeb7-130">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)
  
[<span data-ttu-id="5aeb7-131">IMAPISupport::NewEntry</span><span class="sxs-lookup"><span data-stu-id="5aeb7-131">IMAPISupport::NewEntry</span></span>](imapisupport-newentry.md)
  
[<span data-ttu-id="5aeb7-132">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5aeb7-132">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="5aeb7-133">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="5aeb7-133">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="5aeb7-134">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="5aeb7-134">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="5aeb7-135">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="5aeb7-135">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="5aeb7-136">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="5aeb7-136">PidTagCreateTemplates Canonical Property</span></span>](pidtagcreatetemplates-canonical-property.md)
  
[<span data-ttu-id="5aeb7-137">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5aeb7-137">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="5aeb7-138">一次性表</span><span class="sxs-lookup"><span data-stu-id="5aeb7-138">One-Off Tables</span></span>](one-off-tables.md)

