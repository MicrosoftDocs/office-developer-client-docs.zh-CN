---
title: HrEntryIDFromSz
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrEntryIDFromSz
api_type:
- COM
ms.assetid: 14c171ec-0aec-43ab-8be8-e6bc0ce28a58
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ac59aeb3d650c0fbeb5bcdb580e0401cbab58ee6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437726"
---
# <a name="hrentryidfromsz"></a><span data-ttu-id="5b85a-103">HrEntryIDFromSz</span><span class="sxs-lookup"><span data-stu-id="5b85a-103">HrEntryIDFromSz</span></span>

  
  
<span data-ttu-id="5b85a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5b85a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5b85a-105">从 ASCII 编码重新创建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="5b85a-105">Recreates an entry identifier from its ASCII encoding.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5b85a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="5b85a-106">Header file:</span></span>  <br/> |<span data-ttu-id="5b85a-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="5b85a-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="5b85a-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="5b85a-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="5b85a-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="5b85a-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="5b85a-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="5b85a-110">Called by:</span></span>  <br/> |<span data-ttu-id="5b85a-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="5b85a-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT HrEntryIDFromSz(
  LPSTR sz,
  ULONG FAR * pcb,
  LPENTRYID FAR * ppentry
);
```

## <a name="parameters"></a><span data-ttu-id="5b85a-112">参数</span><span class="sxs-lookup"><span data-stu-id="5b85a-112">Parameters</span></span>

 <span data-ttu-id="5b85a-113">_sz_</span><span class="sxs-lookup"><span data-stu-id="5b85a-113">_sz_</span></span>
  
> <span data-ttu-id="5b85a-114">[in]指向用于创建条目标识符的 ASCII 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="5b85a-114">[in] Pointer to the ASCII string from which to create an entry identifier.</span></span> 
    
 <span data-ttu-id="5b85a-115">_这些_</span><span class="sxs-lookup"><span data-stu-id="5b85a-115">_pcb_</span></span>
  
> <span data-ttu-id="5b85a-116">[out]指向  _ppentry_ 参数指向的条目标识符的大小（以字节为单位）的指针。</span><span class="sxs-lookup"><span data-stu-id="5b85a-116">[out] Pointer to the size, in bytes, of the entry identifier pointed to by the  _ppentry_ parameter.</span></span> 
    
 <span data-ttu-id="5b85a-117">_ppentry_</span><span class="sxs-lookup"><span data-stu-id="5b85a-117">_ppentry_</span></span>
  
> <span data-ttu-id="5b85a-118">[out]指向返回的包含新条目标识符 [的 ENTRYID](entryid.md) 结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5b85a-118">[out] Pointer to a pointer to the returned [ENTRYID](entryid.md) structure that contains the new entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5b85a-119">返回值</span><span class="sxs-lookup"><span data-stu-id="5b85a-119">Return value</span></span>

<span data-ttu-id="5b85a-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b85a-120">S_OK</span></span>
  
> <span data-ttu-id="5b85a-121">娱乐已成功。</span><span class="sxs-lookup"><span data-stu-id="5b85a-121">The recreation was successful.</span></span>
    
<span data-ttu-id="5b85a-122">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="5b85a-122">MAPI_E_INVALID_ENTRYID</span></span>
  
> <span data-ttu-id="5b85a-123">条目 ID 无效。</span><span class="sxs-lookup"><span data-stu-id="5b85a-123">The entry ID was invalid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5b85a-124">备注</span><span class="sxs-lookup"><span data-stu-id="5b85a-124">Remarks</span></span>

<span data-ttu-id="5b85a-125">**HrEntryIDFromSz** 和 [HrSzFromEntryID](hrszfromentryid.md)函数提供条目标识符的字符串和二进制格式之间的转换。</span><span class="sxs-lookup"><span data-stu-id="5b85a-125">The **HrEntryIDFromSz** and [HrSzFromEntryID](hrszfromentryid.md) functions provide conversion between the string and binary formats of entry identifiers.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5b85a-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5b85a-126">Notes to callers</span></span>

<span data-ttu-id="5b85a-127">**HrEntryIDFromSz** 函数使用 [MAPIAllocateBuffer](mapiallocatebuffer.md)函数为 ASCII 字符串分配内存。</span><span class="sxs-lookup"><span data-stu-id="5b85a-127">The **HrEntryIDFromSz** function allocates memory for the ASCII string using the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> 
  

