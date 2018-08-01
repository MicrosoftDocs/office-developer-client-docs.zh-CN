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
ms.openlocfilehash: 28a802ffc43b08d3e2ec2be26dd98fa78f474d91
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778680"
---
# <a name="sccopynotifications"></a><span data-ttu-id="29208-103">ScCopyNotifications</span><span class="sxs-lookup"><span data-stu-id="29208-103">ScCopyNotifications</span></span>

  
  
<span data-ttu-id="29208-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="29208-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="29208-105">将一组事件通知的复制到单个块的内存。</span><span class="sxs-lookup"><span data-stu-id="29208-105">Copies a group of event notifications to a single block of memory.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="29208-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="29208-106">Header file:</span></span>  <br/> |<span data-ttu-id="29208-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="29208-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="29208-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="29208-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="29208-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="29208-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="29208-110">调用：</span><span class="sxs-lookup"><span data-stu-id="29208-110">Called by:</span></span>  <br/> |<span data-ttu-id="29208-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="29208-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCopyNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  LPVOID pvDst,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="29208-112">参数</span><span class="sxs-lookup"><span data-stu-id="29208-112">Parameters</span></span>

 <span data-ttu-id="29208-113">_cntf_</span><span class="sxs-lookup"><span data-stu-id="29208-113">_cntf_</span></span>
  
> <span data-ttu-id="29208-114">[in][通知](notification.md)结构由_rgntf_参数指示在阵列中的计数。</span><span class="sxs-lookup"><span data-stu-id="29208-114">[in] Count of [NOTIFICATION](notification.md) structures in the array indicated by the  _rgntf_ parameter.</span></span> 
    
 <span data-ttu-id="29208-115">_rgntf_</span><span class="sxs-lookup"><span data-stu-id="29208-115">_rgntf_</span></span>
  
> <span data-ttu-id="29208-116">[in]为数组定义要复制的事件通知的**通知**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="29208-116">[in] Pointer to an array of **NOTIFICATION** structures defining the event notifications to be copied.</span></span> 
    
 <span data-ttu-id="29208-117">_pvDst_</span><span class="sxs-lookup"><span data-stu-id="29208-117">_pvDst_</span></span>
  
> <span data-ttu-id="29208-118">[输出]返回的通知的指针。</span><span class="sxs-lookup"><span data-stu-id="29208-118">[out] Pointer to the returned notifications.</span></span> 
    
 <span data-ttu-id="29208-119">_pcb_</span><span class="sxs-lookup"><span data-stu-id="29208-119">_pcb_</span></span>
  
> <span data-ttu-id="29208-120">[输出]存储到其中的大小，以字节为单位的数组的_rgntf_参数指向变量的可选指针。</span><span class="sxs-lookup"><span data-stu-id="29208-120">[out] Optional pointer to a variable where the size, in bytes, of the array pointed to by the  _rgntf_ parameter is stored.</span></span> <span data-ttu-id="29208-121">如果不为 NULL， _pcb_参数设置为_pvDst_参数中存储的字节数。</span><span class="sxs-lookup"><span data-stu-id="29208-121">If not NULL, the  _pcb_ parameter is set to the number of bytes stored in the  _pvDst_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="29208-122">返回值</span><span class="sxs-lookup"><span data-stu-id="29208-122">Return value</span></span>

<span data-ttu-id="29208-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="29208-123">S_OK</span></span>
  
> <span data-ttu-id="29208-124">已成功复制事件通知。</span><span class="sxs-lookup"><span data-stu-id="29208-124">Event notifications were copied successfully.</span></span>
    
<span data-ttu-id="29208-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="29208-125">E_INVALIDARG</span></span>
  
> <span data-ttu-id="29208-126">遇到无效的通知。</span><span class="sxs-lookup"><span data-stu-id="29208-126">An invalid notification was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="29208-127">说明</span><span class="sxs-lookup"><span data-stu-id="29208-127">Remarks</span></span>

<span data-ttu-id="29208-128">如果_pcb_参数中传递 NULL，则会执行任何复制;如果在_pcb_传递一个非空值，则**ScCopyNotifications**函数将数组和阵列本身的大小复制到一个独立的内存块中。</span><span class="sxs-lookup"><span data-stu-id="29208-128">If NULL is passed in the  _pcb_ parameter, no copying is performed; if a non-null value is passed in  _pcb_, the **ScCopyNotifications** function copies the size of the array and the array itself to a single block of memory.</span></span> <span data-ttu-id="29208-129">如果_pcb_不为 NULL，则将它设置为_pvDst_参数中存储的字节数。</span><span class="sxs-lookup"><span data-stu-id="29208-129">If  _pcb_ is not NULL, it is set to the number of bytes stored in the  _pvDst_ parameter.</span></span> <span data-ttu-id="29208-130">_PvDst_参数必须为足够大，使其包含整个数组。</span><span class="sxs-lookup"><span data-stu-id="29208-130">The  _pvDst_ parameter must be large enough to contain the entire array.</span></span> 
  

