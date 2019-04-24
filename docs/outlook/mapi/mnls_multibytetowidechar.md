---
title: MNLS_MultiByteToWideChar
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 065d78bf-4c9c-48dd-b1f1-b4e59f3f1243
description: '上次修改时间: 2012 年2月21日'
ms.openlocfilehash: 1f137aba40703fe84e5753ee6e370262f780f0a3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338239"
---
# <a name="mnlsmultibytetowidechar"></a><span data-ttu-id="d9a23-103">MNLS_MultiByteToWideChar</span><span class="sxs-lookup"><span data-stu-id="d9a23-103">MNLS_MultiByteToWideChar</span></span>

  
  
<span data-ttu-id="d9a23-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9a23-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9a23-105">类似于**MultiByteToWideChar**, 它将字符串映射到 utf-16 (宽字符) 字符串。</span><span class="sxs-lookup"><span data-stu-id="d9a23-105">Similar to **MultiByteToWideChar**, which maps a character string to a UTF-16 (wide character) string.</span></span> <span data-ttu-id="d9a23-106">字符串不一定来自多字节字符集。</span><span class="sxs-lookup"><span data-stu-id="d9a23-106">The character string is not necessarily from a multibyte character set.</span></span>
  
```cpp
int MNLS_MultiByteToWideChar(
  UINT uCodePage,
  DWORD dwFlags,
  LPCSTR lpMultiByteStr,
  int cchMultiByte,
  LPWSTR lpWideCharStr,
  int cchWideChar);
```

## <a name="parameters"></a><span data-ttu-id="d9a23-107">参数</span><span class="sxs-lookup"><span data-stu-id="d9a23-107">Parameters</span></span>

 <span data-ttu-id="d9a23-108">_uCodePage_</span><span class="sxs-lookup"><span data-stu-id="d9a23-108">_uCodePage_</span></span>
  
> <span data-ttu-id="d9a23-109">实时要在执行转换时使用的代码页。</span><span class="sxs-lookup"><span data-stu-id="d9a23-109">[in] Code page to use in performing the conversion.</span></span>
    
 <span data-ttu-id="d9a23-110">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="d9a23-110">_dwFlags_</span></span>
  
> <span data-ttu-id="d9a23-111">实时指示转换类型的标志。</span><span class="sxs-lookup"><span data-stu-id="d9a23-111">[in] Flags indicating the conversion type.</span></span>
    
 <span data-ttu-id="d9a23-112">_lpMultiByteStr_</span><span class="sxs-lookup"><span data-stu-id="d9a23-112">_lpMultiByteStr_</span></span>
  
> <span data-ttu-id="d9a23-113">实时指向要转换的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="d9a23-113">[in] Pointer to the character string to convert.</span></span>
    
 <span data-ttu-id="d9a23-114">_cchMultiByte_</span><span class="sxs-lookup"><span data-stu-id="d9a23-114">_cchMultiByte_</span></span>
  
> <span data-ttu-id="d9a23-115">实时由_lpMultiByteStr_参数指示的字符串的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="d9a23-115">[in] Size, in bytes, of the string indicated by the  _lpMultiByteStr_ parameter.</span></span> 
    
 <span data-ttu-id="d9a23-116">_lpWideCharStr_</span><span class="sxs-lookup"><span data-stu-id="d9a23-116">_lpWideCharStr_</span></span>
  
> <span data-ttu-id="d9a23-117">[] out可选。</span><span class="sxs-lookup"><span data-stu-id="d9a23-117">[out] Optional.</span></span> <span data-ttu-id="d9a23-118">指向接收转换后的字符串的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="d9a23-118">Pointer to a buffer that receives the converted string.</span></span>
    
 <span data-ttu-id="d9a23-119">_cchWideChar_</span><span class="sxs-lookup"><span data-stu-id="d9a23-119">_cchWideChar_</span></span>
  
> <span data-ttu-id="d9a23-120">实时由_lpWideCharStr_指示的缓冲区的大小 (以字符为单位)。</span><span class="sxs-lookup"><span data-stu-id="d9a23-120">[in] Size, in characters, of the buffer indicated by  _lpWideCharStr_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d9a23-121">返回值</span><span class="sxs-lookup"><span data-stu-id="d9a23-121">Return value</span></span>

<span data-ttu-id="d9a23-122">返回在_lpWideCharStr_成功时写入缓冲区中的字符数。</span><span class="sxs-lookup"><span data-stu-id="d9a23-122">Returns the number of characters written to the buffer indicated by  _lpWideCharStr_ if successful.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="d9a23-123">注解</span><span class="sxs-lookup"><span data-stu-id="d9a23-123">Remarks</span></span>

<span data-ttu-id="d9a23-124">此函数将包装**MultiByteToWideChar**函数。</span><span class="sxs-lookup"><span data-stu-id="d9a23-124">This function wraps the **MultiByteToWideChar** function.</span></span> <span data-ttu-id="d9a23-125">有关详细信息, 请参阅[MultiByteToWideChar](https://msdn.microsoft.com/library/dd319072%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d9a23-125">For more information, see [MultiByteToWideChar](https://msdn.microsoft.com/library/dd319072%28VS.85%29.aspx).</span></span>
  

