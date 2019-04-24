---
title: MNLS_WideCharToMultiByte
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f64cde12-7ed1-444f-8ca4-51cb3ea514cf
description: '上次修改时间: 2012 年2月21日'
ms.openlocfilehash: ad41f9b6060e5cfbabecfd9bb29a47815929d6b5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338729"
---
# <a name="mnlswidechartomultibyte"></a><span data-ttu-id="e36a6-103">MNLS_WideCharToMultiByte</span><span class="sxs-lookup"><span data-stu-id="e36a6-103">MNLS_WideCharToMultiByte</span></span>

  
  
<span data-ttu-id="e36a6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e36a6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e36a6-105">此函数类似于**WideCharToMultiByte**, 它将 UTF-16 (宽字符) 字符串映射到新的字符字符串。</span><span class="sxs-lookup"><span data-stu-id="e36a6-105">This function is similar to **WideCharToMultiByte**, which maps a UTF-16 (wide character) string to a new character string.</span></span> <span data-ttu-id="e36a6-106">新的字符串不一定来自多字节字符集。</span><span class="sxs-lookup"><span data-stu-id="e36a6-106">The new character string is not necessarily from a multibyte character set.</span></span>
  
```cpp
int MNLS_WideCharToMultiByte(
  UINT uCodePage,
  DWORD dwFlags,
  LPCWSTR lpWideCharStr,
  int cchWideChar,
  LPSTR lpMultiByteStr,
  int cchMultiByte,
  LPCSTR lpDefaultChar,
  BOOL FAR *lpfUsedDefaultChar);
```

## <a name="parameters"></a><span data-ttu-id="e36a6-107">参数</span><span class="sxs-lookup"><span data-stu-id="e36a6-107">Parameters</span></span>

 <span data-ttu-id="e36a6-108">_uCodePage_</span><span class="sxs-lookup"><span data-stu-id="e36a6-108">_uCodePage_</span></span>
  
> <span data-ttu-id="e36a6-109">实时要在执行转换时使用的代码页。</span><span class="sxs-lookup"><span data-stu-id="e36a6-109">[in] Code page to use in performing the conversion.</span></span>
    
 <span data-ttu-id="e36a6-110">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="e36a6-110">_dwFlags_</span></span>
  
> <span data-ttu-id="e36a6-111">实时指示转换类型的标志。</span><span class="sxs-lookup"><span data-stu-id="e36a6-111">[in] Flags indicating the conversion type.</span></span>
    
 <span data-ttu-id="e36a6-112">_lpWideCharStr_</span><span class="sxs-lookup"><span data-stu-id="e36a6-112">_lpWideCharStr_</span></span>
  
> <span data-ttu-id="e36a6-113">实时指向要转换的 Unicode 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="e36a6-113">[in] Pointer to the Unicode string to convert.</span></span>
    
 <span data-ttu-id="e36a6-114">_cchWideChar_</span><span class="sxs-lookup"><span data-stu-id="e36a6-114">_cchWideChar_</span></span>
  
> <span data-ttu-id="e36a6-115">实时指示转换类型的标志。</span><span class="sxs-lookup"><span data-stu-id="e36a6-115">[in] Flags indicating the conversion type.</span></span>
    
 <span data-ttu-id="e36a6-116">_lpMultiByteStr_</span><span class="sxs-lookup"><span data-stu-id="e36a6-116">_lpMultiByteStr_</span></span>
  
> <span data-ttu-id="e36a6-117">[] out可选。</span><span class="sxs-lookup"><span data-stu-id="e36a6-117">[out] Optional.</span></span> <span data-ttu-id="e36a6-118">指向接收转换后的字符串的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="e36a6-118">Pointer to a buffer that receives the converted string.</span></span>
    
 <span data-ttu-id="e36a6-119">_cchMultiByte_</span><span class="sxs-lookup"><span data-stu-id="e36a6-119">_cchMultiByte_</span></span>
  
> <span data-ttu-id="e36a6-120">实时由_lpMultiByteStr_指示的缓冲区的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="e36a6-120">[in] Size, in bytes, of the buffer indicated by  _lpMultiByteStr_.</span></span>
    
 <span data-ttu-id="e36a6-121">_lpDefaultChar_</span><span class="sxs-lookup"><span data-stu-id="e36a6-121">_lpDefaultChar_</span></span>
  
> <span data-ttu-id="e36a6-122">[中]可选。</span><span class="sxs-lookup"><span data-stu-id="e36a6-122">[in] Optional.</span></span> <span data-ttu-id="e36a6-123">一个指针, 指向在指定的代码页中无法表示字符时要使用的字符。</span><span class="sxs-lookup"><span data-stu-id="e36a6-123">Pointer to the character to use if a character cannot be represented in the specified code page.</span></span>
    
 <span data-ttu-id="e36a6-124">_lpfUsedDefaultChar_</span><span class="sxs-lookup"><span data-stu-id="e36a6-124">_lpfUsedDefaultChar_</span></span>
  
> <span data-ttu-id="e36a6-125">[] out可选。</span><span class="sxs-lookup"><span data-stu-id="e36a6-125">[out] Optional.</span></span> <span data-ttu-id="e36a6-126">指向标志的指针, 该标志指示函数是否已在转换中使用默认字符。</span><span class="sxs-lookup"><span data-stu-id="e36a6-126">Pointer to a flag that indicates if the function has used a default character in the conversion.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e36a6-127">返回值</span><span class="sxs-lookup"><span data-stu-id="e36a6-127">Return value</span></span>

<span data-ttu-id="e36a6-128">如果成功, 则返回写入到_lpMultiByteStr_所指向的缓冲区中的字节数。</span><span class="sxs-lookup"><span data-stu-id="e36a6-128">Returns the number of bytes written to the buffer pointed to by  _lpMultiByteStr_ if successful.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e36a6-129">注解</span><span class="sxs-lookup"><span data-stu-id="e36a6-129">Remarks</span></span>

<span data-ttu-id="e36a6-130">此函数将包装**WideCharToMultiByte**函数。</span><span class="sxs-lookup"><span data-stu-id="e36a6-130">This function wraps the **WideCharToMultiByte** function.</span></span> <span data-ttu-id="e36a6-131">有关详细信息, 请参阅[WideCharToMultiByte](https://msdn.microsoft.com/library/dd374130%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e36a6-131">For more information, see [WideCharToMultiByte](https://msdn.microsoft.com/library/dd374130%28VS.85%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e36a6-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e36a6-132">See also</span></span>



[<span data-ttu-id="e36a6-133">WideCharToMultiByte</span><span class="sxs-lookup"><span data-stu-id="e36a6-133">WideCharToMultiByte</span></span>](https://msdn.microsoft.com/library/dd374130%28VS.85%29.aspx)

