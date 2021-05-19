---
title: SzFindLastCh
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SzFindLastCh
api_type:
- COM
ms.assetid: 7c3e5a71-7b78-4328-b8ee-265cc4da4be5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f22d30c1bc7c797834f58bcd1306b14ac2542c6d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421254"
---
# <a name="szfindlastch"></a><span data-ttu-id="576c4-103">SzFindLastCh</span><span class="sxs-lookup"><span data-stu-id="576c4-103">SzFindLastCh</span></span>

  
  
<span data-ttu-id="576c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="576c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="576c4-105">在以 null 结尾的字符串中搜索最后一次出现的字符。</span><span class="sxs-lookup"><span data-stu-id="576c4-105">Searches for the last occurrence of a character in a null-terminated string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="576c4-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="576c4-106">Header file:</span></span>  <br/> |<span data-ttu-id="576c4-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="576c4-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="576c4-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="576c4-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="576c4-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="576c4-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="576c4-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="576c4-110">Called by:</span></span>  <br/> |<span data-ttu-id="576c4-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="576c4-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPSTR SzFindLastCh(
  LPCSTR lpsz,
  USHORT ch
);
```

## <a name="parameters"></a><span data-ttu-id="576c4-112">参数</span><span class="sxs-lookup"><span data-stu-id="576c4-112">Parameters</span></span>

 <span data-ttu-id="576c4-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="576c4-113">_lpsz_</span></span>
  
> <span data-ttu-id="576c4-114">[in]指向要搜索的以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="576c4-114">[in] Pointer to the null-terminated string to be searched.</span></span> 
    
 <span data-ttu-id="576c4-115">_ch_</span><span class="sxs-lookup"><span data-stu-id="576c4-115">_ch_</span></span>
  
> <span data-ttu-id="576c4-116">[in]要搜索的字符。</span><span class="sxs-lookup"><span data-stu-id="576c4-116">[in] The character to be searched for.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="576c4-117">返回值</span><span class="sxs-lookup"><span data-stu-id="576c4-117">Return value</span></span>

 <span data-ttu-id="576c4-118">**SzFindLastCh** 返回指向字符串中最后出现的字符的指针。</span><span class="sxs-lookup"><span data-stu-id="576c4-118">**SzFindLastCh** returns a pointer to the last occurrence of the character in the string.</span></span> <span data-ttu-id="576c4-119">如果该字符不在字符串中的任何位置出现，或者  _lpsz_ 参数为 NULL，则返回 NULL 值。</span><span class="sxs-lookup"><span data-stu-id="576c4-119">If the character does not occur anywhere in the string, or if the  _lpsz_ parameter is NULL, a value of NULL is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="576c4-120">备注</span><span class="sxs-lookup"><span data-stu-id="576c4-120">Remarks</span></span>

<span data-ttu-id="576c4-121">**SzFindLastCh** 函数仅搜索完全匹配;区分大小写和音调差异。</span><span class="sxs-lookup"><span data-stu-id="576c4-121">The **SzFindLastCh** function searches for an exact match only; it is sensitive to case and diacritical differences.</span></span> <span data-ttu-id="576c4-122">支持 Unicode 和 DBCS 格式的搜索。</span><span class="sxs-lookup"><span data-stu-id="576c4-122">Searches in the Unicode and DBCS formats are supported.</span></span> 
  

