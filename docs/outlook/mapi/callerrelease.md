---
title: CALLERRELEASE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CALLERRELEASE
api_type:
- HeaderDef
ms.assetid: 80ba893d-3380-4db1-9175-f5b84cb57def
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9a22550e60c9de38236a9f612c7e60f50f18978f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408724"
---
# <a name="callerrelease"></a><span data-ttu-id="5cb57-103">CALLERRELEASE</span><span class="sxs-lookup"><span data-stu-id="5cb57-103">CALLERRELEASE</span></span>

  
  
<span data-ttu-id="5cb57-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5cb57-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5cb57-105">定义一个回调函数，该函数可在发布表视图时释放表数据对象。</span><span class="sxs-lookup"><span data-stu-id="5cb57-105">Defines a callback function that can release a table data object when a table view is being released.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5cb57-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="5cb57-106">Header file:</span></span>  <br/> |<span data-ttu-id="5cb57-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="5cb57-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="5cb57-108">定义的函数实现方：</span><span class="sxs-lookup"><span data-stu-id="5cb57-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="5cb57-109">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="5cb57-109">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="5cb57-110">由调用的已定义函数：</span><span class="sxs-lookup"><span data-stu-id="5cb57-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="5cb57-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="5cb57-111">MAPI</span></span>  <br/> |
   
```cpp
void CALLERRELEASE(
  ULONG_PTR ulCallerData,
  LPTABLEDATA lpTblData,
  LPMAPITABLE lpVue
);
```

## <a name="parameters"></a><span data-ttu-id="5cb57-112">参数</span><span class="sxs-lookup"><span data-stu-id="5cb57-112">Parameters</span></span>

 <span data-ttu-id="5cb57-113">_ulCallerData_</span><span class="sxs-lookup"><span data-stu-id="5cb57-113">_ulCallerData_</span></span>
  
> <span data-ttu-id="5cb57-114">[in]MAPI 保存的调用方数据与表视图一起传递给 **基于 CALLERRELEASE** 的回调函数。</span><span class="sxs-lookup"><span data-stu-id="5cb57-114">[in] Caller data saved by MAPI with the table view and passed to the **CALLERRELEASE** based callback function.</span></span> <span data-ttu-id="5cb57-115">数据提供有关要发布的表视图的上下文。</span><span class="sxs-lookup"><span data-stu-id="5cb57-115">The data provides context about the table view being released.</span></span> 
    
 <span data-ttu-id="5cb57-116">_lpTblData_</span><span class="sxs-lookup"><span data-stu-id="5cb57-116">_lpTblData_</span></span>
  
> <span data-ttu-id="5cb57-117">[in]指向要发布的表视图基础的表数据对象的 [ITableData ： IUnknown](itabledataiunknown.md) 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="5cb57-117">[in] Pointer to the [ITableData : IUnknown](itabledataiunknown.md) interface for the table data object underlying the table view being released.</span></span> 
    
 <span data-ttu-id="5cb57-118">_lpVue_</span><span class="sxs-lookup"><span data-stu-id="5cb57-118">_lpVue_</span></span>
  
> <span data-ttu-id="5cb57-119">[in]指向要发布的 [表视图的 IMAPITable ： IUnknown](imapitableiunknown.md) 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="5cb57-119">[in] Pointer to the [IMAPITable : IUnknown](imapitableiunknown.md) interface for the table view being released.</span></span> <span data-ttu-id="5cb57-120">这是创建要释放的对象的 [ITableData：：HrGetView](itabledata-hrgetview.md)方法 _的 lppMAPITable_ 参数中返回的表对象的接口。</span><span class="sxs-lookup"><span data-stu-id="5cb57-120">This is an interface for the table object returned in the  _lppMAPITable_ parameter of the [ITableData::HrGetView](itabledata-hrgetview.md) method that created the object to release.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5cb57-121">返回值</span><span class="sxs-lookup"><span data-stu-id="5cb57-121">Return value</span></span>

<span data-ttu-id="5cb57-122">无</span><span class="sxs-lookup"><span data-stu-id="5cb57-122">None</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="5cb57-123">备注</span><span class="sxs-lookup"><span data-stu-id="5cb57-123">Remarks</span></span>

<span data-ttu-id="5cb57-124">已填充表数据对象的客户端应用程序或服务提供商可以调用 [ITableData：：HrGetView](itabledata-hrgetview.md) 来创建表的只读排序视图。</span><span class="sxs-lookup"><span data-stu-id="5cb57-124">A client application or service provider that has populated a table data object can call [ITableData::HrGetView](itabledata-hrgetview.md) to create a read-only, sorted view of the table.</span></span> <span data-ttu-id="5cb57-125">对 **HrGetView 的** 调用将指针传递给基于 **CALLERRELEASE** 的回调函数以及要与表视图一起保存的上下文。</span><span class="sxs-lookup"><span data-stu-id="5cb57-125">The call to **HrGetView** passes a pointer to a **CALLERRELEASE** based callback function and also a context to be saved with the table view.</span></span> <span data-ttu-id="5cb57-126">当表视图的引用计数返回零并释放视图时 **，IMAPITable** 实现将调用回调函数，在  _ulCallerData_ 参数中传递上下文。</span><span class="sxs-lookup"><span data-stu-id="5cb57-126">When the reference count of the table view returns to zero and the view is being released, the **IMAPITable** implementation calls the callback function, passing the context in the  _ulCallerData_ parameter.</span></span> 
  
<span data-ttu-id="5cb57-127">基于 **CALLERRELEASE** 的回调函数的常见用途是释放基础表数据对象，并且不需要在后续处理过程中跟踪它。</span><span class="sxs-lookup"><span data-stu-id="5cb57-127">A common use of a **CALLERRELEASE** based callback function is to release the underlying table data object and not have to keep track of it during subsequent processing.</span></span> 
  

