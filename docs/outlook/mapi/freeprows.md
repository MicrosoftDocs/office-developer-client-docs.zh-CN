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
ms.openlocfilehash: 0686cee9bf6fa47332f75f99e1d2a2d35cb7e7fb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578022"
---
# <a name="freeprows"></a><span data-ttu-id="7b16a-103">FreeProws</span><span class="sxs-lookup"><span data-stu-id="7b16a-103">FreeProws</span></span>

  
  
<span data-ttu-id="7b16a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7b16a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7b16a-105">销毁[SRowSet](srowset.md)结构并释放关联的内存，包括分配给所有成员数组和结构的内存。</span><span class="sxs-lookup"><span data-stu-id="7b16a-105">Destroys an [SRowSet](srowset.md) structure and frees associated memory, including memory allocated for all member arrays and structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7b16a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="7b16a-106">Header file:</span></span>  <br/> |<span data-ttu-id="7b16a-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="7b16a-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="7b16a-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="7b16a-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7b16a-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7b16a-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7b16a-110">调用：</span><span class="sxs-lookup"><span data-stu-id="7b16a-110">Called by:</span></span>  <br/> |<span data-ttu-id="7b16a-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="7b16a-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void FreeProws(
  LPSRowSet prows
);
```

## <a name="parameters"></a><span data-ttu-id="7b16a-112">参数</span><span class="sxs-lookup"><span data-stu-id="7b16a-112">Parameters</span></span>

 <span data-ttu-id="7b16a-113">_prows_</span><span class="sxs-lookup"><span data-stu-id="7b16a-113">_prows_</span></span>
  
> <span data-ttu-id="7b16a-114">[in]指向要销毁**SRowSet**结构。</span><span class="sxs-lookup"><span data-stu-id="7b16a-114">[in] Pointer to the **SRowSet** structure to be destroyed.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7b16a-115">返回值</span><span class="sxs-lookup"><span data-stu-id="7b16a-115">Return value</span></span>

<span data-ttu-id="7b16a-116">无。</span><span class="sxs-lookup"><span data-stu-id="7b16a-116">None.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="7b16a-117">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7b16a-117">Notes to callers</span></span>

<span data-ttu-id="7b16a-118">作为其实现**FreeProws**的一部分，MAPI 调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放完整结构之前释放**SRowSet**结构中的每个条目。</span><span class="sxs-lookup"><span data-stu-id="7b16a-118">As part of its implementation of **FreeProws**, MAPI calls the [MAPIFreeBuffer](mapifreebuffer.md) function to free every entry in the **SRowSet** structure before freeing the complete structure.</span></span> <span data-ttu-id="7b16a-119">因此所有此类条目必须遵循了[SRowSet](srowset.md)结构的分配规则，使用个人[MAPIAllocateBuffer](mapiallocatebuffer.md)调用的每个成员数组和结构。</span><span class="sxs-lookup"><span data-stu-id="7b16a-119">Therefore all such entries must have followed the allocation rules for the [SRowSet](srowset.md) structure, using an individual [MAPIAllocateBuffer](mapiallocatebuffer.md) call for each member array and structure.</span></span> 
  
<span data-ttu-id="7b16a-120">有关为**ADRLIST**和**SRowSet**结构分配内存的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="7b16a-120">For more information about allocating memory for **ADRLIST** and **SRowSet** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="7b16a-121">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="7b16a-121">MFCMAPI reference</span></span>

<span data-ttu-id="7b16a-122">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7b16a-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7b16a-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="7b16a-123">**File**</span></span>|<span data-ttu-id="7b16a-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="7b16a-124">**Function**</span></span>|<span data-ttu-id="7b16a-125">**Comment**</span><span class="sxs-lookup"><span data-stu-id="7b16a-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7b16a-126">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="7b16a-126">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="7b16a-127">DwThreadFuncLoadTable</span><span class="sxs-lookup"><span data-stu-id="7b16a-127">DwThreadFuncLoadTable</span></span>  <br/> |<span data-ttu-id="7b16a-128">MFCMAPI 使用**FreeProws**方法来释放包含正在处理 table 的行 SRowSet 结构。</span><span class="sxs-lookup"><span data-stu-id="7b16a-128">MFCMAPI uses the **FreeProws** method to free an SRowSet structure containing rows of the table being processed.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7b16a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b16a-129">See also</span></span>



[<span data-ttu-id="7b16a-130">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7b16a-130">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

