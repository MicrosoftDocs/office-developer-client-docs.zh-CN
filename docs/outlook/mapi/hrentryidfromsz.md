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
ms.openlocfilehash: a524a7eb40c33d6de2f64cd5373c9a39a8a1e3df
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565296"
---
# <a name="hrentryidfromsz"></a><span data-ttu-id="1bbe6-103">HrEntryIDFromSz</span><span class="sxs-lookup"><span data-stu-id="1bbe6-103">HrEntryIDFromSz</span></span>

  
  
<span data-ttu-id="1bbe6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1bbe6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1bbe6-105">重新创建从其 ASCII 编码的项标识符。</span><span class="sxs-lookup"><span data-stu-id="1bbe6-105">Recreates an entry identifier from its ASCII encoding.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1bbe6-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="1bbe6-106">Header file:</span></span>  <br/> |<span data-ttu-id="1bbe6-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="1bbe6-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="1bbe6-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="1bbe6-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="1bbe6-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="1bbe6-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="1bbe6-110">调用：</span><span class="sxs-lookup"><span data-stu-id="1bbe6-110">Called by:</span></span>  <br/> |<span data-ttu-id="1bbe6-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="1bbe6-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT HrEntryIDFromSz(
  LPSTR sz,
  ULONG FAR * pcb,
  LPENTRYID FAR * ppentry
);
```

## <a name="parameters"></a><span data-ttu-id="1bbe6-112">参数</span><span class="sxs-lookup"><span data-stu-id="1bbe6-112">Parameters</span></span>

 <span data-ttu-id="1bbe6-113">_sz_</span><span class="sxs-lookup"><span data-stu-id="1bbe6-113">_sz_</span></span>
  
> <span data-ttu-id="1bbe6-114">[in]指向 ASCII 字符串从中创建的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="1bbe6-114">[in] Pointer to the ASCII string from which to create an entry identifier.</span></span> 
    
 <span data-ttu-id="1bbe6-115">_pcb_</span><span class="sxs-lookup"><span data-stu-id="1bbe6-115">_pcb_</span></span>
  
> <span data-ttu-id="1bbe6-116">[输出]指向的大小，以字节为单位_ppentry_参数指向的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="1bbe6-116">[out] Pointer to the size, in bytes, of the entry identifier pointed to by the  _ppentry_ parameter.</span></span> 
    
 <span data-ttu-id="1bbe6-117">_ppentry_</span><span class="sxs-lookup"><span data-stu-id="1bbe6-117">_ppentry_</span></span>
  
> <span data-ttu-id="1bbe6-118">[输出]返回包含新的项标识符的[ENTRYID](entryid.md)结构为指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1bbe6-118">[out] Pointer to a pointer to the returned [ENTRYID](entryid.md) structure that contains the new entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1bbe6-119">返回值</span><span class="sxs-lookup"><span data-stu-id="1bbe6-119">Return value</span></span>

<span data-ttu-id="1bbe6-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="1bbe6-120">S_OK</span></span>
  
> <span data-ttu-id="1bbe6-121">重新创建已成功。</span><span class="sxs-lookup"><span data-stu-id="1bbe6-121">The recreation was successful.</span></span>
    
<span data-ttu-id="1bbe6-122">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="1bbe6-122">MAPI_E_INVALID_ENTRYID</span></span>
  
> <span data-ttu-id="1bbe6-123">条目 ID 无效。</span><span class="sxs-lookup"><span data-stu-id="1bbe6-123">The entry ID was invalid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1bbe6-124">注解</span><span class="sxs-lookup"><span data-stu-id="1bbe6-124">Remarks</span></span>

<span data-ttu-id="1bbe6-125">**HrEntryIDFromSz**和[HrSzFromEntryID](hrszfromentryid.md)函数提供的字符串和项标识符的二进制格式之间的转换。</span><span class="sxs-lookup"><span data-stu-id="1bbe6-125">The **HrEntryIDFromSz** and [HrSzFromEntryID](hrszfromentryid.md) functions provide conversion between the string and binary formats of entry identifiers.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1bbe6-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1bbe6-126">Notes to callers</span></span>

<span data-ttu-id="1bbe6-127">**HrEntryIDFromSz**函数使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的 ASCII 字符串分配内存。</span><span class="sxs-lookup"><span data-stu-id="1bbe6-127">The **HrEntryIDFromSz** function allocates memory for the ASCII string using the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> 
  

