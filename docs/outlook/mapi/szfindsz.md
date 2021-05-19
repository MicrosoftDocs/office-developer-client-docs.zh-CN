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
# <a name="szfindsz"></a><span data-ttu-id="cf363-103">SzFindSz</span><span class="sxs-lookup"><span data-stu-id="cf363-103">SzFindSz</span></span>

  
  
<span data-ttu-id="cf363-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cf363-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cf363-105">在以 null 结尾的字符串中查找第一次出现以 null 结尾的子字符串。</span><span class="sxs-lookup"><span data-stu-id="cf363-105">Locates the first occurrence of a null-terminated substring in a null-terminated string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cf363-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="cf363-106">Header file:</span></span>  <br/> |<span data-ttu-id="cf363-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="cf363-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="cf363-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="cf363-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="cf363-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="cf363-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="cf363-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="cf363-110">Called by:</span></span>  <br/> |<span data-ttu-id="cf363-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="cf363-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPSTR SzFindCh(
  LPCSTR lpsz,
  LPCSTR lpszKey
);
```

## <a name="parameters"></a><span data-ttu-id="cf363-112">参数</span><span class="sxs-lookup"><span data-stu-id="cf363-112">Parameters</span></span>

 <span data-ttu-id="cf363-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="cf363-113">_lpsz_</span></span>
  
> <span data-ttu-id="cf363-114">[in]指向要搜索的以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="cf363-114">[in] Pointer to the null-terminated string to be searched.</span></span> <span data-ttu-id="cf363-115">_lpsz_ 参数不能超过 65536 个字符。</span><span class="sxs-lookup"><span data-stu-id="cf363-115">The  _lpsz_ parameter must not exceed 65536 characters.</span></span> 
    
 <span data-ttu-id="cf363-116">_lpszKey_</span><span class="sxs-lookup"><span data-stu-id="cf363-116">_lpszKey_</span></span>
  
> <span data-ttu-id="cf363-117">[in]指向要搜索的以 null 结束的子字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="cf363-117">[in] Pointer to the null-terminated substring to be searched for.</span></span> <span data-ttu-id="cf363-118">_lpszKey_ 参数不能超过 65536 个字符。</span><span class="sxs-lookup"><span data-stu-id="cf363-118">The  _lpszKey_ parameter must not exceed 65536 characters.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="cf363-119">返回值</span><span class="sxs-lookup"><span data-stu-id="cf363-119">Return value</span></span>

 <span data-ttu-id="cf363-120">**SzFindSz** 返回指向字符串中子字符串第一个出现的第一个字符的指针。</span><span class="sxs-lookup"><span data-stu-id="cf363-120">**SzFindSz** returns a pointer to the first character of the first occurrence of the substring in the string.</span></span> <span data-ttu-id="cf363-121">如果子字符串未出现在字符串中的任何位置，如果  _lpszKey_ 大于  _lpsz_，或者如果任一参数为 NULL，则返回 NULL 值。</span><span class="sxs-lookup"><span data-stu-id="cf363-121">If the substring does not occur anywhere in the string, if  _lpszKey_ is larger than  _lpsz_, or if either parameter is NULL, a value of NULL is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="cf363-122">备注</span><span class="sxs-lookup"><span data-stu-id="cf363-122">Remarks</span></span>

<span data-ttu-id="cf363-123">**SzFindSz** 函数仅搜索完全匹配;区分大小写和音调差异。</span><span class="sxs-lookup"><span data-stu-id="cf363-123">The **SzFindSz** function searches for an exact match only; it is sensitive to case and diacritical differences.</span></span> <span data-ttu-id="cf363-124">支持 Unicode 和 DBCS 格式的搜索。</span><span class="sxs-lookup"><span data-stu-id="cf363-124">Searches in Unicode and DBCS formats are supported.</span></span> <span data-ttu-id="cf363-125">这两个参数的长度限制为字符，不一定是字节。</span><span class="sxs-lookup"><span data-stu-id="cf363-125">The length limit on both parameters is in characters, not necessarily bytes.</span></span> 
  

