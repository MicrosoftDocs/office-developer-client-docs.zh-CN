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
ms.openlocfilehash: 366208b8288aeb61bf1bb78f2c9f10b400a3dc26
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567592"
---
# <a name="hrszfromentryid"></a><span data-ttu-id="4308f-103">HrSzFromEntryID</span><span class="sxs-lookup"><span data-stu-id="4308f-103">HrSzFromEntryID</span></span>

  
  
<span data-ttu-id="4308f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4308f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4308f-105">编码为 ASCII 字符串的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4308f-105">Encodes an entry identifier into an ASCII string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4308f-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="4308f-106">Header file:</span></span>  <br/> |<span data-ttu-id="4308f-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="4308f-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="4308f-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="4308f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="4308f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="4308f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="4308f-110">调用：</span><span class="sxs-lookup"><span data-stu-id="4308f-110">Called by:</span></span>  <br/> |<span data-ttu-id="4308f-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="4308f-111">Client applications</span></span>  <br/> |
   
```cpp
HrSzFromEntryID(
  ULONG cb,
  LPENTRYID pentry,
  LPSTR FAR * psz
);
```

## <a name="parameters"></a><span data-ttu-id="4308f-112">参数</span><span class="sxs-lookup"><span data-stu-id="4308f-112">Parameters</span></span>

 <span data-ttu-id="4308f-113">_cb_</span><span class="sxs-lookup"><span data-stu-id="4308f-113">_cb_</span></span>
  
> <span data-ttu-id="4308f-114">[in]大小，以字节为单位_pentry_参数指向的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4308f-114">[in] Size, in bytes, of the entry identifier pointed to by the  _pentry_ parameter.</span></span> 
    
 <span data-ttu-id="4308f-115">_pentry_</span><span class="sxs-lookup"><span data-stu-id="4308f-115">_pentry_</span></span>
  
> <span data-ttu-id="4308f-116">[in]指向[ENTRYID](entryid.md)结构，其中包含要编码的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="4308f-116">[in] Pointer to an [ENTRYID](entryid.md) structure that contains the entry identifier to be encoded.</span></span> 
    
 <span data-ttu-id="4308f-117">_psz_</span><span class="sxs-lookup"><span data-stu-id="4308f-117">_psz_</span></span>
  
> <span data-ttu-id="4308f-118">[输出]指向返回 ASCII 字符串。</span><span class="sxs-lookup"><span data-stu-id="4308f-118">[out] Pointer to the returned ASCII string.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4308f-119">返回值</span><span class="sxs-lookup"><span data-stu-id="4308f-119">Return value</span></span>

<span data-ttu-id="4308f-120">无。</span><span class="sxs-lookup"><span data-stu-id="4308f-120">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4308f-121">注解</span><span class="sxs-lookup"><span data-stu-id="4308f-121">Remarks</span></span>

<span data-ttu-id="4308f-122">[HrEntryIDFromSz](hrentryidfromsz.md)和**HrSzFromEntryID**函数提供的字符串和项标识符的二进制格式之间的转换。</span><span class="sxs-lookup"><span data-stu-id="4308f-122">The [HrEntryIDFromSz](hrentryidfromsz.md) and **HrSzFromEntryID** functions provide conversion between the string and binary formats of entry identifiers.</span></span> <span data-ttu-id="4308f-123">使用 MAPI，应使用二进制数据结构。</span><span class="sxs-lookup"><span data-stu-id="4308f-123">With MAPI, you should use structures with binary data.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="4308f-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="4308f-124">Notes to callers</span></span>

<span data-ttu-id="4308f-125">**HrSzFromEntryID**函数使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的 ASCII 字符串分配内存。</span><span class="sxs-lookup"><span data-stu-id="4308f-125">The **HrSzFromEntryID** function allocates memory for the ASCII string using the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> 
  

