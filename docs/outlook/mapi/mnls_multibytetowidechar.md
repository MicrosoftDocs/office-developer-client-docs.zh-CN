---
title: MNLS_MultiByteToWideChar
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 065d78bf-4c9c-48dd-b1f1-b4e59f3f1243
description: 上次修改时间：2012 年 2 月 21 日
ms.openlocfilehash: 1f137aba40703fe84e5753ee6e370262f780f0a3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338239"
---
# <a name="mnls_multibytetowidechar"></a><span data-ttu-id="38e71-103">MNLS_MultiByteToWideChar</span><span class="sxs-lookup"><span data-stu-id="38e71-103">MNLS_MultiByteToWideChar</span></span>

  
  
<span data-ttu-id="38e71-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38e71-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38e71-105">类似于 **MultiByteToWideChar**，它映射一个字符字符串到 UTF-16 (宽字符) 字符串。</span><span class="sxs-lookup"><span data-stu-id="38e71-105">Similar to **MultiByteToWideChar**, which maps a character string to a UTF-16 (wide character) string.</span></span> <span data-ttu-id="38e71-106">该字符串不一定来自多字节字符集。</span><span class="sxs-lookup"><span data-stu-id="38e71-106">The character string is not necessarily from a multibyte character set.</span></span>
  
```cpp
int MNLS_MultiByteToWideChar(
  UINT uCodePage,
  DWORD dwFlags,
  LPCSTR lpMultiByteStr,
  int cchMultiByte,
  LPWSTR lpWideCharStr,
  int cchWideChar);
```

## <a name="parameters"></a><span data-ttu-id="38e71-107">参数</span><span class="sxs-lookup"><span data-stu-id="38e71-107">Parameters</span></span>

 <span data-ttu-id="38e71-108">_uCodePage_</span><span class="sxs-lookup"><span data-stu-id="38e71-108">_uCodePage_</span></span>
  
> <span data-ttu-id="38e71-109">[in]执行转换时要使用的代码页。</span><span class="sxs-lookup"><span data-stu-id="38e71-109">[in] Code page to use in performing the conversion.</span></span>
    
 <span data-ttu-id="38e71-110">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="38e71-110">_dwFlags_</span></span>
  
> <span data-ttu-id="38e71-111">[in]指示转换类型的标志。</span><span class="sxs-lookup"><span data-stu-id="38e71-111">[in] Flags indicating the conversion type.</span></span>
    
 <span data-ttu-id="38e71-112">_lpMultiByteStr_</span><span class="sxs-lookup"><span data-stu-id="38e71-112">_lpMultiByteStr_</span></span>
  
> <span data-ttu-id="38e71-113">[in]指向要转换的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="38e71-113">[in] Pointer to the character string to convert.</span></span>
    
 <span data-ttu-id="38e71-114">_cchMultiByte_</span><span class="sxs-lookup"><span data-stu-id="38e71-114">_cchMultiByte_</span></span>
  
> <span data-ttu-id="38e71-115">[in]  _lpMultiByteStr_ 参数指示的字符串的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="38e71-115">[in] Size, in bytes, of the string indicated by the  _lpMultiByteStr_ parameter.</span></span> 
    
 <span data-ttu-id="38e71-116">_lpWideCharStr_</span><span class="sxs-lookup"><span data-stu-id="38e71-116">_lpWideCharStr_</span></span>
  
> <span data-ttu-id="38e71-117">[] out可选。</span><span class="sxs-lookup"><span data-stu-id="38e71-117">[out] Optional.</span></span> <span data-ttu-id="38e71-118">指向接收转换后的字符串的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="38e71-118">Pointer to a buffer that receives the converted string.</span></span>
    
 <span data-ttu-id="38e71-119">_cchWideChar_</span><span class="sxs-lookup"><span data-stu-id="38e71-119">_cchWideChar_</span></span>
  
> <span data-ttu-id="38e71-120">[in]由  _lpWideCharStr_ 指示的缓冲区的大小（以字符表示）。</span><span class="sxs-lookup"><span data-stu-id="38e71-120">[in] Size, in characters, of the buffer indicated by  _lpWideCharStr_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="38e71-121">返回值</span><span class="sxs-lookup"><span data-stu-id="38e71-121">Return value</span></span>

<span data-ttu-id="38e71-122">如果成功，则返回写入  _lpWideCharStr_ 指示的缓冲区的字符数。</span><span class="sxs-lookup"><span data-stu-id="38e71-122">Returns the number of characters written to the buffer indicated by  _lpWideCharStr_ if successful.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="38e71-123">备注</span><span class="sxs-lookup"><span data-stu-id="38e71-123">Remarks</span></span>

<span data-ttu-id="38e71-124">此函数包装 **MultiByteToWideChar** 函数。</span><span class="sxs-lookup"><span data-stu-id="38e71-124">This function wraps the **MultiByteToWideChar** function.</span></span> <span data-ttu-id="38e71-125">有关详细信息，请参阅 [MultiByteToWideChar](https://msdn.microsoft.com/library/dd319072%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="38e71-125">For more information, see [MultiByteToWideChar](https://msdn.microsoft.com/library/dd319072%28VS.85%29.aspx).</span></span>
  

