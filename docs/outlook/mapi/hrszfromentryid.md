---
title: HrSzFromEntryID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrSzFromEntryID
api_type:
- COM
ms.assetid: 5e3ed6b2-8eaf-44ab-bc6a-d3faabe84a93
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4020a9161a51994ebe5b7e339d26f7612ad47361
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411552"
---
# <a name="hrszfromentryid"></a><span data-ttu-id="38164-103">HrSzFromEntryID</span><span class="sxs-lookup"><span data-stu-id="38164-103">HrSzFromEntryID</span></span>

  
  
<span data-ttu-id="38164-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38164-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38164-105">将条目标识符编码为 ASCII 字符串。</span><span class="sxs-lookup"><span data-stu-id="38164-105">Encodes an entry identifier into an ASCII string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="38164-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="38164-106">Header file:</span></span>  <br/> |<span data-ttu-id="38164-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="38164-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="38164-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="38164-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="38164-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="38164-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="38164-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="38164-110">Called by:</span></span>  <br/> |<span data-ttu-id="38164-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="38164-111">Client applications</span></span>  <br/> |
   
```cpp
HrSzFromEntryID(
  ULONG cb,
  LPENTRYID pentry,
  LPSTR FAR * psz
);
```

## <a name="parameters"></a><span data-ttu-id="38164-112">参数</span><span class="sxs-lookup"><span data-stu-id="38164-112">Parameters</span></span>

 <span data-ttu-id="38164-113">_cb_</span><span class="sxs-lookup"><span data-stu-id="38164-113">_cb_</span></span>
  
> <span data-ttu-id="38164-114">实时由_pentry_参数指向的条目标识符的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="38164-114">[in] Size, in bytes, of the entry identifier pointed to by the  _pentry_ parameter.</span></span> 
    
 <span data-ttu-id="38164-115">_pentry_</span><span class="sxs-lookup"><span data-stu-id="38164-115">_pentry_</span></span>
  
> <span data-ttu-id="38164-116">实时指向包含要编码的条目标识符的[ENTRYID](entryid.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="38164-116">[in] Pointer to an [ENTRYID](entryid.md) structure that contains the entry identifier to be encoded.</span></span> 
    
 <span data-ttu-id="38164-117">_psz_</span><span class="sxs-lookup"><span data-stu-id="38164-117">_psz_</span></span>
  
> <span data-ttu-id="38164-118">排除指向返回的 ASCII 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="38164-118">[out] Pointer to the returned ASCII string.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="38164-119">返回值</span><span class="sxs-lookup"><span data-stu-id="38164-119">Return value</span></span>

<span data-ttu-id="38164-120">无。</span><span class="sxs-lookup"><span data-stu-id="38164-120">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="38164-121">说明</span><span class="sxs-lookup"><span data-stu-id="38164-121">Remarks</span></span>

<span data-ttu-id="38164-122">[HrEntryIDFromSz](hrentryidfromsz.md)和**HrSzFromEntryID**函数提供条目标识符的字符串和二进制格式之间的转换。</span><span class="sxs-lookup"><span data-stu-id="38164-122">The [HrEntryIDFromSz](hrentryidfromsz.md) and **HrSzFromEntryID** functions provide conversion between the string and binary formats of entry identifiers.</span></span> <span data-ttu-id="38164-123">使用 MAPI 时, 应使用二进制数据的结构。</span><span class="sxs-lookup"><span data-stu-id="38164-123">With MAPI, you should use structures with binary data.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="38164-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="38164-124">Notes to callers</span></span>

<span data-ttu-id="38164-125">**HrSzFromEntryID**函数使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数为 ASCII 字符串分配内存。</span><span class="sxs-lookup"><span data-stu-id="38164-125">The **HrSzFromEntryID** function allocates memory for the ASCII string using the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> 
  

