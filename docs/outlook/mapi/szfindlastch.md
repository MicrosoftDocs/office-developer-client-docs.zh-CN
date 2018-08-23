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
ms.openlocfilehash: eeeff110e5de592d491865079adfa187e5dfa194
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570875"
---
# <a name="szfindlastch"></a><span data-ttu-id="ebaba-103">SzFindLastCh</span><span class="sxs-lookup"><span data-stu-id="ebaba-103">SzFindLastCh</span></span>

  
  
<span data-ttu-id="ebaba-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ebaba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ebaba-105">搜索的以 null 结尾的字符串中的字符的最后一个实例。</span><span class="sxs-lookup"><span data-stu-id="ebaba-105">Searches for the last occurrence of a character in a null-terminated string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ebaba-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ebaba-106">Header file:</span></span>  <br/> |<span data-ttu-id="ebaba-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ebaba-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="ebaba-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ebaba-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ebaba-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ebaba-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ebaba-110">调用：</span><span class="sxs-lookup"><span data-stu-id="ebaba-110">Called by:</span></span>  <br/> |<span data-ttu-id="ebaba-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="ebaba-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPSTR SzFindLastCh(
  LPCSTR lpsz,
  USHORT ch
);
```

## <a name="parameters"></a><span data-ttu-id="ebaba-112">参数</span><span class="sxs-lookup"><span data-stu-id="ebaba-112">Parameters</span></span>

 <span data-ttu-id="ebaba-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="ebaba-113">_lpsz_</span></span>
  
> <span data-ttu-id="ebaba-114">[in]指向以 null 结尾的字符串，要搜索的指针。</span><span class="sxs-lookup"><span data-stu-id="ebaba-114">[in] Pointer to the null-terminated string to be searched.</span></span> 
    
 <span data-ttu-id="ebaba-115">_频道_</span><span class="sxs-lookup"><span data-stu-id="ebaba-115">_ch_</span></span>
  
> <span data-ttu-id="ebaba-116">[in]要搜索的字符。</span><span class="sxs-lookup"><span data-stu-id="ebaba-116">[in] The character to be searched for.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ebaba-117">返回值</span><span class="sxs-lookup"><span data-stu-id="ebaba-117">Return value</span></span>

 <span data-ttu-id="ebaba-118">**SzFindLastCh**返回到字符串中的字符的最后一个匹配项的指针。</span><span class="sxs-lookup"><span data-stu-id="ebaba-118">**SzFindLastCh** returns a pointer to the last occurrence of the character in the string.</span></span> <span data-ttu-id="ebaba-119">如果字符，不会发生无处不在字符串中，或者如果_lpsz_参数为 NULL，则返回 NULL 的值。</span><span class="sxs-lookup"><span data-stu-id="ebaba-119">If the character does not occur anywhere in the string, or if the  _lpsz_ parameter is NULL, a value of NULL is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ebaba-120">注解</span><span class="sxs-lookup"><span data-stu-id="ebaba-120">Remarks</span></span>

<span data-ttu-id="ebaba-121">**SzFindLastCh**功能将搜索完全匹配只;它是敏感案例和发音差异。</span><span class="sxs-lookup"><span data-stu-id="ebaba-121">The **SzFindLastCh** function searches for an exact match only; it is sensitive to case and diacritical differences.</span></span> <span data-ttu-id="ebaba-122">支持 Unicode 和 DBCS 格式的搜索。</span><span class="sxs-lookup"><span data-stu-id="ebaba-122">Searches in the Unicode and DBCS formats are supported.</span></span> 
  

