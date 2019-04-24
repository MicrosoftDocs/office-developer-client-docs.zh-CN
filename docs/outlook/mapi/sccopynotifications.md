---
title: ScCopyNotifications
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScCopyNotifications
api_type:
- COM
ms.assetid: ac31cf65-a2bc-4c8e-91a4-d2903aa98776
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 08b9b954f856d64214947d81cf700adee42bcce4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357482"
---
# <a name="sccopynotifications"></a><span data-ttu-id="028fc-103">ScCopyNotifications</span><span class="sxs-lookup"><span data-stu-id="028fc-103">ScCopyNotifications</span></span>

  
  
<span data-ttu-id="028fc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="028fc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="028fc-105">将一组事件通知复制到单个内存块。</span><span class="sxs-lookup"><span data-stu-id="028fc-105">Copies a group of event notifications to a single block of memory.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="028fc-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="028fc-106">Header file:</span></span>  <br/> |<span data-ttu-id="028fc-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="028fc-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="028fc-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="028fc-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="028fc-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="028fc-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="028fc-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="028fc-110">Called by:</span></span>  <br/> |<span data-ttu-id="028fc-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="028fc-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCopyNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  LPVOID pvDst,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="028fc-112">参数</span><span class="sxs-lookup"><span data-stu-id="028fc-112">Parameters</span></span>

 <span data-ttu-id="028fc-113">_cntf_</span><span class="sxs-lookup"><span data-stu-id="028fc-113">_cntf_</span></span>
  
> <span data-ttu-id="028fc-114">实时由_rgntf_参数指示的数组中的[通知](notification.md)结构的计数。</span><span class="sxs-lookup"><span data-stu-id="028fc-114">[in] Count of [NOTIFICATION](notification.md) structures in the array indicated by the  _rgntf_ parameter.</span></span> 
    
 <span data-ttu-id="028fc-115">_rgntf_</span><span class="sxs-lookup"><span data-stu-id="028fc-115">_rgntf_</span></span>
  
> <span data-ttu-id="028fc-116">实时指向定义要复制的事件通知的**通知**结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="028fc-116">[in] Pointer to an array of **NOTIFICATION** structures defining the event notifications to be copied.</span></span> 
    
 <span data-ttu-id="028fc-117">_pvDst_</span><span class="sxs-lookup"><span data-stu-id="028fc-117">_pvDst_</span></span>
  
> <span data-ttu-id="028fc-118">排除指向返回的通知的指针。</span><span class="sxs-lookup"><span data-stu-id="028fc-118">[out] Pointer to the returned notifications.</span></span> 
    
 <span data-ttu-id="028fc-119">_pcb_</span><span class="sxs-lookup"><span data-stu-id="028fc-119">_pcb_</span></span>
  
> <span data-ttu-id="028fc-120">排除一个可选指针, 指向一个变量, 存储_rgntf_参数指向的数组的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="028fc-120">[out] Optional pointer to a variable where the size, in bytes, of the array pointed to by the  _rgntf_ parameter is stored.</span></span> <span data-ttu-id="028fc-121">如果不为 NULL, 则将_pcb_参数设置为_pvDst_参数中存储的字节数。</span><span class="sxs-lookup"><span data-stu-id="028fc-121">If not NULL, the  _pcb_ parameter is set to the number of bytes stored in the  _pvDst_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="028fc-122">返回值</span><span class="sxs-lookup"><span data-stu-id="028fc-122">Return value</span></span>

<span data-ttu-id="028fc-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="028fc-123">S_OK</span></span>
  
> <span data-ttu-id="028fc-124">已成功复制事件通知。</span><span class="sxs-lookup"><span data-stu-id="028fc-124">Event notifications were copied successfully.</span></span>
    
<span data-ttu-id="028fc-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="028fc-125">E_INVALIDARG</span></span>
  
> <span data-ttu-id="028fc-126">遇到无效的通知。</span><span class="sxs-lookup"><span data-stu-id="028fc-126">An invalid notification was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="028fc-127">注解</span><span class="sxs-lookup"><span data-stu-id="028fc-127">Remarks</span></span>

<span data-ttu-id="028fc-128">如果在_pcb_参数中传递了 NULL 值, 则不会执行任何复制;如果在_pcb_中传递一个非 null 值, 则**ScCopyNotifications**函数会将数组和数组本身的大小复制到单个内存块。</span><span class="sxs-lookup"><span data-stu-id="028fc-128">If NULL is passed in the  _pcb_ parameter, no copying is performed; if a non-null value is passed in  _pcb_, the **ScCopyNotifications** function copies the size of the array and the array itself to a single block of memory.</span></span> <span data-ttu-id="028fc-129">如果_pcb_不为 NULL, 则将其设置为_pvDst_参数中存储的字节数。</span><span class="sxs-lookup"><span data-stu-id="028fc-129">If  _pcb_ is not NULL, it is set to the number of bytes stored in the  _pvDst_ parameter.</span></span> <span data-ttu-id="028fc-130">_pvDst_参数的大小必须足以包含整个数组。</span><span class="sxs-lookup"><span data-stu-id="028fc-130">The  _pvDst_ parameter must be large enough to contain the entire array.</span></span> 
  

