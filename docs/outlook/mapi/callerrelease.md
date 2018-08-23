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
ms.openlocfilehash: e97e1d5302d8247cb09ce7cb1b581582405300a5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568125"
---
# <a name="callerrelease"></a><span data-ttu-id="957cd-103">CALLERRELEASE</span><span class="sxs-lookup"><span data-stu-id="957cd-103">CALLERRELEASE</span></span>

  
  
<span data-ttu-id="957cd-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="957cd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="957cd-105">定义一个在释放表视图时，可以释放表数据对象的回调函数。</span><span class="sxs-lookup"><span data-stu-id="957cd-105">Defines a callback function that can release a table data object when a table view is being released.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="957cd-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="957cd-106">Header file:</span></span>  <br/> |<span data-ttu-id="957cd-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="957cd-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="957cd-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="957cd-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="957cd-109">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="957cd-109">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="957cd-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="957cd-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="957cd-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="957cd-111">MAPI</span></span>  <br/> |
   
```cpp
void CALLERRELEASE(
  ULONG_PTR ulCallerData,
  LPTABLEDATA lpTblData,
  LPMAPITABLE lpVue
);
```

## <a name="parameters"></a><span data-ttu-id="957cd-112">参数</span><span class="sxs-lookup"><span data-stu-id="957cd-112">Parameters</span></span>

 <span data-ttu-id="957cd-113">_ulCallerData_</span><span class="sxs-lookup"><span data-stu-id="957cd-113">_ulCallerData_</span></span>
  
> <span data-ttu-id="957cd-114">[in]呼叫者数据，由 MAPI 保存与表视图并传递给**CALLERRELEASE**基于回调函数。</span><span class="sxs-lookup"><span data-stu-id="957cd-114">[in] Caller data saved by MAPI with the table view and passed to the **CALLERRELEASE** based callback function.</span></span> <span data-ttu-id="957cd-115">数据提供有关要发布的表视图的上下文。</span><span class="sxs-lookup"><span data-stu-id="957cd-115">The data provides context about the table view being released.</span></span> 
    
 <span data-ttu-id="957cd-116">_lpTblData_</span><span class="sxs-lookup"><span data-stu-id="957cd-116">_lpTblData_</span></span>
  
> <span data-ttu-id="957cd-117">[in]指向[ITableData: IUnknown](itabledataiunknown.md)基础正在发布表视图的表数据对象的接口。</span><span class="sxs-lookup"><span data-stu-id="957cd-117">[in] Pointer to the [ITableData : IUnknown](itabledataiunknown.md) interface for the table data object underlying the table view being released.</span></span> 
    
 <span data-ttu-id="957cd-118">_lpVue_</span><span class="sxs-lookup"><span data-stu-id="957cd-118">_lpVue_</span></span>
  
> <span data-ttu-id="957cd-119">[in]指向[IMAPITable: IUnknown](imapitableiunknown.md)正在发布表视图的接口。</span><span class="sxs-lookup"><span data-stu-id="957cd-119">[in] Pointer to the [IMAPITable : IUnknown](imapitableiunknown.md) interface for the table view being released.</span></span> <span data-ttu-id="957cd-120">这是用于创建要释放的对象的[ITableData::HrGetView](itabledata-hrgetview.md)方法的_lppMAPITable_参数中返回的 table 对象的接口。</span><span class="sxs-lookup"><span data-stu-id="957cd-120">This is an interface for the table object returned in the  _lppMAPITable_ parameter of the [ITableData::HrGetView](itabledata-hrgetview.md) method that created the object to release.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="957cd-121">返回值</span><span class="sxs-lookup"><span data-stu-id="957cd-121">Return value</span></span>

<span data-ttu-id="957cd-122">无</span><span class="sxs-lookup"><span data-stu-id="957cd-122">None</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="957cd-123">注解</span><span class="sxs-lookup"><span data-stu-id="957cd-123">Remarks</span></span>

<span data-ttu-id="957cd-124">客户端应用程序或已填充表数据对象的服务提供商可以调用[ITableData::HrGetView](itabledata-hrgetview.md)创建只读、 已排序的表的视图。</span><span class="sxs-lookup"><span data-stu-id="957cd-124">A client application or service provider that has populated a table data object can call [ITableData::HrGetView](itabledata-hrgetview.md) to create a read-only, sorted view of the table.</span></span> <span data-ttu-id="957cd-125">对**HrGetView**的调用将指针传递给**CALLERRELEASE**基于回调函数以及与表视图保存的上下文。</span><span class="sxs-lookup"><span data-stu-id="957cd-125">The call to **HrGetView** passes a pointer to a **CALLERRELEASE** based callback function and also a context to be saved with the table view.</span></span> <span data-ttu-id="957cd-126">当表视图的引用计数返回为零，即被释放视图**IMAPITable**实现调用_ulCallerData_参数中传递上下文的回调函数。</span><span class="sxs-lookup"><span data-stu-id="957cd-126">When the reference count of the table view returns to zero and the view is being released, the **IMAPITable** implementation calls the callback function, passing the context in the  _ulCallerData_ parameter.</span></span> 
  
<span data-ttu-id="957cd-127">**CALLERRELEASE**基于回调函数的一个常见用途是发行版基础表数据对象并没有以跟踪其后续处理过程中。</span><span class="sxs-lookup"><span data-stu-id="957cd-127">A common use of a **CALLERRELEASE** based callback function is to release the underlying table data object and not have to keep track of it during subsequent processing.</span></span> 
  

