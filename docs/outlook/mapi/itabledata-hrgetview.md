---
title: ITableDataHrGetView
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrGetView
api_type:
- COM
ms.assetid: 0e2a47be-497b-4031-87ce-60b2635e25f7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 375a0f1d39b09b7ad453120f20752e00ffda0e15
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278713"
---
# <a name="itabledatahrgetview"></a><span data-ttu-id="6e15d-103">ITableData::HrGetView</span><span class="sxs-lookup"><span data-stu-id="6e15d-103">ITableData::HrGetView</span></span>

  
  
<span data-ttu-id="6e15d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6e15d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6e15d-105">创建表视图，返回指向 [IMAPITable](imapitableiunknown.md) 实现指针。</span><span class="sxs-lookup"><span data-stu-id="6e15d-105">Creates a table view, returning a pointer to an [IMAPITable](imapitableiunknown.md) implementation.</span></span> 
  
```cpp
HRESULT HrGetView(
  LPSSortOrderSet lpSSortOrderSet,
  CALLERRELEASE FAR * lpfCallerRelease,
  ULONG_PTR ulCallerData,
  LPMAPITABLE FAR * lppMAPITable
);
```

## <a name="parameters"></a><span data-ttu-id="6e15d-106">参数</span><span class="sxs-lookup"><span data-stu-id="6e15d-106">Parameters</span></span>

 <span data-ttu-id="6e15d-107">_lpSSortOrderSet_</span><span class="sxs-lookup"><span data-stu-id="6e15d-107">_lpSSortOrderSet_</span></span>
  
> <span data-ttu-id="6e15d-108">[in]指向用于描述表视图的排序顺序的排序顺序结构的指针。</span><span class="sxs-lookup"><span data-stu-id="6e15d-108">[in] A pointer to a sort order structure that describes the sort order for the table view.</span></span> <span data-ttu-id="6e15d-109">如果在  _lpSSortOrderSet_ 参数中传递 NULL，则不对视图进行排序。</span><span class="sxs-lookup"><span data-stu-id="6e15d-109">If NULL is passed in the  _lpSSortOrderSet_ parameter, the view is not sorted.</span></span> 
    
 <span data-ttu-id="6e15d-110">_lpfCallerRelease_</span><span class="sxs-lookup"><span data-stu-id="6e15d-110">_lpfCallerRelease_</span></span>
  
> <span data-ttu-id="6e15d-111">[in]指向基于 [CALLERRELEASE](callerrelease.md) 原型的回调函数的指针，MAPI 在发布视图时调用该原型。</span><span class="sxs-lookup"><span data-stu-id="6e15d-111">[in] A pointer to a callback function based on the [CALLERRELEASE](callerrelease.md) prototype that MAPI calls when it releases the view.</span></span> <span data-ttu-id="6e15d-112">如果在  _lpfCallerRelease_ 参数中传递 NULL，则发布视图时不调用任何函数。</span><span class="sxs-lookup"><span data-stu-id="6e15d-112">If NULL is passed in the  _lpfCallerRelease_ parameter, no function is called on release of the view.</span></span> 
    
 <span data-ttu-id="6e15d-113">_ulCallerData_</span><span class="sxs-lookup"><span data-stu-id="6e15d-113">_ulCallerData_</span></span>
  
> <span data-ttu-id="6e15d-114">[in]必须使用新视图保存并传递给  _lpfCallerRelease_ 指向的回调函数的数据。</span><span class="sxs-lookup"><span data-stu-id="6e15d-114">[in] The data that must be saved with the new view and passed to the callback function pointed to by  _lpfCallerRelease_.</span></span>
    
 <span data-ttu-id="6e15d-115">_lppMAPITable_</span><span class="sxs-lookup"><span data-stu-id="6e15d-115">_lppMAPITable_</span></span>
  
> <span data-ttu-id="6e15d-116">[out]指向指向新创建的视图的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="6e15d-116">[out] A pointer to a pointer to the newly created view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6e15d-117">返回值</span><span class="sxs-lookup"><span data-stu-id="6e15d-117">Return value</span></span>

<span data-ttu-id="6e15d-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e15d-118">S_OK</span></span> 
  
> <span data-ttu-id="6e15d-119">已成功创建视图。</span><span class="sxs-lookup"><span data-stu-id="6e15d-119">The view was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6e15d-120">备注</span><span class="sxs-lookup"><span data-stu-id="6e15d-120">Remarks</span></span>

<span data-ttu-id="6e15d-121">**ITableData：：HrGetView** 方法创建表中数据的只读视图，按 _lpSSortOrderSet_ 参数指向的顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="6e15d-121">The **ITableData::HrGetView** method creates a read-only view of the data in the table, sorted in the order pointed to by the  _lpSSortOrderSet_ parameter.</span></span> <span data-ttu-id="6e15d-122">光标放置在视图中第一行的开头。</span><span class="sxs-lookup"><span data-stu-id="6e15d-122">The cursor is placed at the beginning of the first row in the view.</span></span> <span data-ttu-id="6e15d-123">返回 **用于访问视图的 IMAPITable** 接口实现。</span><span class="sxs-lookup"><span data-stu-id="6e15d-123">An **IMAPITable** interface implementation for accessing the view is returned.</span></span> 
  
<span data-ttu-id="6e15d-124">当服务提供商需要向客户端授予对表的访问权限时，将调用 **HrGetView。**</span><span class="sxs-lookup"><span data-stu-id="6e15d-124">Service providers call **HrGetView** when they need to give a client access to a table.</span></span> <span data-ttu-id="6e15d-125">**HrGetView** 创建视图并返回 **IMAPITable** 指针。</span><span class="sxs-lookup"><span data-stu-id="6e15d-125">**HrGetView** creates the view and returns the **IMAPITable** pointer.</span></span> <span data-ttu-id="6e15d-126">服务提供商反过来将指针传递给客户端。</span><span class="sxs-lookup"><span data-stu-id="6e15d-126">Service providers in turn pass the pointer on to the client.</span></span> <span data-ttu-id="6e15d-127">当客户端使用完表并调用其 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法时 **，HrGetView** 将调用  _lpfCallerRelease_ 参数指向的回调函数。</span><span class="sxs-lookup"><span data-stu-id="6e15d-127">When the client is finished using the table and calls its [IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method, **HrGetView** calls the callback function pointed to by the  _lpfCallerRelease_ parameter.</span></span> 
  
<span data-ttu-id="6e15d-128">如果服务提供商需要向客户端返回具有自定义列集或限制的视图，则提供程序可以在允许客户端访问之前调用该视图的 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 和 [IMAPITable：：Restrict](imapitable-restrict.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="6e15d-128">If a service provider needs to return to a client a view that has a customized column set or a restriction, the provider can call the view's [IMAPITable::SetColumns](imapitable-setcolumns.md) and [IMAPITable::Restrict](imapitable-restrict.md) methods before allowing the client access.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6e15d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e15d-129">See also</span></span>



[<span data-ttu-id="6e15d-130">CALLERRELEASE</span><span class="sxs-lookup"><span data-stu-id="6e15d-130">CALLERRELEASE</span></span>](callerrelease.md)
  
[<span data-ttu-id="6e15d-131">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6e15d-131">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="6e15d-132">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="6e15d-132">SSortOrderSet</span></span>](ssortorderset.md)
  
[<span data-ttu-id="6e15d-133">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6e15d-133">ITableData : IUnknown</span></span>](itabledataiunknown.md)

