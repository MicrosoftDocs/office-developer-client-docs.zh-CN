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
ms.openlocfilehash: dc7fa8b546783819b701604a5e489f0fd030ae86
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775136"
---
# <a name="hraddcolumns"></a><span data-ttu-id="4af20-103">HrAddColumns</span><span class="sxs-lookup"><span data-stu-id="4af20-103">HrAddColumns</span></span>

  
  
<span data-ttu-id="4af20-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4af20-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4af20-105">添加或移到现有表的起点的列。</span><span class="sxs-lookup"><span data-stu-id="4af20-105">Adds or moves columns to the beginning of an existing table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4af20-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="4af20-106">Header file:</span></span>  <br/> |<span data-ttu-id="4af20-107">mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="4af20-107">mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="4af20-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="4af20-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="4af20-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="4af20-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="4af20-110">调用：</span><span class="sxs-lookup"><span data-stu-id="4af20-110">Called by:</span></span>  <br/> |<span data-ttu-id="4af20-111">客户端应用程序和服务提供商。</span><span class="sxs-lookup"><span data-stu-id="4af20-111">Client applications and service providers.</span></span>  <br/> |
   
```cpp
HRESULT HrAddColumns(
  LPMAPITABLE lptbl,
  LPSPropTagArray lpproptagColumnsNew,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="4af20-112">参数</span><span class="sxs-lookup"><span data-stu-id="4af20-112">Parameters</span></span>

 <span data-ttu-id="4af20-113">_lptbl_</span><span class="sxs-lookup"><span data-stu-id="4af20-113">_lptbl_</span></span>
  
> <span data-ttu-id="4af20-114">[in]指向受影响的 MAPI 表。</span><span class="sxs-lookup"><span data-stu-id="4af20-114">[in] Pointer to the MAPI table affected.</span></span>
    
 <span data-ttu-id="4af20-115">_lpproptagColumnsNew_</span><span class="sxs-lookup"><span data-stu-id="4af20-115">_lpproptagColumnsNew_</span></span>
  
> <span data-ttu-id="4af20-116">[in]指向**SPropTagArray**结构，其中包含要添加或移至表格的开头的属性的属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="4af20-116">[in] Pointer to an **SPropTagArray** structure that contains an array of property tags for the properties to be added or moved to the beginning of the table.</span></span> 
    
 <span data-ttu-id="4af20-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="4af20-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="4af20-118">[in]指向**MAPIAllocateBuffer**函数指针。</span><span class="sxs-lookup"><span data-stu-id="4af20-118">[in] Pointer to the **MAPIAllocateBuffer** function.</span></span> <span data-ttu-id="4af20-119">用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="4af20-119">Used to allocate memory.</span></span> 
    
 <span data-ttu-id="4af20-120">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="4af20-120">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="4af20-121">[in]指向**MAPIFreeBuffer**函数指针。</span><span class="sxs-lookup"><span data-stu-id="4af20-121">[in] Pointer to the **MAPIFreeBuffer** function.</span></span> <span data-ttu-id="4af20-122">使用以释放内存。</span><span class="sxs-lookup"><span data-stu-id="4af20-122">Used to free memory.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="4af20-123">返回值</span><span class="sxs-lookup"><span data-stu-id="4af20-123">Return value</span></span>

 <span data-ttu-id="4af20-124">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="4af20-124">**S_OK**</span></span>
  
> <span data-ttu-id="4af20-125">调用成功，并指定的列已移动或添加。</span><span class="sxs-lookup"><span data-stu-id="4af20-125">The call succeeded and the specified columns were moved or added.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4af20-126">说明</span><span class="sxs-lookup"><span data-stu-id="4af20-126">Remarks</span></span>

<span data-ttu-id="4af20-127">**HrAddColumns**函数等效于**HrAddColumnsEx**使用_lpfnFilterColumns_设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4af20-127">The **HrAddColumns** function is equivalent to using **HrAddColumnsEx** with  _lpfnFilterColumns_ set to NULL.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4af20-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4af20-128">See also</span></span>



[<span data-ttu-id="4af20-129">HrAddColumnsEx</span><span class="sxs-lookup"><span data-stu-id="4af20-129">HrAddColumnsEx</span></span>](hraddcolumnsex.md)
  
[<span data-ttu-id="4af20-130">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="4af20-130">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="4af20-131">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="4af20-131">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="4af20-132">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="4af20-132">SPropTagArray</span></span>](sproptagarray.md)

