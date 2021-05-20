---
title: FreeProws
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FreeProws
api_type:
- HeaderDef
ms.assetid: 0f8f9fc4-4940-4c0a-92cc-2a6409b9a13f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b1109b3201e1b1e4a78c3a0fe0f2eb4d0cd43c05
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438818"
---
# <a name="freeprows"></a><span data-ttu-id="6bebe-103">FreeProws</span><span class="sxs-lookup"><span data-stu-id="6bebe-103">FreeProws</span></span>

  
  
<span data-ttu-id="6bebe-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6bebe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6bebe-105">销毁 [SRowSet](srowset.md) 结构并释放关联的内存，包括分配给所有成员数组和结构的内存。</span><span class="sxs-lookup"><span data-stu-id="6bebe-105">Destroys an [SRowSet](srowset.md) structure and frees associated memory, including memory allocated for all member arrays and structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6bebe-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6bebe-106">Header file:</span></span>  <br/> |<span data-ttu-id="6bebe-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="6bebe-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="6bebe-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="6bebe-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="6bebe-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="6bebe-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="6bebe-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="6bebe-110">Called by:</span></span>  <br/> |<span data-ttu-id="6bebe-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="6bebe-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void FreeProws(
  LPSRowSet prows
);
```

## <a name="parameters"></a><span data-ttu-id="6bebe-112">参数</span><span class="sxs-lookup"><span data-stu-id="6bebe-112">Parameters</span></span>

 <span data-ttu-id="6bebe-113">_prows_</span><span class="sxs-lookup"><span data-stu-id="6bebe-113">_prows_</span></span>
  
> <span data-ttu-id="6bebe-114">[in]指向要 **销毁的 SRowSet** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="6bebe-114">[in] Pointer to the **SRowSet** structure to be destroyed.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="6bebe-115">返回值</span><span class="sxs-lookup"><span data-stu-id="6bebe-115">Return value</span></span>

<span data-ttu-id="6bebe-116">无。</span><span class="sxs-lookup"><span data-stu-id="6bebe-116">None.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="6bebe-117">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="6bebe-117">Notes to callers</span></span>

<span data-ttu-id="6bebe-118">在 **FreeProws** 的实现过程中 [，MAPI 调用 MAPIFreeBuffer](mapifreebuffer.md) 函数以释放 **SRowSet** 结构的每一项，然后再释放整个结构。</span><span class="sxs-lookup"><span data-stu-id="6bebe-118">As part of its implementation of **FreeProws**, MAPI calls the [MAPIFreeBuffer](mapifreebuffer.md) function to free every entry in the **SRowSet** structure before freeing the complete structure.</span></span> <span data-ttu-id="6bebe-119">因此，所有此类条目都必须遵循 [SRowSet](srowset.md) 结构的分配规则，并针对每个成员数组和结构使用单个 [MAPIAllocateBuffer](mapiallocatebuffer.md) 调用。</span><span class="sxs-lookup"><span data-stu-id="6bebe-119">Therefore all such entries must have followed the allocation rules for the [SRowSet](srowset.md) structure, using an individual [MAPIAllocateBuffer](mapiallocatebuffer.md) call for each member array and structure.</span></span> 
  
<span data-ttu-id="6bebe-120">有关为 **ADRLIST** 和 **SRowSet** 结构分配内存的信息，请参阅 [管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="6bebe-120">For more information about allocating memory for **ADRLIST** and **SRowSet** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6bebe-121">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="6bebe-121">MFCMAPI reference</span></span>

<span data-ttu-id="6bebe-122">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6bebe-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6bebe-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="6bebe-123">**File**</span></span>|<span data-ttu-id="6bebe-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="6bebe-124">**Function**</span></span>|<span data-ttu-id="6bebe-125">**备注**</span><span class="sxs-lookup"><span data-stu-id="6bebe-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6bebe-126">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="6bebe-126">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="6bebe-127">DwThreadFuncLoadTable</span><span class="sxs-lookup"><span data-stu-id="6bebe-127">DwThreadFuncLoadTable</span></span>  <br/> |<span data-ttu-id="6bebe-128">MFCMAPI 使用 **FreeProws** 方法释放包含正在处理的表的行的 SRowSet 结构。</span><span class="sxs-lookup"><span data-stu-id="6bebe-128">MFCMAPI uses the **FreeProws** method to free an SRowSet structure containing rows of the table being processed.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6bebe-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bebe-129">See also</span></span>



[<span data-ttu-id="6bebe-130">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6bebe-130">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

