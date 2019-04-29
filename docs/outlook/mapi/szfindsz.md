---
title: SzFindSz
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SzFindSz
api_type:
- COM
ms.assetid: f4584569-1246-4ac9-a404-48284e4920d7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9fc21a27cb6c9041bdd8976ce5f030f0ab9eb57f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435220"
---
# <a name="szfindsz"></a><span data-ttu-id="0f151-103">SzFindSz</span><span class="sxs-lookup"><span data-stu-id="0f151-103">SzFindSz</span></span>

  
  
<span data-ttu-id="0f151-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f151-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0f151-105">在以 null 结尾的字符串中查找以 null 结尾的子字符串的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="0f151-105">Locates the first occurrence of a null-terminated substring in a null-terminated string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0f151-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0f151-106">Header file:</span></span>  <br/> |<span data-ttu-id="0f151-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="0f151-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="0f151-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="0f151-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="0f151-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="0f151-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="0f151-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="0f151-110">Called by:</span></span>  <br/> |<span data-ttu-id="0f151-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="0f151-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPSTR SzFindCh(
  LPCSTR lpsz,
  LPCSTR lpszKey
);
```

## <a name="parameters"></a><span data-ttu-id="0f151-112">参数</span><span class="sxs-lookup"><span data-stu-id="0f151-112">Parameters</span></span>

 <span data-ttu-id="0f151-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="0f151-113">_lpsz_</span></span>
  
> <span data-ttu-id="0f151-114">实时指向要搜索的以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="0f151-114">[in] Pointer to the null-terminated string to be searched.</span></span> <span data-ttu-id="0f151-115">_lpsz_参数不能超过65536个字符。</span><span class="sxs-lookup"><span data-stu-id="0f151-115">The  _lpsz_ parameter must not exceed 65536 characters.</span></span> 
    
 <span data-ttu-id="0f151-116">_lpszKey_</span><span class="sxs-lookup"><span data-stu-id="0f151-116">_lpszKey_</span></span>
  
> <span data-ttu-id="0f151-117">实时指向要搜索的以 null 结尾的子字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="0f151-117">[in] Pointer to the null-terminated substring to be searched for.</span></span> <span data-ttu-id="0f151-118">_lpszKey_参数不能超过65536个字符。</span><span class="sxs-lookup"><span data-stu-id="0f151-118">The  _lpszKey_ parameter must not exceed 65536 characters.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0f151-119">返回值</span><span class="sxs-lookup"><span data-stu-id="0f151-119">Return value</span></span>

 <span data-ttu-id="0f151-120">**SzFindSz**返回一个指针, 指向字符串中的子字符串的第一个匹配项的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="0f151-120">**SzFindSz** returns a pointer to the first character of the first occurrence of the substring in the string.</span></span> <span data-ttu-id="0f151-121">如果子字符串不出现在字符串中的任何位置, 如果_lpszKey_大于_lpsz_, 或者任一参数为 null, 则返回 null 值。</span><span class="sxs-lookup"><span data-stu-id="0f151-121">If the substring does not occur anywhere in the string, if  _lpszKey_ is larger than  _lpsz_, or if either parameter is NULL, a value of NULL is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="0f151-122">说明</span><span class="sxs-lookup"><span data-stu-id="0f151-122">Remarks</span></span>

<span data-ttu-id="0f151-123">**SzFindSz**函数仅搜索完全匹配项;区分大小写和变音差异。</span><span class="sxs-lookup"><span data-stu-id="0f151-123">The **SzFindSz** function searches for an exact match only; it is sensitive to case and diacritical differences.</span></span> <span data-ttu-id="0f151-124">支持以 Unicode 和 DBCS 格式搜索。</span><span class="sxs-lookup"><span data-stu-id="0f151-124">Searches in Unicode and DBCS formats are supported.</span></span> <span data-ttu-id="0f151-125">这两个参数的长度限制为字符, 而不一定是字节。</span><span class="sxs-lookup"><span data-stu-id="0f151-125">The length limit on both parameters is in characters, not necessarily bytes.</span></span> 
  

