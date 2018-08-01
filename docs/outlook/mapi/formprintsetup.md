---
title: FORMPRINTSETUP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FORMPRINTSETUP
api_type:
- COM
ms.assetid: 6e82fe94-47bd-4a25-b25b-0ab6fe2db274
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ff46c58fbb352d56ae3df09d6949cdd5f614673f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774977"
---
# <a name="formprintsetup"></a><span data-ttu-id="29fb1-103">FORMPRINTSETUP</span><span class="sxs-lookup"><span data-stu-id="29fb1-103">FORMPRINTSETUP</span></span>

  
  
<span data-ttu-id="29fb1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="29fb1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="29fb1-105">介绍 form 对象的打印设置信息。</span><span class="sxs-lookup"><span data-stu-id="29fb1-105">Describes the print setup information for the form object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="29fb1-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="29fb1-106">Header file:</span></span>  <br/> |<span data-ttu-id="29fb1-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="29fb1-107">Mapiform.h</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG ulFlags;
  HDEVMODE hDevMode;
  HDEVNAMES hDevNames;
  ULONG ulFirstPageNumber;
  ULONG ulFPrintAttachments;
} FORMPRINTSETUP, FAR * LPFORMPRINTSETUP;

```

## <a name="members"></a><span data-ttu-id="29fb1-108">Members</span><span class="sxs-lookup"><span data-stu-id="29fb1-108">Members</span></span>

 <span data-ttu-id="29fb1-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="29fb1-109">**ulFlags**</span></span>
  
> <span data-ttu-id="29fb1-110">位掩码的标志，控制字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="29fb1-110">Bitmask of flags that controls the type of the strings.</span></span> <span data-ttu-id="29fb1-111">可以使用以下标记：</span><span class="sxs-lookup"><span data-stu-id="29fb1-111">The following flag can be used:</span></span>
    
<span data-ttu-id="29fb1-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="29fb1-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="29fb1-113">字符串是 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="29fb1-113">The strings are in Unicode format.</span></span> <span data-ttu-id="29fb1-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="29fb1-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="29fb1-115">**hDevmode**</span><span class="sxs-lookup"><span data-stu-id="29fb1-115">**hDevmode**</span></span>
  
> <span data-ttu-id="29fb1-116">打印机的模式的句柄。</span><span class="sxs-lookup"><span data-stu-id="29fb1-116">Handle to the mode of the printer.</span></span>
    
 <span data-ttu-id="29fb1-117">**hDevnames**</span><span class="sxs-lookup"><span data-stu-id="29fb1-117">**hDevnames**</span></span>
  
> <span data-ttu-id="29fb1-118">处理到打印机的路径。</span><span class="sxs-lookup"><span data-stu-id="29fb1-118">Handle to the path of the printer.</span></span>
    
 <span data-ttu-id="29fb1-119">**ulFirstPageNumber**</span><span class="sxs-lookup"><span data-stu-id="29fb1-119">**ulFirstPageNumber**</span></span>
  
> <span data-ttu-id="29fb1-120">要打印的第一页的页码。</span><span class="sxs-lookup"><span data-stu-id="29fb1-120">Page number of the first page to be printed.</span></span>
    
 <span data-ttu-id="29fb1-121">**ulFPrintAttachments**</span><span class="sxs-lookup"><span data-stu-id="29fb1-121">**ulFPrintAttachments**</span></span>
  
> <span data-ttu-id="29fb1-122">指示是否有要打印的附件的标志。</span><span class="sxs-lookup"><span data-stu-id="29fb1-122">Flag that indicates whether there are attachments to be printed.</span></span> <span data-ttu-id="29fb1-123">如果要打印的附件， **ulFPrintAttachments**成员设置为 1。</span><span class="sxs-lookup"><span data-stu-id="29fb1-123">If there are attachments to print, the **ulFPrintAttachments** member is set to 1.</span></span> <span data-ttu-id="29fb1-124">如果不有任何附件打印，则将其设置为 0。</span><span class="sxs-lookup"><span data-stu-id="29fb1-124">If there are no attachments to print, it is set to 0.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="29fb1-125">说明</span><span class="sxs-lookup"><span data-stu-id="29fb1-125">Remarks</span></span>

<span data-ttu-id="29fb1-126">**FORMPRINTSETUP**结构用于描述 form 对象的打印设置信息。</span><span class="sxs-lookup"><span data-stu-id="29fb1-126">The **FORMPRINTSETUP** structure is used to describe the print setup information for a form object.</span></span> <span data-ttu-id="29fb1-127">实现的[IMAPIViewContext::GetPrintSetup](imapiviewcontext-getprintsetup.md)填写**FORMPRINTSETUP**结构，并将其返回**GetPrintSetup** _lppFormPrintSetup_输出参数的内容中。</span><span class="sxs-lookup"><span data-stu-id="29fb1-127">Implementations of [IMAPIViewContext::GetPrintSetup](imapiviewcontext-getprintsetup.md) fill in the **FORMPRINTSETUP** structure and return it in the contents of the  _lppFormPrintSetup_ output parameter of **GetPrintSetup**.</span></span>
  
<span data-ttu-id="29fb1-128">如果**GetPrintSetup**的_ulFlags_参数中传递 MAPI_UNICODE 标志，则引用的**hDevmode**和**hDevnames**成员的字符串应为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="29fb1-128">If the MAPI_UNICODE flag is passed in the  _ulFlags_ parameter of **GetPrintSetup**, the strings referenced by the **hDevmode** and **hDevnames** members should be in Unicode format.</span></span> <span data-ttu-id="29fb1-129">否则，字符串应以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="29fb1-129">Otherwise, the strings should be in ANSI format.</span></span> 
  
<span data-ttu-id="29fb1-130">实现**IMAPIViewContext**表单查看器必须分配**FORMPRINTSETUP**结构使用 MAPI 分配器函数[MAPIAllocateBuffer](mapiallocatebuffer.md)，但分配各个成员， **hDevMode**和**hDevNames**，与 Windows 函数[GlobalAlloc](http://go.microsoft.com/fwlink/?LinkId=132110)。</span><span class="sxs-lookup"><span data-stu-id="29fb1-130">Form viewers implementing **IMAPIViewContext** must allocate the **FORMPRINTSETUP** structure using the MAPI allocator function [MAPIAllocateBuffer](mapiallocatebuffer.md), but allocate the individual members, **hDevMode** and **hDevNames**, with the Windows function [GlobalAlloc](http://go.microsoft.com/fwlink/?LinkId=132110).</span></span> <span data-ttu-id="29fb1-131">同样处理内存的版本。</span><span class="sxs-lookup"><span data-stu-id="29fb1-131">The release of memory is handled similarly.</span></span> <span data-ttu-id="29fb1-132">使用 Windows 函数[GlobalFree](http://go.microsoft.com/fwlink/?LinkId=132108)而必须用[MAPIFreeBuffer](mapifreebuffer.md)函数释放**FORMPRINTSETUP**结构，必须释放的**hDevMode**和**hDevNames**成员。</span><span class="sxs-lookup"><span data-stu-id="29fb1-132">The **hDevMode** and **hDevNames** members must be freed using the Windows function [GlobalFree](http://go.microsoft.com/fwlink/?LinkId=132108) whereas the **FORMPRINTSETUP** structure must be freed with the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="29fb1-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29fb1-133">See also</span></span>



[<span data-ttu-id="29fb1-134">IMAPIViewContext::GetPrintSetup</span><span class="sxs-lookup"><span data-stu-id="29fb1-134">IMAPIViewContext::GetPrintSetup</span></span>](imapiviewcontext-getprintsetup.md)
  
[<span data-ttu-id="29fb1-135">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="29fb1-135">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="29fb1-136">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="29fb1-136">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)


[<span data-ttu-id="29fb1-137">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="29fb1-137">MAPI Structures</span></span>](mapi-structures.md)

