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
# <a name="hraddcolumns"></a><span data-ttu-id="18d22-103">HrAddColumns</span><span class="sxs-lookup"><span data-stu-id="18d22-103">HrAddColumns</span></span>

  
  
<span data-ttu-id="18d22-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="18d22-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="18d22-105">将列添加或移动到现有表的开头。</span><span class="sxs-lookup"><span data-stu-id="18d22-105">Adds or moves columns to the beginning of an existing table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="18d22-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="18d22-106">Header file:</span></span>  <br/> |<span data-ttu-id="18d22-107">mapiutil</span><span class="sxs-lookup"><span data-stu-id="18d22-107">mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="18d22-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="18d22-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="18d22-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="18d22-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="18d22-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="18d22-110">Called by:</span></span>  <br/> |<span data-ttu-id="18d22-111">客户端应用程序和服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="18d22-111">Client applications and service providers.</span></span>  <br/> |
   
```cpp
HRESULT HrAddColumns(
  LPMAPITABLE lptbl,
  LPSPropTagArray lpproptagColumnsNew,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="18d22-112">参数</span><span class="sxs-lookup"><span data-stu-id="18d22-112">Parameters</span></span>

 <span data-ttu-id="18d22-113">_lptbl_</span><span class="sxs-lookup"><span data-stu-id="18d22-113">_lptbl_</span></span>
  
> <span data-ttu-id="18d22-114">实时指向受影响的 MAPI 表的指针。</span><span class="sxs-lookup"><span data-stu-id="18d22-114">[in] Pointer to the MAPI table affected.</span></span>
    
 <span data-ttu-id="18d22-115">_lpproptagColumnsNew_</span><span class="sxs-lookup"><span data-stu-id="18d22-115">_lpproptagColumnsNew_</span></span>
  
> <span data-ttu-id="18d22-116">实时指向**SPropTagArray**结构的指针, 该结构包含要添加或移动到表开头的属性的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="18d22-116">[in] Pointer to an **SPropTagArray** structure that contains an array of property tags for the properties to be added or moved to the beginning of the table.</span></span> 
    
 <span data-ttu-id="18d22-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="18d22-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="18d22-118">实时指向**MAPIAllocateBuffer**函数的指针。</span><span class="sxs-lookup"><span data-stu-id="18d22-118">[in] Pointer to the **MAPIAllocateBuffer** function.</span></span> <span data-ttu-id="18d22-119">用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="18d22-119">Used to allocate memory.</span></span> 
    
 <span data-ttu-id="18d22-120">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="18d22-120">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="18d22-121">实时指向**MAPIFreeBuffer**函数的指针。</span><span class="sxs-lookup"><span data-stu-id="18d22-121">[in] Pointer to the **MAPIFreeBuffer** function.</span></span> <span data-ttu-id="18d22-122">用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="18d22-122">Used to free memory.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="18d22-123">返回值</span><span class="sxs-lookup"><span data-stu-id="18d22-123">Return value</span></span>

 <span data-ttu-id="18d22-124">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="18d22-124">**S_OK**</span></span>
  
> <span data-ttu-id="18d22-125">调用成功, 并已移动或添加指定的列。</span><span class="sxs-lookup"><span data-stu-id="18d22-125">The call succeeded and the specified columns were moved or added.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="18d22-126">说明</span><span class="sxs-lookup"><span data-stu-id="18d22-126">Remarks</span></span>

<span data-ttu-id="18d22-127">**HrAddColumns**函数等效于使用_lpfnFilterColumns_设置为 NULL 的**HrAddColumnsEx** 。</span><span class="sxs-lookup"><span data-stu-id="18d22-127">The **HrAddColumns** function is equivalent to using **HrAddColumnsEx** with  _lpfnFilterColumns_ set to NULL.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="18d22-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18d22-128">See also</span></span>



[<span data-ttu-id="18d22-129">HrAddColumnsEx</span><span class="sxs-lookup"><span data-stu-id="18d22-129">HrAddColumnsEx</span></span>](hraddcolumnsex.md)
  
[<span data-ttu-id="18d22-130">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="18d22-130">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="18d22-131">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="18d22-131">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="18d22-132">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="18d22-132">SPropTagArray</span></span>](sproptagarray.md)

