---
title: MNLS_WideCharToMultiByte
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f64cde12-7ed1-444f-8ca4-51cb3ea514cf
description: 上次修改时间： 2012 年 2 月 21 日
ms.openlocfilehash: ad41f9b6060e5cfbabecfd9bb29a47815929d6b5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385513"
---
# <a name="mnlswidechartomultibyte"></a><span data-ttu-id="59ed1-103">MNLS_WideCharToMultiByte</span><span class="sxs-lookup"><span data-stu-id="59ed1-103">MNLS_WideCharToMultiByte</span></span>

  
  
<span data-ttu-id="59ed1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="59ed1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="59ed1-105">此函数是类似于**WideCharToMultiByte**，映射到新的字符串的 utf-16 （宽字符） 字符串。</span><span class="sxs-lookup"><span data-stu-id="59ed1-105">This function is similar to **WideCharToMultiByte**, which maps a UTF-16 (wide character) string to a new character string.</span></span> <span data-ttu-id="59ed1-106">新的字符串不一定是从多字节字符设置。</span><span class="sxs-lookup"><span data-stu-id="59ed1-106">The new character string is not necessarily from a multibyte character set.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="59ed1-107">参数</span><span class="sxs-lookup"><span data-stu-id="59ed1-107">Parameters</span></span>

 <span data-ttu-id="59ed1-108">_uCodePage_</span><span class="sxs-lookup"><span data-stu-id="59ed1-108">_uCodePage_</span></span>
  
> <span data-ttu-id="59ed1-109">[in]用于执行转换的代码页。</span><span class="sxs-lookup"><span data-stu-id="59ed1-109">[in] Code page to use in performing the conversion.</span></span>
    
 <span data-ttu-id="59ed1-110">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="59ed1-110">_dwFlags_</span></span>
  
> <span data-ttu-id="59ed1-111">[in]标志指示的转换类型。</span><span class="sxs-lookup"><span data-stu-id="59ed1-111">[in] Flags indicating the conversion type.</span></span>
    
 <span data-ttu-id="59ed1-112">_lpWideCharStr_</span><span class="sxs-lookup"><span data-stu-id="59ed1-112">_lpWideCharStr_</span></span>
  
> <span data-ttu-id="59ed1-113">[in]指向要转换的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="59ed1-113">[in] Pointer to the Unicode string to convert.</span></span>
    
 <span data-ttu-id="59ed1-114">_cchWideChar_</span><span class="sxs-lookup"><span data-stu-id="59ed1-114">_cchWideChar_</span></span>
  
> <span data-ttu-id="59ed1-115">[in]标志指示的转换类型。</span><span class="sxs-lookup"><span data-stu-id="59ed1-115">[in] Flags indicating the conversion type.</span></span>
    
 <span data-ttu-id="59ed1-116">_lpMultiByteStr_</span><span class="sxs-lookup"><span data-stu-id="59ed1-116">_lpMultiByteStr_</span></span>
  
> <span data-ttu-id="59ed1-117">[] out可选。</span><span class="sxs-lookup"><span data-stu-id="59ed1-117">[out] Optional.</span></span> <span data-ttu-id="59ed1-118">指向接收转换后的字符串的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="59ed1-118">Pointer to a buffer that receives the converted string.</span></span>
    
 <span data-ttu-id="59ed1-119">_cchMultiByte_</span><span class="sxs-lookup"><span data-stu-id="59ed1-119">_cchMultiByte_</span></span>
  
> <span data-ttu-id="59ed1-120">[in]以字节为单位指示_lpMultiByteStr_缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="59ed1-120">[in] Size, in bytes, of the buffer indicated by  _lpMultiByteStr_.</span></span>
    
 <span data-ttu-id="59ed1-121">_lpDefaultChar_</span><span class="sxs-lookup"><span data-stu-id="59ed1-121">_lpDefaultChar_</span></span>
  
> <span data-ttu-id="59ed1-122">[中]可选。</span><span class="sxs-lookup"><span data-stu-id="59ed1-122">[in] Optional.</span></span> <span data-ttu-id="59ed1-123">指向要使用如果字符不能表示指定的代码页中的字符。</span><span class="sxs-lookup"><span data-stu-id="59ed1-123">Pointer to the character to use if a character cannot be represented in the specified code page.</span></span>
    
 <span data-ttu-id="59ed1-124">_lpfUsedDefaultChar_</span><span class="sxs-lookup"><span data-stu-id="59ed1-124">_lpfUsedDefaultChar_</span></span>
  
> <span data-ttu-id="59ed1-125">[] out可选。</span><span class="sxs-lookup"><span data-stu-id="59ed1-125">[out] Optional.</span></span> <span data-ttu-id="59ed1-126">指向一个标志，指示该函数已转换中使用默认的字符。</span><span class="sxs-lookup"><span data-stu-id="59ed1-126">Pointer to a flag that indicates if the function has used a default character in the conversion.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="59ed1-127">返回值</span><span class="sxs-lookup"><span data-stu-id="59ed1-127">Return value</span></span>

<span data-ttu-id="59ed1-128">返回写入如果成功_lpMultiByteStr_指向缓冲区的字节数。</span><span class="sxs-lookup"><span data-stu-id="59ed1-128">Returns the number of bytes written to the buffer pointed to by  _lpMultiByteStr_ if successful.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="59ed1-129">说明</span><span class="sxs-lookup"><span data-stu-id="59ed1-129">Remarks</span></span>

<span data-ttu-id="59ed1-130">此函数的换行**WideCharToMultiByte**函数。</span><span class="sxs-lookup"><span data-stu-id="59ed1-130">This function wraps the **WideCharToMultiByte** function.</span></span> <span data-ttu-id="59ed1-131">有关详细信息，请参阅[WideCharToMultiByte](https://msdn.microsoft.com/library/dd374130%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="59ed1-131">For more information, see [WideCharToMultiByte](https://msdn.microsoft.com/library/dd374130%28VS.85%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="59ed1-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59ed1-132">See also</span></span>



[<span data-ttu-id="59ed1-133">WideCharToMultiByte</span><span class="sxs-lookup"><span data-stu-id="59ed1-133">WideCharToMultiByte</span></span>](https://msdn.microsoft.com/library/dd374130%28VS.85%29.aspx)

