---
title: HrAddColumns
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8c980257-9372-4478-b635-bd91d0a66af9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 465b685038bc3d906e468c7d7b06e9c20e1fd3c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422472"
---
# <a name="hraddcolumns"></a><span data-ttu-id="905fc-103">HrAddColumns</span><span class="sxs-lookup"><span data-stu-id="905fc-103">HrAddColumns</span></span>

  
  
<span data-ttu-id="905fc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="905fc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="905fc-105">向现有表格的开头添加或移动列。</span><span class="sxs-lookup"><span data-stu-id="905fc-105">Adds or moves columns to the beginning of an existing table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="905fc-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="905fc-106">Header file:</span></span>  <br/> |<span data-ttu-id="905fc-107">mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="905fc-107">mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="905fc-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="905fc-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="905fc-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="905fc-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="905fc-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="905fc-110">Called by:</span></span>  <br/> |<span data-ttu-id="905fc-111">客户端应用程序和服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="905fc-111">Client applications and service providers.</span></span>  <br/> |
   
```cpp
HRESULT HrAddColumns(
  LPMAPITABLE lptbl,
  LPSPropTagArray lpproptagColumnsNew,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="905fc-112">参数</span><span class="sxs-lookup"><span data-stu-id="905fc-112">Parameters</span></span>

 <span data-ttu-id="905fc-113">_lptbl_</span><span class="sxs-lookup"><span data-stu-id="905fc-113">_lptbl_</span></span>
  
> <span data-ttu-id="905fc-114">[in]指向受影响的 MAPI 表的指针。</span><span class="sxs-lookup"><span data-stu-id="905fc-114">[in] Pointer to the MAPI table affected.</span></span>
    
 <span data-ttu-id="905fc-115">_lpproptagColumnsNew_</span><span class="sxs-lookup"><span data-stu-id="905fc-115">_lpproptagColumnsNew_</span></span>
  
> <span data-ttu-id="905fc-116">[in]指向 **SPropTagArray** 结构的指针，其中包含要添加或移动到表开头的属性的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="905fc-116">[in] Pointer to an **SPropTagArray** structure that contains an array of property tags for the properties to be added or moved to the beginning of the table.</span></span> 
    
 <span data-ttu-id="905fc-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="905fc-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="905fc-118">[in]指向 **MAPIAllocateBuffer 函数的** 指针。</span><span class="sxs-lookup"><span data-stu-id="905fc-118">[in] Pointer to the **MAPIAllocateBuffer** function.</span></span> <span data-ttu-id="905fc-119">用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="905fc-119">Used to allocate memory.</span></span> 
    
 <span data-ttu-id="905fc-120">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="905fc-120">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="905fc-121">[in]指向 **MAPIFreeBuffer 函数的** 指针。</span><span class="sxs-lookup"><span data-stu-id="905fc-121">[in] Pointer to the **MAPIFreeBuffer** function.</span></span> <span data-ttu-id="905fc-122">用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="905fc-122">Used to free memory.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="905fc-123">返回值</span><span class="sxs-lookup"><span data-stu-id="905fc-123">Return value</span></span>

 <span data-ttu-id="905fc-124">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="905fc-124">**S_OK**</span></span>
  
> <span data-ttu-id="905fc-125">调用成功，并移动或添加指定的列。</span><span class="sxs-lookup"><span data-stu-id="905fc-125">The call succeeded and the specified columns were moved or added.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="905fc-126">备注</span><span class="sxs-lookup"><span data-stu-id="905fc-126">Remarks</span></span>

<span data-ttu-id="905fc-127">**HrAddColumns** 函数等效于将 **HrAddColumnsEx** 与 _将 lpfnFilterColumns_ 设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="905fc-127">The **HrAddColumns** function is equivalent to using **HrAddColumnsEx** with  _lpfnFilterColumns_ set to NULL.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="905fc-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="905fc-128">See also</span></span>



[<span data-ttu-id="905fc-129">HrAddColumnsEx</span><span class="sxs-lookup"><span data-stu-id="905fc-129">HrAddColumnsEx</span></span>](hraddcolumnsex.md)
  
[<span data-ttu-id="905fc-130">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="905fc-130">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="905fc-131">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="905fc-131">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="905fc-132">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="905fc-132">SPropTagArray</span></span>](sproptagarray.md)

