---
title: FreePadrlist
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FreePadrlist
api_type:
- COM
ms.assetid: ca8fbac6-b6f1-46ab-90a1-fc16f0d5824c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 95c2e52760bd7d65351b4dd2091b68a43cd2f97c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408640"
---
# <a name="freepadrlist"></a><span data-ttu-id="2e963-103">FreePadrlist</span><span class="sxs-lookup"><span data-stu-id="2e963-103">FreePadrlist</span></span>

  
  
<span data-ttu-id="2e963-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e963-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e963-105">销毁 [ADRLIST](adrlist.md) 结构并释放关联的内存，包括分配给所有成员数组和结构的内存。</span><span class="sxs-lookup"><span data-stu-id="2e963-105">Destroys an [ADRLIST](adrlist.md) structure and frees associated memory, including memory allocated for all member arrays and structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2e963-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2e963-106">Header file:</span></span>  <br/> |<span data-ttu-id="2e963-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="2e963-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="2e963-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="2e963-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2e963-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2e963-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2e963-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="2e963-110">Called by:</span></span>  <br/> |<span data-ttu-id="2e963-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="2e963-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void FreePadrlist(
  LPADRLIST padrlist
);
```

## <a name="parameters"></a><span data-ttu-id="2e963-112">参数</span><span class="sxs-lookup"><span data-stu-id="2e963-112">Parameters</span></span>

 <span data-ttu-id="2e963-113">_padrlist_</span><span class="sxs-lookup"><span data-stu-id="2e963-113">_padrlist_</span></span>
  
> <span data-ttu-id="2e963-114">[in]指向要 **销毁的 ADRLIST** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="2e963-114">[in] Pointer to the **ADRLIST** structure to be destroyed.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2e963-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2e963-115">Return value</span></span>

<span data-ttu-id="2e963-116">无。</span><span class="sxs-lookup"><span data-stu-id="2e963-116">None.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="2e963-117">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2e963-117">Notes to callers</span></span>

<span data-ttu-id="2e963-118">作为 **FreePadrlist** 实现一部分 [，MAPI 调用 MAPIFreeBuffer](mapifreebuffer.md) 函数以释放 **ADRLIST** 结构的每一项，然后再释放整个结构。</span><span class="sxs-lookup"><span data-stu-id="2e963-118">As part of its implementation of **FreePadrlist**, MAPI calls the [MAPIFreeBuffer](mapifreebuffer.md) function to free every entry in the **ADRLIST** structure before freeing the complete structure.</span></span> <span data-ttu-id="2e963-119">因此，所有此类条目都必须遵循 [ADRLIST](adrlist.md) 结构的分配规则，并针对每个成员数组和结构使用单个 [MAPIAllocateBuffer](mapiallocatebuffer.md) 调用。</span><span class="sxs-lookup"><span data-stu-id="2e963-119">Therefore all such entries must have followed the allocation rules for the [ADRLIST](adrlist.md) structure, using an individual [MAPIAllocateBuffer](mapiallocatebuffer.md) call for each member array and structure.</span></span> 
  
<span data-ttu-id="2e963-120">有关为 **ADRLIST** 和 **SRowSet** 结构分配内存的信息，请参阅 [管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="2e963-120">For more information about allocating memory for **ADRLIST** and **SRowSet** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="2e963-121">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="2e963-121">MFCMAPI reference</span></span>

<span data-ttu-id="2e963-122">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2e963-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2e963-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="2e963-123">**File**</span></span>|<span data-ttu-id="2e963-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="2e963-124">**Function**</span></span>|<span data-ttu-id="2e963-125">**备注**</span><span class="sxs-lookup"><span data-stu-id="2e963-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e963-126">MAPIABFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="2e963-126">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="2e963-127">AddOneOffAddress</span><span class="sxs-lookup"><span data-stu-id="2e963-127">AddOneOffAddress</span></span>  <br/> |<span data-ttu-id="2e963-128">MFCMAPI 使用 **FreePadrlist** 方法释放 ADRLIST 结构，该结构构建为向邮件添加一次地址。</span><span class="sxs-lookup"><span data-stu-id="2e963-128">MFCMAPI uses the **FreePadrlist** method to free an ADRLIST structure that was built to add a one-off address to a message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2e963-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e963-129">See also</span></span>



[<span data-ttu-id="2e963-130">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="2e963-130">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

