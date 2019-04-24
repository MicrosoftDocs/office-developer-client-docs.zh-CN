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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c0beec8a0b234794d3f623c4ceac773db698dd79
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316574"
---
# <a name="imapisupportgetoneofftable"></a><span data-ttu-id="2f11f-103">IMAPISupport::GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="2f11f-103">IMAPISupport::GetOneOffTable</span></span>

  
  
<span data-ttu-id="2f11f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f11f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f11f-105">返回指向 MAPI 一次性表 (所有通讯簿提供程序为创建新收件人所支持的模板列表) 的指针。</span><span class="sxs-lookup"><span data-stu-id="2f11f-105">Returns a pointer to the MAPI one-off table (a list of templates that all address book providers support for creating new recipients).</span></span>
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="2f11f-106">参数</span><span class="sxs-lookup"><span data-stu-id="2f11f-106">Parameters</span></span>

 <span data-ttu-id="2f11f-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2f11f-107">_ulFlags_</span></span>
  
> <span data-ttu-id="2f11f-108">实时用于控制字符串列的类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2f11f-108">[in] A bitmask of flags that controls the type of the string columns.</span></span> <span data-ttu-id="2f11f-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="2f11f-109">The following flag can be set:</span></span>
    
<span data-ttu-id="2f11f-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2f11f-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="2f11f-111">字符串列采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="2f11f-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="2f11f-112">如果未设置 MAPI_UNICODE 标志, 则字符串列的格式为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="2f11f-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
 <span data-ttu-id="2f11f-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="2f11f-113">_lppTable_</span></span>
  
> <span data-ttu-id="2f11f-114">排除指向一次性表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2f11f-114">[out] A pointer to a pointer to the one-off table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2f11f-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2f11f-115">Return value</span></span>

<span data-ttu-id="2f11f-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f11f-116">S_OK</span></span> 
  
> <span data-ttu-id="2f11f-117">已成功检索一次性表。</span><span class="sxs-lookup"><span data-stu-id="2f11f-117">The one-off table was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2f11f-118">注解</span><span class="sxs-lookup"><span data-stu-id="2f11f-118">Remarks</span></span>

<span data-ttu-id="2f11f-119">为通讯簿提供程序支持对象实现了**IMAPISupport:: GetOneOffTable**方法。</span><span class="sxs-lookup"><span data-stu-id="2f11f-119">The **IMAPISupport::GetOneOffTable** method is implemented for address book provider support objects.</span></span> <span data-ttu-id="2f11f-120">通讯簿提供程序调用**GetOneOffTable**以检索用于创建新收件人的模板的完整列表。</span><span class="sxs-lookup"><span data-stu-id="2f11f-120">Address book providers call **GetOneOffTable** to retrieve the complete list of templates for creating new recipients.</span></span> <span data-ttu-id="2f11f-121">此表包含了通讯簿提供程序在会话支持中处于活动状态的模板以及 MAPI 支持的模板。</span><span class="sxs-lookup"><span data-stu-id="2f11f-121">This table includes templates that address book providers that are active in the session support, as well as templates that MAPI supports.</span></span> 
  
<span data-ttu-id="2f11f-122">可以使用新创建的收件人来处理邮件, 也可以将其添加到通讯簿容器中。</span><span class="sxs-lookup"><span data-stu-id="2f11f-122">The newly created recipients can be used to address a message or can be added to an address book container.</span></span>
  
<span data-ttu-id="2f11f-123">有关构成一次性表中设置的必需列的属性列表, 请参阅[一次性表](one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="2f11f-123">For a list of the properties that make up the required column set in one-off tables, see [One-Off Tables](one-off-tables.md).</span></span>
  
<span data-ttu-id="2f11f-124">在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响从[IMAPITable:: QueryColumns](imapitable-querycolumns.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="2f11f-124">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> <span data-ttu-id="2f11f-125">此标志还按[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序控制属性类型。</span><span class="sxs-lookup"><span data-stu-id="2f11f-125">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="2f11f-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2f11f-126">Notes to callers</span></span>

<span data-ttu-id="2f11f-127">如果您已注册接收对此一次性表所做更改的通知, 则还将接收对其他提供程序的一次性表所做更改的通知。</span><span class="sxs-lookup"><span data-stu-id="2f11f-127">If you are registered to receive notifications of changes to this one-off table, you will also receive notifications of changes to other providers' one-off tables.</span></span> <span data-ttu-id="2f11f-128">根据这些通知, 可以支持在当前会话期间添加的新地址类型。</span><span class="sxs-lookup"><span data-stu-id="2f11f-128">Based on these notifications, you can support new address types that are added during the current session.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f11f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f11f-129">See also</span></span>



[<span data-ttu-id="2f11f-130">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="2f11f-130">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)
  
[<span data-ttu-id="2f11f-131">IMAPISupport::NewEntry</span><span class="sxs-lookup"><span data-stu-id="2f11f-131">IMAPISupport::NewEntry</span></span>](imapisupport-newentry.md)
  
[<span data-ttu-id="2f11f-132">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2f11f-132">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="2f11f-133">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="2f11f-133">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="2f11f-134">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="2f11f-134">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="2f11f-135">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="2f11f-135">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="2f11f-136">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="2f11f-136">PidTagCreateTemplates Canonical Property</span></span>](pidtagcreatetemplates-canonical-property.md)
  
[<span data-ttu-id="2f11f-137">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2f11f-137">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="2f11f-138">一次性表</span><span class="sxs-lookup"><span data-stu-id="2f11f-138">One-Off Tables</span></span>](one-off-tables.md)

