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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a913f2f3a72a365ec7d5078eccf31c4212ca83a5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776091"
---
# <a name="itabledatahrgetview"></a><span data-ttu-id="4d093-103">ITableData::HrGetView</span><span class="sxs-lookup"><span data-stu-id="4d093-103">ITableData::HrGetView</span></span>

  
  
<span data-ttu-id="4d093-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4d093-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4d093-105">创建表视图中，返回到[IMAPITable](imapitableiunknown.md)实现的指针。</span><span class="sxs-lookup"><span data-stu-id="4d093-105">Creates a table view, returning a pointer to an [IMAPITable](imapitableiunknown.md) implementation.</span></span> 
  
```cpp
HRESULT HrGetView(
  LPSSortOrderSet lpSSortOrderSet,
  CALLERRELEASE FAR * lpfCallerRelease,
  ULONG_PTR ulCallerData,
  LPMAPITABLE FAR * lppMAPITable
);
```

## <a name="parameters"></a><span data-ttu-id="4d093-106">参数</span><span class="sxs-lookup"><span data-stu-id="4d093-106">Parameters</span></span>

 <span data-ttu-id="4d093-107">_lpSSortOrderSet_</span><span class="sxs-lookup"><span data-stu-id="4d093-107">_lpSSortOrderSet_</span></span>
  
> <span data-ttu-id="4d093-108">[in]指向介绍表视图的排序顺序排序顺序结构的指针。</span><span class="sxs-lookup"><span data-stu-id="4d093-108">[in] A pointer to a sort order structure that describes the sort order for the table view.</span></span> <span data-ttu-id="4d093-109">如果_lpSSortOrderSet_参数中传递 NULL，则视图未排序。</span><span class="sxs-lookup"><span data-stu-id="4d093-109">If NULL is passed in the  _lpSSortOrderSet_ parameter, the view is not sorted.</span></span> 
    
 <span data-ttu-id="4d093-110">_lpfCallerRelease_</span><span class="sxs-lookup"><span data-stu-id="4d093-110">_lpfCallerRelease_</span></span>
  
> <span data-ttu-id="4d093-111">[in]指向[CALLERRELEASE](callerrelease.md)原型 MAPI 调用时释放视图所基于的回调函数的指针。</span><span class="sxs-lookup"><span data-stu-id="4d093-111">[in] A pointer to a callback function based on the [CALLERRELEASE](callerrelease.md) prototype that MAPI calls when it releases the view.</span></span> <span data-ttu-id="4d093-112">如果_lpfCallerRelease_参数中传递 NULL，则没有函数调用上的视图的版本。</span><span class="sxs-lookup"><span data-stu-id="4d093-112">If NULL is passed in the  _lpfCallerRelease_ parameter, no function is called on release of the view.</span></span> 
    
 <span data-ttu-id="4d093-113">_ulCallerData_</span><span class="sxs-lookup"><span data-stu-id="4d093-113">_ulCallerData_</span></span>
  
> <span data-ttu-id="4d093-114">[in]必须使用新的视图保存并传递给回调函数使用的数据所指的_lpfCallerRelease_。</span><span class="sxs-lookup"><span data-stu-id="4d093-114">[in] The data that must be saved with the new view and passed to the callback function pointed to by  _lpfCallerRelease_.</span></span>
    
 <span data-ttu-id="4d093-115">_lppMAPITable_</span><span class="sxs-lookup"><span data-stu-id="4d093-115">_lppMAPITable_</span></span>
  
> <span data-ttu-id="4d093-116">[输出]为指向新创建的视图的指针。</span><span class="sxs-lookup"><span data-stu-id="4d093-116">[out] A pointer to a pointer to the newly created view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4d093-117">返回值</span><span class="sxs-lookup"><span data-stu-id="4d093-117">Return value</span></span>

<span data-ttu-id="4d093-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d093-118">S_OK</span></span> 
  
> <span data-ttu-id="4d093-119">成功创建的视图。</span><span class="sxs-lookup"><span data-stu-id="4d093-119">The view was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4d093-120">说明</span><span class="sxs-lookup"><span data-stu-id="4d093-120">Remarks</span></span>

<span data-ttu-id="4d093-121">**ITableData::HrGetView**方法在表中， _lpSSortOrderSet_参数指向的顺序排序创建只读视图的数据。</span><span class="sxs-lookup"><span data-stu-id="4d093-121">The **ITableData::HrGetView** method creates a read-only view of the data in the table, sorted in the order pointed to by the  _lpSSortOrderSet_ parameter.</span></span> <span data-ttu-id="4d093-122">光标置于视图中的第一行开头处。</span><span class="sxs-lookup"><span data-stu-id="4d093-122">The cursor is placed at the beginning of the first row in the view.</span></span> <span data-ttu-id="4d093-123">返回**IMAPITable**接口实现用于访问该视图。</span><span class="sxs-lookup"><span data-stu-id="4d093-123">An **IMAPITable** interface implementation for accessing the view is returned.</span></span> 
  
<span data-ttu-id="4d093-124">服务提供商调用**HrGetView**时所需向表格的客户端访问。</span><span class="sxs-lookup"><span data-stu-id="4d093-124">Service providers call **HrGetView** when they need to give a client access to a table.</span></span> <span data-ttu-id="4d093-125">**HrGetView**创建视图，并返回**IMAPITable**指针。</span><span class="sxs-lookup"><span data-stu-id="4d093-125">**HrGetView** creates the view and returns the **IMAPITable** pointer.</span></span> <span data-ttu-id="4d093-126">服务提供商反过来传递到客户端的指针。</span><span class="sxs-lookup"><span data-stu-id="4d093-126">Service providers in turn pass the pointer on to the client.</span></span> <span data-ttu-id="4d093-127">当客户端完成使用表后，并将调用其[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法时， **HrGetView**调用_lpfCallerRelease_参数指向的回调函数。</span><span class="sxs-lookup"><span data-stu-id="4d093-127">When the client is finished using the table and calls its [IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method, **HrGetView** calls the callback function pointed to by the  _lpfCallerRelease_ parameter.</span></span> 
  
<span data-ttu-id="4d093-128">如果服务提供商需要具有一个自定义的列设置的视图返回到客户端或限制，提供程序可以调用视图的[IMAPITable::SetColumns](imapitable-setcolumns.md)和[IMAPITable::Restrict](imapitable-restrict.md)方法才允许客户端访问。</span><span class="sxs-lookup"><span data-stu-id="4d093-128">If a service provider needs to return to a client a view that has a customized column set or a restriction, the provider can call the view's [IMAPITable::SetColumns](imapitable-setcolumns.md) and [IMAPITable::Restrict](imapitable-restrict.md) methods before allowing the client access.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4d093-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d093-129">See also</span></span>



[<span data-ttu-id="4d093-130">CALLERRELEASE</span><span class="sxs-lookup"><span data-stu-id="4d093-130">CALLERRELEASE</span></span>](callerrelease.md)
  
[<span data-ttu-id="4d093-131">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4d093-131">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="4d093-132">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="4d093-132">SSortOrderSet</span></span>](ssortorderset.md)
  
[<span data-ttu-id="4d093-133">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4d093-133">ITableData : IUnknown</span></span>](itabledataiunknown.md)

