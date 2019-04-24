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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331841"
---
# <a name="callerrelease"></a><span data-ttu-id="c0cf3-103">CALLERRELEASE</span><span class="sxs-lookup"><span data-stu-id="c0cf3-103">CALLERRELEASE</span></span>

  
  
<span data-ttu-id="c0cf3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c0cf3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c0cf3-105">定义在释放表视图时可释放表数据对象的回调函数。</span><span class="sxs-lookup"><span data-stu-id="c0cf3-105">Defines a callback function that can release a table data object when a table view is being released.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c0cf3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c0cf3-106">Header file:</span></span>  <br/> |<span data-ttu-id="c0cf3-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="c0cf3-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="c0cf3-108">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="c0cf3-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="c0cf3-109">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="c0cf3-109">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="c0cf3-110">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="c0cf3-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="c0cf3-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="c0cf3-111">MAPI</span></span>  <br/> |
   
```cpp
void CALLERRELEASE(
  ULONG_PTR ulCallerData,
  LPTABLEDATA lpTblData,
  LPMAPITABLE lpVue
);
```

## <a name="parameters"></a><span data-ttu-id="c0cf3-112">参数</span><span class="sxs-lookup"><span data-stu-id="c0cf3-112">Parameters</span></span>

 <span data-ttu-id="c0cf3-113">_ulCallerData_</span><span class="sxs-lookup"><span data-stu-id="c0cf3-113">_ulCallerData_</span></span>
  
> <span data-ttu-id="c0cf3-114">实时由 MAPI 保存在表视图中并传递给基于**CALLERRELEASE**的回调函数的调用方数据。</span><span class="sxs-lookup"><span data-stu-id="c0cf3-114">[in] Caller data saved by MAPI with the table view and passed to the **CALLERRELEASE** based callback function.</span></span> <span data-ttu-id="c0cf3-115">数据提供有关要释放的表视图的上下文。</span><span class="sxs-lookup"><span data-stu-id="c0cf3-115">The data provides context about the table view being released.</span></span> 
    
 <span data-ttu-id="c0cf3-116">_lpTblData_</span><span class="sxs-lookup"><span data-stu-id="c0cf3-116">_lpTblData_</span></span>
  
> <span data-ttu-id="c0cf3-117">实时指向要释放的表视图基础的表数据对象的[ITableData: IUnknown](itabledataiunknown.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="c0cf3-117">[in] Pointer to the [ITableData : IUnknown](itabledataiunknown.md) interface for the table data object underlying the table view being released.</span></span> 
    
 <span data-ttu-id="c0cf3-118">_lpVue_</span><span class="sxs-lookup"><span data-stu-id="c0cf3-118">_lpVue_</span></span>
  
> <span data-ttu-id="c0cf3-119">实时指向要释放的表视图的[IMAPITable: IUnknown](imapitableiunknown.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="c0cf3-119">[in] Pointer to the [IMAPITable : IUnknown](imapitableiunknown.md) interface for the table view being released.</span></span> <span data-ttu-id="c0cf3-120">这是在创建要释放的对象的[ITableData:: HrGetView](itabledata-hrgetview.md)方法的_lppMAPITable_参数中返回的 table 对象的接口。</span><span class="sxs-lookup"><span data-stu-id="c0cf3-120">This is an interface for the table object returned in the  _lppMAPITable_ parameter of the [ITableData::HrGetView](itabledata-hrgetview.md) method that created the object to release.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c0cf3-121">返回值</span><span class="sxs-lookup"><span data-stu-id="c0cf3-121">Return value</span></span>

<span data-ttu-id="c0cf3-122">无</span><span class="sxs-lookup"><span data-stu-id="c0cf3-122">None</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c0cf3-123">注解</span><span class="sxs-lookup"><span data-stu-id="c0cf3-123">Remarks</span></span>

<span data-ttu-id="c0cf3-124">填充了 table data 对象的客户端应用程序或服务提供程序可以调用[ITableData:: HrGetView](itabledata-hrgetview.md)以创建表的只读、排序视图。</span><span class="sxs-lookup"><span data-stu-id="c0cf3-124">A client application or service provider that has populated a table data object can call [ITableData::HrGetView](itabledata-hrgetview.md) to create a read-only, sorted view of the table.</span></span> <span data-ttu-id="c0cf3-125">对**HrGetView**的调用会将指针传递给基于**CALLERRELEASE**的回调函数, 还会传递与表视图一起保存的上下文。</span><span class="sxs-lookup"><span data-stu-id="c0cf3-125">The call to **HrGetView** passes a pointer to a **CALLERRELEASE** based callback function and also a context to be saved with the table view.</span></span> <span data-ttu-id="c0cf3-126">当表视图的引用计数返回到零, 并且正在释放视图时, **IMAPITable**实现将调用回调函数, 并在_ulCallerData_参数中传递上下文。</span><span class="sxs-lookup"><span data-stu-id="c0cf3-126">When the reference count of the table view returns to zero and the view is being released, the **IMAPITable** implementation calls the callback function, passing the context in the  _ulCallerData_ parameter.</span></span> 
  
<span data-ttu-id="c0cf3-127">基于**CALLERRELEASE**的回调函数的常见用途是释放基础表数据对象, 而无需在后续处理期间对其进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="c0cf3-127">A common use of a **CALLERRELEASE** based callback function is to release the underlying table data object and not have to keep track of it during subsequent processing.</span></span> 
  

