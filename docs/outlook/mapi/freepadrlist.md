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
ms.openlocfilehash: 2c5d4ec8381d6614cc2bc92fb0a762b068a97a81
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775001"
---
# <a name="freepadrlist"></a><span data-ttu-id="05822-103">FreePadrlist</span><span class="sxs-lookup"><span data-stu-id="05822-103">FreePadrlist</span></span>

  
  
<span data-ttu-id="05822-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="05822-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="05822-105">销毁[ADRLIST](adrlist.md)结构并释放关联的内存，包括分配给所有成员数组和结构的内存。</span><span class="sxs-lookup"><span data-stu-id="05822-105">Destroys an [ADRLIST](adrlist.md) structure and frees associated memory, including memory allocated for all member arrays and structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="05822-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="05822-106">Header file:</span></span>  <br/> |<span data-ttu-id="05822-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="05822-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="05822-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="05822-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="05822-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="05822-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="05822-110">调用：</span><span class="sxs-lookup"><span data-stu-id="05822-110">Called by:</span></span>  <br/> |<span data-ttu-id="05822-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="05822-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void FreePadrlist(
  LPADRLIST padrlist
);
```

## <a name="parameters"></a><span data-ttu-id="05822-112">参数</span><span class="sxs-lookup"><span data-stu-id="05822-112">Parameters</span></span>

 <span data-ttu-id="05822-113">_padrlist_</span><span class="sxs-lookup"><span data-stu-id="05822-113">_padrlist_</span></span>
  
> <span data-ttu-id="05822-114">[in]指向要销毁**ADRLIST**结构。</span><span class="sxs-lookup"><span data-stu-id="05822-114">[in] Pointer to the **ADRLIST** structure to be destroyed.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="05822-115">返回值</span><span class="sxs-lookup"><span data-stu-id="05822-115">Return value</span></span>

<span data-ttu-id="05822-116">无。</span><span class="sxs-lookup"><span data-stu-id="05822-116">None.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="05822-117">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="05822-117">Notes to callers</span></span>

<span data-ttu-id="05822-118">作为其实现**FreePadrlist**的一部分，MAPI 调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放完整结构之前释放**ADRLIST**结构中的每个条目。</span><span class="sxs-lookup"><span data-stu-id="05822-118">As part of its implementation of **FreePadrlist**, MAPI calls the [MAPIFreeBuffer](mapifreebuffer.md) function to free every entry in the **ADRLIST** structure before freeing the complete structure.</span></span> <span data-ttu-id="05822-119">因此所有此类条目必须遵循了[ADRLIST](adrlist.md)结构的分配规则，使用个人[MAPIAllocateBuffer](mapiallocatebuffer.md)调用的每个成员数组和结构。</span><span class="sxs-lookup"><span data-stu-id="05822-119">Therefore all such entries must have followed the allocation rules for the [ADRLIST](adrlist.md) structure, using an individual [MAPIAllocateBuffer](mapiallocatebuffer.md) call for each member array and structure.</span></span> 
  
<span data-ttu-id="05822-120">有关为**ADRLIST**和**SRowSet**结构分配内存的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="05822-120">For more information about allocating memory for **ADRLIST** and **SRowSet** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="05822-121">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="05822-121">MFCMAPI reference</span></span>

<span data-ttu-id="05822-122">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="05822-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="05822-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="05822-123">**File**</span></span>|<span data-ttu-id="05822-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="05822-124">**Function**</span></span>|<span data-ttu-id="05822-125">**Comment**</span><span class="sxs-lookup"><span data-stu-id="05822-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="05822-126">MAPIABFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="05822-126">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="05822-127">AddOneOffAddress</span><span class="sxs-lookup"><span data-stu-id="05822-127">AddOneOffAddress</span></span>  <br/> |<span data-ttu-id="05822-128">MFCMAPI 使用**FreePadrlist**方法释放生成一次性地址添加到一条消息 ADRLIST 结构。</span><span class="sxs-lookup"><span data-stu-id="05822-128">MFCMAPI uses the **FreePadrlist** method to free an ADRLIST structure that was built to add a one-off address to a message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="05822-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05822-129">See also</span></span>



[<span data-ttu-id="05822-130">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="05822-130">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

