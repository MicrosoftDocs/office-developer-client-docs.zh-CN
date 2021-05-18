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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412756"
---
# <a name="imapisupportgetoneofftable"></a><span data-ttu-id="edb99-103">IMAPISupport::GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="edb99-103">IMAPISupport::GetOneOffTable</span></span>

  
  
<span data-ttu-id="edb99-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="edb99-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="edb99-105">返回一个指向 MAPI 一 (表的指针，该表包含所有通讯簿提供程序都支持创建新收件人的) 。</span><span class="sxs-lookup"><span data-stu-id="edb99-105">Returns a pointer to the MAPI one-off table (a list of templates that all address book providers support for creating new recipients).</span></span>
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="edb99-106">参数</span><span class="sxs-lookup"><span data-stu-id="edb99-106">Parameters</span></span>

 <span data-ttu-id="edb99-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="edb99-107">_ulFlags_</span></span>
  
> <span data-ttu-id="edb99-108">[in]控制字符串列类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="edb99-108">[in] A bitmask of flags that controls the type of the string columns.</span></span> <span data-ttu-id="edb99-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="edb99-109">The following flag can be set:</span></span>
    
<span data-ttu-id="edb99-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="edb99-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="edb99-111">字符串列采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="edb99-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="edb99-112">如果未MAPI_UNICODE，则字符串列采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="edb99-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
 <span data-ttu-id="edb99-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="edb99-113">_lppTable_</span></span>
  
> <span data-ttu-id="edb99-114">[out]指向指向一次表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="edb99-114">[out] A pointer to a pointer to the one-off table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="edb99-115">返回值</span><span class="sxs-lookup"><span data-stu-id="edb99-115">Return value</span></span>

<span data-ttu-id="edb99-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="edb99-116">S_OK</span></span> 
  
> <span data-ttu-id="edb99-117">已成功检索一次表。</span><span class="sxs-lookup"><span data-stu-id="edb99-117">The one-off table was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="edb99-118">备注</span><span class="sxs-lookup"><span data-stu-id="edb99-118">Remarks</span></span>

<span data-ttu-id="edb99-119">**为通讯簿提供程序支持对象实现 IMAPISupport：：GetOneOffTable** 方法。</span><span class="sxs-lookup"><span data-stu-id="edb99-119">The **IMAPISupport::GetOneOffTable** method is implemented for address book provider support objects.</span></span> <span data-ttu-id="edb99-120">通讯簿提供程序调用 **GetOneOffTable** 以检索用于创建新收件人的模板的完整列表。</span><span class="sxs-lookup"><span data-stu-id="edb99-120">Address book providers call **GetOneOffTable** to retrieve the complete list of templates for creating new recipients.</span></span> <span data-ttu-id="edb99-121">此表包括通讯簿提供程序在会话支持中处于活动状态的模板，以及 MAPI 支持的模板。</span><span class="sxs-lookup"><span data-stu-id="edb99-121">This table includes templates that address book providers that are active in the session support, as well as templates that MAPI supports.</span></span> 
  
<span data-ttu-id="edb99-122">新创建的收件人可用于处理邮件，也可以添加到通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="edb99-122">The newly created recipients can be used to address a message or can be added to an address book container.</span></span>
  
<span data-ttu-id="edb99-123">有关一对一表中必需列集的属性列表，请参阅 [一键式表格](one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="edb99-123">For a list of the properties that make up the required column set in one-off tables, see [One-Off Tables](one-off-tables.md).</span></span>
  
<span data-ttu-id="edb99-124">在  _ulFlags_ 参数中设置 MAPI_UNICODE 标志会影响 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="edb99-124">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> <span data-ttu-id="edb99-125">此标志还按 [IMAPITable：：QuerySortOrder](imapitable-querysortorder.md) 方法返回的排序顺序控制属性类型。</span><span class="sxs-lookup"><span data-stu-id="edb99-125">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="edb99-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="edb99-126">Notes to callers</span></span>

<span data-ttu-id="edb99-127">如果注册为接收对此一键式表的更改的通知，还将收到其他提供商的一键式表更改通知。</span><span class="sxs-lookup"><span data-stu-id="edb99-127">If you are registered to receive notifications of changes to this one-off table, you will also receive notifications of changes to other providers' one-off tables.</span></span> <span data-ttu-id="edb99-128">根据这些通知，可以支持在当前会话期间添加的新地址类型。</span><span class="sxs-lookup"><span data-stu-id="edb99-128">Based on these notifications, you can support new address types that are added during the current session.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="edb99-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edb99-129">See also</span></span>



[<span data-ttu-id="edb99-130">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="edb99-130">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)
  
[<span data-ttu-id="edb99-131">IMAPISupport::NewEntry</span><span class="sxs-lookup"><span data-stu-id="edb99-131">IMAPISupport::NewEntry</span></span>](imapisupport-newentry.md)
  
[<span data-ttu-id="edb99-132">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="edb99-132">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="edb99-133">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="edb99-133">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="edb99-134">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="edb99-134">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="edb99-135">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="edb99-135">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="edb99-136">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="edb99-136">PidTagCreateTemplates Canonical Property</span></span>](pidtagcreatetemplates-canonical-property.md)
  
[<span data-ttu-id="edb99-137">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="edb99-137">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="edb99-138">一键式表</span><span class="sxs-lookup"><span data-stu-id="edb99-138">One-Off Tables</span></span>](one-off-tables.md)

