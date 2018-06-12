---
title: ScRelocNotifications
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScRelocNotifications
api_type:
- COM
ms.assetid: 22de5d38-7be6-48b3-90a7-bc553dcdb042
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bb4ff6a128b9fed29ff0be5325c21e5600389740
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778732"
---
# <a name="screlocnotifications"></a><span data-ttu-id="988aa-103">ScRelocNotifications</span><span class="sxs-lookup"><span data-stu-id="988aa-103">ScRelocNotifications</span></span>

  
  
<span data-ttu-id="988aa-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="988aa-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="988aa-105">调整指定的事件通知阵列中的指针。</span><span class="sxs-lookup"><span data-stu-id="988aa-105">Adjusts a pointer within a specified event notification array.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="988aa-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="988aa-106">Header file:</span></span>  <br/> |<span data-ttu-id="988aa-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="988aa-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="988aa-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="988aa-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="988aa-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="988aa-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="988aa-110">调用：</span><span class="sxs-lookup"><span data-stu-id="988aa-110">Called by:</span></span>  <br/> |<span data-ttu-id="988aa-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="988aa-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScRelocNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  LPVOID pvBaseOld,
  LPVOID pvBaseNew,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="988aa-112">参数</span><span class="sxs-lookup"><span data-stu-id="988aa-112">Parameters</span></span>

 <span data-ttu-id="988aa-113">_cntf_</span><span class="sxs-lookup"><span data-stu-id="988aa-113">_cntf_</span></span>
  
> <span data-ttu-id="988aa-114">[in][通知](notification.md)结构由_rgntf_参数指示在阵列中的计数。</span><span class="sxs-lookup"><span data-stu-id="988aa-114">[in] Count of [NOTIFICATION](notification.md) structures in the array indicated by the  _rgntf_ parameter.</span></span> 
    
 <span data-ttu-id="988aa-115">_rgntf_</span><span class="sxs-lookup"><span data-stu-id="988aa-115">_rgntf_</span></span>
  
> <span data-ttu-id="988aa-116">[in]定义在其中指针是要调整的事件通知的**通知**结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="988aa-116">[in] Pointer to the array of **NOTIFICATION** structures defining event notifications within which a pointer is to be adjusted.</span></span> 
    
 <span data-ttu-id="988aa-117">_pvBaseOld_</span><span class="sxs-lookup"><span data-stu-id="988aa-117">_pvBaseOld_</span></span>
  
> <span data-ttu-id="988aa-118">[in]指向原始基址_rgntf_参数指示的数组。</span><span class="sxs-lookup"><span data-stu-id="988aa-118">[in] Pointer to the original base address of the array indicated by the  _rgntf_ parameter.</span></span> 
    
 <span data-ttu-id="988aa-119">_pvBaseNew_</span><span class="sxs-lookup"><span data-stu-id="988aa-119">_pvBaseNew_</span></span>
  
> <span data-ttu-id="988aa-120">[in]**ScRelocNotifications**向其中写入_rgntf_参数指示的数组的新基址位置。</span><span class="sxs-lookup"><span data-stu-id="988aa-120">[in] The location to which **ScRelocNotifications** writes the new base address of the array indicated by the  _rgntf_ parameter.</span></span> 
    
 <span data-ttu-id="988aa-121">_pcb_</span><span class="sxs-lookup"><span data-stu-id="988aa-121">_pcb_</span></span>
  
> <span data-ttu-id="988aa-122">[输出]指向的大小，以字节为单位指示_pvBaseNew_参数的数组。</span><span class="sxs-lookup"><span data-stu-id="988aa-122">[out] Pointer to the size, in bytes, of the array indicated by the  _pvBaseNew_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="988aa-123">返回值</span><span class="sxs-lookup"><span data-stu-id="988aa-123">Return value</span></span>

<span data-ttu-id="988aa-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="988aa-124">S_OK</span></span>
  
> <span data-ttu-id="988aa-125">已成功调整指针。</span><span class="sxs-lookup"><span data-stu-id="988aa-125">A pointer was adjusted successfully.</span></span>
    
<span data-ttu-id="988aa-126">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="988aa-126">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="988aa-127">遇到无效的通知。</span><span class="sxs-lookup"><span data-stu-id="988aa-127">An invalid notification was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="988aa-128">备注</span><span class="sxs-lookup"><span data-stu-id="988aa-128">Remarks</span></span>

<span data-ttu-id="988aa-129">**ScRelocNotifications**函数_pcb_参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="988aa-129">The  _pcb_ parameter to the **ScRelocNotifications** function is optional.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="988aa-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="988aa-130">See also</span></span>



[<span data-ttu-id="988aa-131">ScRelocProps</span><span class="sxs-lookup"><span data-stu-id="988aa-131">ScRelocProps</span></span>](screlocprops.md)

