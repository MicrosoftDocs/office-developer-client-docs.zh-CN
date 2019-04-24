---
title: SzFindCh
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SzFindCh
api_type:
- COM
ms.assetid: 3406d060-bfea-4cea-8253-2a9aeb9e8147
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 522c67b19656c00ea169def98a42ca2b3c1db840
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345239"
---
# <a name="szfindch"></a><span data-ttu-id="61069-103">SzFindCh</span><span class="sxs-lookup"><span data-stu-id="61069-103">SzFindCh</span></span>
 
<span data-ttu-id="61069-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="61069-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="61069-105">在以 null 结尾的字符串中搜索字符的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="61069-105">Searches for the first occurrence of a character in a null-terminated string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="61069-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="61069-106">Header file:</span></span>  <br/> |<span data-ttu-id="61069-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="61069-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="61069-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="61069-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="61069-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="61069-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="61069-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="61069-110">Called by:</span></span>  <br/> |<span data-ttu-id="61069-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="61069-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPSTR SzFindCh(
  LPCSTR lpsz,
  USHORT ch
);
```

## <a name="parameters"></a><span data-ttu-id="61069-112">参数</span><span class="sxs-lookup"><span data-stu-id="61069-112">Parameters</span></span>

<span data-ttu-id="61069-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="61069-113">_lpsz_</span></span>
  
> <span data-ttu-id="61069-114">实时指向要搜索的以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="61069-114">[in] Pointer to the null-terminated string to be searched.</span></span> 
    
<span data-ttu-id="61069-115">_章_</span><span class="sxs-lookup"><span data-stu-id="61069-115">_ch_</span></span>
  
> <span data-ttu-id="61069-116">实时要搜索的字符。</span><span class="sxs-lookup"><span data-stu-id="61069-116">[in] The character to be searched for.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="61069-117">返回值</span><span class="sxs-lookup"><span data-stu-id="61069-117">Return value</span></span>

<span data-ttu-id="61069-118">**SzFindCh**返回一个指针, 指向字符串中字符的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="61069-118">**SzFindCh** returns a pointer to the first occurrence of the character in the string.</span></span> <span data-ttu-id="61069-119">如果该字符未出现在字符串中的任何位置, 或者如果_lpsz_参数为 null, 则返回值 null。</span><span class="sxs-lookup"><span data-stu-id="61069-119">If the character does not occur anywhere in the string, or if the  _lpsz_ parameter is NULL, a value of NULL is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="61069-120">注解</span><span class="sxs-lookup"><span data-stu-id="61069-120">Remarks</span></span>

<span data-ttu-id="61069-121">**SzFindCh**函数仅搜索完全匹配项;区分大小写和变音差异。</span><span class="sxs-lookup"><span data-stu-id="61069-121">The **SzFindCh** function searches for an exact match only; it is sensitive to case and diacritical differences.</span></span> <span data-ttu-id="61069-122">支持在 Unicode 和 DBCS 格式的搜索中进行搜索。</span><span class="sxs-lookup"><span data-stu-id="61069-122">Searches in the Unicode and DBCS formats are supported.</span></span> 
  

