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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328033"
---
# <a name="freepadrlist"></a><span data-ttu-id="a6274-103">FreePadrlist</span><span class="sxs-lookup"><span data-stu-id="a6274-103">FreePadrlist</span></span>

  
  
<span data-ttu-id="a6274-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a6274-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a6274-105">销毁[ADRLIST](adrlist.md)结构并释放关联内存, 包括为所有成员数组和结构分配的内存。</span><span class="sxs-lookup"><span data-stu-id="a6274-105">Destroys an [ADRLIST](adrlist.md) structure and frees associated memory, including memory allocated for all member arrays and structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a6274-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a6274-106">Header file:</span></span>  <br/> |<span data-ttu-id="a6274-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="a6274-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="a6274-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="a6274-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a6274-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a6274-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a6274-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="a6274-110">Called by:</span></span>  <br/> |<span data-ttu-id="a6274-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="a6274-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void FreePadrlist(
  LPADRLIST padrlist
);
```

## <a name="parameters"></a><span data-ttu-id="a6274-112">参数</span><span class="sxs-lookup"><span data-stu-id="a6274-112">Parameters</span></span>

 <span data-ttu-id="a6274-113">_padrlist_</span><span class="sxs-lookup"><span data-stu-id="a6274-113">_padrlist_</span></span>
  
> <span data-ttu-id="a6274-114">实时指向要销毁的**ADRLIST**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a6274-114">[in] Pointer to the **ADRLIST** structure to be destroyed.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a6274-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a6274-115">Return value</span></span>

<span data-ttu-id="a6274-116">无。</span><span class="sxs-lookup"><span data-stu-id="a6274-116">None.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="a6274-117">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a6274-117">Notes to callers</span></span>

<span data-ttu-id="a6274-118">在**FreePadrlist**的实现过程中, MAPI 将调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 以释放**ADRLIST**结构中的每个条目, 然后再释放完整的结构。</span><span class="sxs-lookup"><span data-stu-id="a6274-118">As part of its implementation of **FreePadrlist**, MAPI calls the [MAPIFreeBuffer](mapifreebuffer.md) function to free every entry in the **ADRLIST** structure before freeing the complete structure.</span></span> <span data-ttu-id="a6274-119">因此, 所有这样的条目都必须遵循[ADRLIST](adrlist.md)结构的分配规则, 为每个成员数组和结构使用单独的[MAPIAllocateBuffer](mapiallocatebuffer.md)调用。</span><span class="sxs-lookup"><span data-stu-id="a6274-119">Therefore all such entries must have followed the allocation rules for the [ADRLIST](adrlist.md) structure, using an individual [MAPIAllocateBuffer](mapiallocatebuffer.md) call for each member array and structure.</span></span> 
  
<span data-ttu-id="a6274-120">有关为**ADRLIST**和**SRowSet**结构分配内存的详细信息, 请参阅[管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="a6274-120">For more information about allocating memory for **ADRLIST** and **SRowSet** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a6274-121">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a6274-121">MFCMAPI reference</span></span>

<span data-ttu-id="a6274-122">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a6274-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a6274-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="a6274-123">**File**</span></span>|<span data-ttu-id="a6274-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="a6274-124">**Function**</span></span>|<span data-ttu-id="a6274-125">**备注**</span><span class="sxs-lookup"><span data-stu-id="a6274-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a6274-126">MAPIABFunctions</span><span class="sxs-lookup"><span data-stu-id="a6274-126">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="a6274-127">AddOneOffAddress</span><span class="sxs-lookup"><span data-stu-id="a6274-127">AddOneOffAddress</span></span>  <br/> |<span data-ttu-id="a6274-128">MFCMAPI 使用**FreePadrlist**方法来释放为向邮件添加一次性地址而生成的 ADRLIST 结构。</span><span class="sxs-lookup"><span data-stu-id="a6274-128">MFCMAPI uses the **FreePadrlist** method to free an ADRLIST structure that was built to add a one-off address to a message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a6274-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6274-129">See also</span></span>



[<span data-ttu-id="a6274-130">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a6274-130">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

