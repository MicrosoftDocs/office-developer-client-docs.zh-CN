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
ms.openlocfilehash: ffc47e924b7a0f94db66adbffe01b2cdc619dc8c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580731"
---
# <a name="hraddcolumns"></a><span data-ttu-id="5389d-103">HrAddColumns</span><span class="sxs-lookup"><span data-stu-id="5389d-103">HrAddColumns</span></span>

  
  
<span data-ttu-id="5389d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5389d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5389d-105">添加或移到现有表的起点的列。</span><span class="sxs-lookup"><span data-stu-id="5389d-105">Adds or moves columns to the beginning of an existing table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5389d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="5389d-106">Header file:</span></span>  <br/> |<span data-ttu-id="5389d-107">mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="5389d-107">mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="5389d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="5389d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="5389d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="5389d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="5389d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="5389d-110">Called by:</span></span>  <br/> |<span data-ttu-id="5389d-111">客户端应用程序和服务提供商。</span><span class="sxs-lookup"><span data-stu-id="5389d-111">Client applications and service providers.</span></span>  <br/> |
   
```cpp
HRESULT HrAddColumns(
  LPMAPITABLE lptbl,
  LPSPropTagArray lpproptagColumnsNew,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="5389d-112">参数</span><span class="sxs-lookup"><span data-stu-id="5389d-112">Parameters</span></span>

 <span data-ttu-id="5389d-113">_lptbl_</span><span class="sxs-lookup"><span data-stu-id="5389d-113">_lptbl_</span></span>
  
> <span data-ttu-id="5389d-114">[in]指向受影响的 MAPI 表。</span><span class="sxs-lookup"><span data-stu-id="5389d-114">[in] Pointer to the MAPI table affected.</span></span>
    
 <span data-ttu-id="5389d-115">_lpproptagColumnsNew_</span><span class="sxs-lookup"><span data-stu-id="5389d-115">_lpproptagColumnsNew_</span></span>
  
> <span data-ttu-id="5389d-116">[in]指向**SPropTagArray**结构，其中包含要添加或移至表格的开头的属性的属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="5389d-116">[in] Pointer to an **SPropTagArray** structure that contains an array of property tags for the properties to be added or moved to the beginning of the table.</span></span> 
    
 <span data-ttu-id="5389d-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="5389d-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="5389d-118">[in]指向**MAPIAllocateBuffer**函数指针。</span><span class="sxs-lookup"><span data-stu-id="5389d-118">[in] Pointer to the **MAPIAllocateBuffer** function.</span></span> <span data-ttu-id="5389d-119">用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="5389d-119">Used to allocate memory.</span></span> 
    
 <span data-ttu-id="5389d-120">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="5389d-120">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="5389d-121">[in]指向**MAPIFreeBuffer**函数指针。</span><span class="sxs-lookup"><span data-stu-id="5389d-121">[in] Pointer to the **MAPIFreeBuffer** function.</span></span> <span data-ttu-id="5389d-122">使用以释放内存。</span><span class="sxs-lookup"><span data-stu-id="5389d-122">Used to free memory.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5389d-123">返回值</span><span class="sxs-lookup"><span data-stu-id="5389d-123">Return value</span></span>

 <span data-ttu-id="5389d-124">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="5389d-124">**S_OK**</span></span>
  
> <span data-ttu-id="5389d-125">调用成功，并指定的列已移动或添加。</span><span class="sxs-lookup"><span data-stu-id="5389d-125">The call succeeded and the specified columns were moved or added.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5389d-126">注解</span><span class="sxs-lookup"><span data-stu-id="5389d-126">Remarks</span></span>

<span data-ttu-id="5389d-127">**HrAddColumns**函数等效于**HrAddColumnsEx**使用_lpfnFilterColumns_设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="5389d-127">The **HrAddColumns** function is equivalent to using **HrAddColumnsEx** with  _lpfnFilterColumns_ set to NULL.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5389d-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5389d-128">See also</span></span>



[<span data-ttu-id="5389d-129">HrAddColumnsEx</span><span class="sxs-lookup"><span data-stu-id="5389d-129">HrAddColumnsEx</span></span>](hraddcolumnsex.md)
  
[<span data-ttu-id="5389d-130">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="5389d-130">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="5389d-131">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="5389d-131">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="5389d-132">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="5389d-132">SPropTagArray</span></span>](sproptagarray.md)

