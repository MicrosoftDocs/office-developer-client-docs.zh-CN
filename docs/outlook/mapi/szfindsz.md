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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0cc8f25271d1494ebdaca82caa2e77839f299276
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778947"
---
# <a name="szfindsz"></a><span data-ttu-id="65f89-103">SzFindSz</span><span class="sxs-lookup"><span data-stu-id="65f89-103">SzFindSz</span></span>

  
  
<span data-ttu-id="65f89-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="65f89-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="65f89-105">在以 null 结尾的字符串中查找第一个出现的以 null 结尾的子字符串。</span><span class="sxs-lookup"><span data-stu-id="65f89-105">Locates the first occurrence of a null-terminated substring in a null-terminated string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="65f89-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="65f89-106">Header file:</span></span>  <br/> |<span data-ttu-id="65f89-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="65f89-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="65f89-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="65f89-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="65f89-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="65f89-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="65f89-110">调用：</span><span class="sxs-lookup"><span data-stu-id="65f89-110">Called by:</span></span>  <br/> |<span data-ttu-id="65f89-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="65f89-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPSTR SzFindCh(
  LPCSTR lpsz,
  LPCSTR lpszKey
);
```

## <a name="parameters"></a><span data-ttu-id="65f89-112">参数</span><span class="sxs-lookup"><span data-stu-id="65f89-112">Parameters</span></span>

 <span data-ttu-id="65f89-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="65f89-113">_lpsz_</span></span>
  
> <span data-ttu-id="65f89-114">[in]指向以 null 结尾的字符串，要搜索的指针。</span><span class="sxs-lookup"><span data-stu-id="65f89-114">[in] Pointer to the null-terminated string to be searched.</span></span> <span data-ttu-id="65f89-115">_Lpsz_参数不能超过 65536 个字符。</span><span class="sxs-lookup"><span data-stu-id="65f89-115">The  _lpsz_ parameter must not exceed 65536 characters.</span></span> 
    
 <span data-ttu-id="65f89-116">_lpszKey_</span><span class="sxs-lookup"><span data-stu-id="65f89-116">_lpszKey_</span></span>
  
> <span data-ttu-id="65f89-117">[in]指向 null 结尾的子字符串搜索的指针。</span><span class="sxs-lookup"><span data-stu-id="65f89-117">[in] Pointer to the null-terminated substring to be searched for.</span></span> <span data-ttu-id="65f89-118">_LpszKey_参数不能超过 65536 个字符。</span><span class="sxs-lookup"><span data-stu-id="65f89-118">The  _lpszKey_ parameter must not exceed 65536 characters.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="65f89-119">返回值</span><span class="sxs-lookup"><span data-stu-id="65f89-119">Return value</span></span>

 <span data-ttu-id="65f89-120">**SzFindSz**返回字符串中的子字符串的第一个匹配项的第一个字符的指针。</span><span class="sxs-lookup"><span data-stu-id="65f89-120">**SzFindSz** returns a pointer to the first character of the first occurrence of the substring in the string.</span></span> <span data-ttu-id="65f89-121">如果子字符串不会发生无处不在字符串中，如果_lpszKey_大于_lpsz_，或者如果任一参数为 NULL，则返回 NULL 值。</span><span class="sxs-lookup"><span data-stu-id="65f89-121">If the substring does not occur anywhere in the string, if  _lpszKey_ is larger than  _lpsz_, or if either parameter is NULL, a value of NULL is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="65f89-122">备注</span><span class="sxs-lookup"><span data-stu-id="65f89-122">Remarks</span></span>

<span data-ttu-id="65f89-123">**SzFindSz**功能将搜索完全匹配只;它是敏感案例和发音差异。</span><span class="sxs-lookup"><span data-stu-id="65f89-123">The **SzFindSz** function searches for an exact match only; it is sensitive to case and diacritical differences.</span></span> <span data-ttu-id="65f89-124">支持 Unicode 和 DBCS 格式的搜索。</span><span class="sxs-lookup"><span data-stu-id="65f89-124">Searches in Unicode and DBCS formats are supported.</span></span> <span data-ttu-id="65f89-125">以字符为单位，不必字节有两个参数的长度限制。</span><span class="sxs-lookup"><span data-stu-id="65f89-125">The length limit on both parameters is in characters, not necessarily bytes.</span></span> 
  

