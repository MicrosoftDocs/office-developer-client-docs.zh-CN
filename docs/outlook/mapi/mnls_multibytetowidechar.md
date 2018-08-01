---
title: MNLS_MultiByteToWideChar
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 065d78bf-4c9c-48dd-b1f1-b4e59f3f1243
description: 上次修改时间： 2012 年 2 月 21 日
ms.openlocfilehash: ab082c8ac70bf851097080fb41033f76bccc3044
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776522"
---
# <a name="mnlsmultibytetowidechar"></a><span data-ttu-id="553ae-103">MNLS_MultiByteToWideChar</span><span class="sxs-lookup"><span data-stu-id="553ae-103">MNLS_MultiByteToWideChar</span></span>

  
  
<span data-ttu-id="553ae-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="553ae-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="553ae-105">类似于**MultiByteToWideChar**，映射到 utf-16 （宽字符） 字符串的字符串。</span><span class="sxs-lookup"><span data-stu-id="553ae-105">Similar to **MultiByteToWideChar**, which maps a character string to a UTF-16 (wide character) string.</span></span> <span data-ttu-id="553ae-106">字符串不一定是从多字节字符设置。</span><span class="sxs-lookup"><span data-stu-id="553ae-106">The character string is not necessarily from a multibyte character set.</span></span>
  
```cpp
int MNLS_MultiByteToWideChar(
  UINT uCodePage,
  DWORD dwFlags,
  LPCSTR lpMultiByteStr,
  int cchMultiByte,
  LPWSTR lpWideCharStr,
  int cchWideChar);
```

## <a name="parameters"></a><span data-ttu-id="553ae-107">参数</span><span class="sxs-lookup"><span data-stu-id="553ae-107">Parameters</span></span>

 <span data-ttu-id="553ae-108">_uCodePage_</span><span class="sxs-lookup"><span data-stu-id="553ae-108">_uCodePage_</span></span>
  
> <span data-ttu-id="553ae-109">[in]用于执行转换的代码页。</span><span class="sxs-lookup"><span data-stu-id="553ae-109">[in] Code page to use in performing the conversion.</span></span>
    
 <span data-ttu-id="553ae-110">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="553ae-110">_dwFlags_</span></span>
  
> <span data-ttu-id="553ae-111">[in]标志指示的转换类型。</span><span class="sxs-lookup"><span data-stu-id="553ae-111">[in] Flags indicating the conversion type.</span></span>
    
 <span data-ttu-id="553ae-112">_lpMultiByteStr_</span><span class="sxs-lookup"><span data-stu-id="553ae-112">_lpMultiByteStr_</span></span>
  
> <span data-ttu-id="553ae-113">[in]指向要转换的字符串。</span><span class="sxs-lookup"><span data-stu-id="553ae-113">[in] Pointer to the character string to convert.</span></span>
    
 <span data-ttu-id="553ae-114">_cchMultiByte_</span><span class="sxs-lookup"><span data-stu-id="553ae-114">_cchMultiByte_</span></span>
  
> <span data-ttu-id="553ae-115">[in]大小，以字节为单位指示_lpMultiByteStr_参数的字符串。</span><span class="sxs-lookup"><span data-stu-id="553ae-115">[in] Size, in bytes, of the string indicated by the  _lpMultiByteStr_ parameter.</span></span> 
    
 <span data-ttu-id="553ae-116">_lpWideCharStr_</span><span class="sxs-lookup"><span data-stu-id="553ae-116">_lpWideCharStr_</span></span>
  
> <span data-ttu-id="553ae-117">[] out可选。</span><span class="sxs-lookup"><span data-stu-id="553ae-117">[out] Optional.</span></span> <span data-ttu-id="553ae-118">指向接收转换后的字符串的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="553ae-118">Pointer to a buffer that receives the converted string.</span></span>
    
 <span data-ttu-id="553ae-119">_cchWideChar_</span><span class="sxs-lookup"><span data-stu-id="553ae-119">_cchWideChar_</span></span>
  
> <span data-ttu-id="553ae-120">[in]以字符为单位，由_lpWideCharStr_缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="553ae-120">[in] Size, in characters, of the buffer indicated by  _lpWideCharStr_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="553ae-121">返回值</span><span class="sxs-lookup"><span data-stu-id="553ae-121">Return value</span></span>

<span data-ttu-id="553ae-122">返回写入由_lpWideCharStr_ ，如果成功缓冲区的字符的数。</span><span class="sxs-lookup"><span data-stu-id="553ae-122">Returns the number of characters written to the buffer indicated by  _lpWideCharStr_ if successful.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="553ae-123">说明</span><span class="sxs-lookup"><span data-stu-id="553ae-123">Remarks</span></span>

<span data-ttu-id="553ae-124">此函数的换行**MultiByteToWideChar**函数。</span><span class="sxs-lookup"><span data-stu-id="553ae-124">This function wraps the **MultiByteToWideChar** function.</span></span> <span data-ttu-id="553ae-125">有关详细信息，请参阅[MultiByteToWideChar](http://msdn.microsoft.com/en-us/library/dd319072%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="553ae-125">For more information, see [MultiByteToWideChar](http://msdn.microsoft.com/en-us/library/dd319072%28VS.85%29.aspx).</span></span>
  

