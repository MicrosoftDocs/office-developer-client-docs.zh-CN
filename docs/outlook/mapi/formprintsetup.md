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
ms.openlocfilehash: c2b9176e21341ef28e6f0bc007757b097a05daee
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327284"
---
# <a name="formprintsetup"></a><span data-ttu-id="6a22a-103">FORMPRINTSETUP</span><span class="sxs-lookup"><span data-stu-id="6a22a-103">FORMPRINTSETUP</span></span>

  
  
<span data-ttu-id="6a22a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6a22a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6a22a-105">描述窗体对象的打印设置信息。</span><span class="sxs-lookup"><span data-stu-id="6a22a-105">Describes the print setup information for the form object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6a22a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6a22a-106">Header file:</span></span>  <br/> |<span data-ttu-id="6a22a-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="6a22a-107">Mapiform.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="6a22a-108">成员</span><span class="sxs-lookup"><span data-stu-id="6a22a-108">Members</span></span>

 <span data-ttu-id="6a22a-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="6a22a-109">**ulFlags**</span></span>
  
> <span data-ttu-id="6a22a-110">控制字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="6a22a-110">Bitmask of flags that controls the type of the strings.</span></span> <span data-ttu-id="6a22a-111">可以使用以下标志：</span><span class="sxs-lookup"><span data-stu-id="6a22a-111">The following flag can be used:</span></span>
    
<span data-ttu-id="6a22a-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6a22a-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="6a22a-113">字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="6a22a-113">The strings are in Unicode format.</span></span> <span data-ttu-id="6a22a-114">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="6a22a-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="6a22a-115">**hDevmode**</span><span class="sxs-lookup"><span data-stu-id="6a22a-115">**hDevmode**</span></span>
  
> <span data-ttu-id="6a22a-116">打印机模式的句柄。</span><span class="sxs-lookup"><span data-stu-id="6a22a-116">Handle to the mode of the printer.</span></span>
    
 <span data-ttu-id="6a22a-117">**hDevnames**</span><span class="sxs-lookup"><span data-stu-id="6a22a-117">**hDevnames**</span></span>
  
> <span data-ttu-id="6a22a-118">打印机路径的句柄。</span><span class="sxs-lookup"><span data-stu-id="6a22a-118">Handle to the path of the printer.</span></span>
    
 <span data-ttu-id="6a22a-119">**ulFirstPageNumber**</span><span class="sxs-lookup"><span data-stu-id="6a22a-119">**ulFirstPageNumber**</span></span>
  
> <span data-ttu-id="6a22a-120">要打印的第一页的页码。</span><span class="sxs-lookup"><span data-stu-id="6a22a-120">Page number of the first page to be printed.</span></span>
    
 <span data-ttu-id="6a22a-121">**ulFPrintAttachments**</span><span class="sxs-lookup"><span data-stu-id="6a22a-121">**ulFPrintAttachments**</span></span>
  
> <span data-ttu-id="6a22a-122">指示是否有附件要打印的标志。</span><span class="sxs-lookup"><span data-stu-id="6a22a-122">Flag that indicates whether there are attachments to be printed.</span></span> <span data-ttu-id="6a22a-123">如果存在要打印的附件，则 **ulFPrintAttachments** 成员设置为 1。</span><span class="sxs-lookup"><span data-stu-id="6a22a-123">If there are attachments to print, the **ulFPrintAttachments** member is set to 1.</span></span> <span data-ttu-id="6a22a-124">如果没有附件要打印，则设置为 0。</span><span class="sxs-lookup"><span data-stu-id="6a22a-124">If there are no attachments to print, it is set to 0.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="6a22a-125">备注</span><span class="sxs-lookup"><span data-stu-id="6a22a-125">Remarks</span></span>

<span data-ttu-id="6a22a-126">**FORMPRINTSETUP** 结构用于描述窗体对象的打印设置信息。</span><span class="sxs-lookup"><span data-stu-id="6a22a-126">The **FORMPRINTSETUP** structure is used to describe the print setup information for a form object.</span></span> <span data-ttu-id="6a22a-127">[IMAPIViewContext：：GetPrintSetup](imapiviewcontext-getprintsetup.md)的实现填充 **FORMPRINTSETUP** 结构，并返回在 **GetPrintSetup**_的 lppFormPrintSetup_ 输出参数的内容中。</span><span class="sxs-lookup"><span data-stu-id="6a22a-127">Implementations of [IMAPIViewContext::GetPrintSetup](imapiviewcontext-getprintsetup.md) fill in the **FORMPRINTSETUP** structure and return it in the contents of the  _lppFormPrintSetup_ output parameter of **GetPrintSetup**.</span></span>
  
<span data-ttu-id="6a22a-128">如果 MAPI_UNICODE 标志在 **GetPrintSetup** 的 _ulFlags_ 参数中传递，**则 hDevmode** 和 **hDevnames** 成员引用的字符串应为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="6a22a-128">If the MAPI_UNICODE flag is passed in the  _ulFlags_ parameter of **GetPrintSetup**, the strings referenced by the **hDevmode** and **hDevnames** members should be in Unicode format.</span></span> <span data-ttu-id="6a22a-129">否则，字符串应为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="6a22a-129">Otherwise, the strings should be in ANSI format.</span></span> 
  
<span data-ttu-id="6a22a-130">实现 **IMAPIViewContext** 的表单查看器必须使用 MAPI 分配程序函数 [MAPIAllocateBuffer](mapiallocatebuffer.md)分配 **FORMPRINTSETUP** 结构，但使用 Windows 函数 [GlobalAlloc](https://go.microsoft.com/fwlink/?LinkId=132110)分配单个成员 **hDevMode** 和 **hDevNames。**</span><span class="sxs-lookup"><span data-stu-id="6a22a-130">Form viewers implementing **IMAPIViewContext** must allocate the **FORMPRINTSETUP** structure using the MAPI allocator function [MAPIAllocateBuffer](mapiallocatebuffer.md), but allocate the individual members, **hDevMode** and **hDevNames**, with the Windows function [GlobalAlloc](https://go.microsoft.com/fwlink/?LinkId=132110).</span></span> <span data-ttu-id="6a22a-131">内存释放的处理方式类似。</span><span class="sxs-lookup"><span data-stu-id="6a22a-131">The release of memory is handled similarly.</span></span> <span data-ttu-id="6a22a-132">**hDevMode** 和 **hDevNames** 成员必须使用 Windows 函数 [GlobalFree](https://go.microsoft.com/fwlink/?LinkId=132108)释放，而 **FORMPRINTSETUP** 结构必须使用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放。</span><span class="sxs-lookup"><span data-stu-id="6a22a-132">The **hDevMode** and **hDevNames** members must be freed using the Windows function [GlobalFree](https://go.microsoft.com/fwlink/?LinkId=132108) whereas the **FORMPRINTSETUP** structure must be freed with the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6a22a-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a22a-133">See also</span></span>



[<span data-ttu-id="6a22a-134">IMAPIViewContext::GetPrintSetup</span><span class="sxs-lookup"><span data-stu-id="6a22a-134">IMAPIViewContext::GetPrintSetup</span></span>](imapiviewcontext-getprintsetup.md)
  
[<span data-ttu-id="6a22a-135">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="6a22a-135">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="6a22a-136">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="6a22a-136">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)


[<span data-ttu-id="6a22a-137">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="6a22a-137">MAPI Structures</span></span>](mapi-structures.md)

