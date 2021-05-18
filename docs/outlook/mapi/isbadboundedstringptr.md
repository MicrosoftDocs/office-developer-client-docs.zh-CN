---
title: IsBadBoundedStringPtr
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 888c60e3-7376-4d66-8ee2-ce81abafb185
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9d5ebb0e16138c3cc65ff6fd7c635e5498c9c1ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278832"
---
# <a name="isbadboundedstringptr"></a><span data-ttu-id="d9542-103">IsBadBoundedStringPtr</span><span class="sxs-lookup"><span data-stu-id="d9542-103">IsBadBoundedStringPtr</span></span>

  
  
<span data-ttu-id="d9542-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9542-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9542-105">验证调用进程是否具有对指定内存范围的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="d9542-105">Verifies that the calling process has read access to the specified range of memory.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d9542-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d9542-106">Header file:</span></span>  <br/> |<span data-ttu-id="d9542-107">mapiwin.h</span><span class="sxs-lookup"><span data-stu-id="d9542-107">mapiwin.h</span></span>  <br/> |
|<span data-ttu-id="d9542-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="d9542-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d9542-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d9542-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d9542-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="d9542-110">Called by:</span></span>  <br/> |<span data-ttu-id="d9542-111">客户端应用程序和服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="d9542-111">Client applications and service providers.</span></span>  <br/> |
   
```cpp
BOOL IsBadBoundedStringPtr(
  const void FAR* lpsz,
  UINT cchMax
);
```

## <a name="parameters"></a><span data-ttu-id="d9542-112">参数</span><span class="sxs-lookup"><span data-stu-id="d9542-112">Parameters</span></span>

 <span data-ttu-id="d9542-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="d9542-113">_lpsz_</span></span>
  
> <span data-ttu-id="d9542-114">[in]指向以 null 结尾的 ASCII 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="d9542-114">[in] Pointer to a null-terminated ASCII string.</span></span>
    
 <span data-ttu-id="d9542-115">_cchMax_</span><span class="sxs-lookup"><span data-stu-id="d9542-115">_cchMax_</span></span>
  
> <span data-ttu-id="d9542-116">[in]字符串的最大大小，以 CHAR 表示。</span><span class="sxs-lookup"><span data-stu-id="d9542-116">[in] The maximum size of the string, in CHARs.</span></span> <span data-ttu-id="d9542-117">该函数检查所有字符（最多为字符串的终止 null 字符）或此参数指定的字符数（以较小者为准）的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="d9542-117">The function checks for read access in all characters up to the terminating null character of the string, or up to the number of characters specified by this parameter, whichever is smaller.</span></span> <span data-ttu-id="d9542-118">如果此参数为零，则返回值为 0。</span><span class="sxs-lookup"><span data-stu-id="d9542-118">If this parameter is zero, the return value is zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d9542-119">返回值</span><span class="sxs-lookup"><span data-stu-id="d9542-119">Return value</span></span>

<span data-ttu-id="d9542-120">当调用进程具有对字符串的终止 null 字符的读取访问权限，或读取访问权限最多为  _cchMax_ 指定的字符数时，返回值是零。</span><span class="sxs-lookup"><span data-stu-id="d9542-120">The return value is zero when the calling process has read access to all characters up to the terminating null character of the string, or read access up to the number of characters specified by  _cchMax_.</span></span>
  
<span data-ttu-id="d9542-121">当调用进程没有对字符串的终止 null 字符之前的所有字符的读取访问权限，或读取访问权最多为  _cchMax_ 指定的字符数时，返回值不为零。</span><span class="sxs-lookup"><span data-stu-id="d9542-121">The return value is non-zero when the calling process does not have read access to all characters up to the terminating null character of the string, or read access up to the number of characters specified by  _cchMax_.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d9542-122">备注</span><span class="sxs-lookup"><span data-stu-id="d9542-122">Remarks</span></span>

<span data-ttu-id="d9542-123">**IsBadBoundedStringPtr** 函数等效于使用 **IsBadStringPtr**。</span><span class="sxs-lookup"><span data-stu-id="d9542-123">The **IsBadBoundedStringPtr** function is equivalent to using **IsBadStringPtr**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9542-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9542-124">See also</span></span>



[<span data-ttu-id="d9542-125">IsBadStringPtr</span><span class="sxs-lookup"><span data-stu-id="d9542-125">IsBadStringPtr</span></span>](https://msdn.microsoft.com/library/windows/desktop/aa366714%28v=vs.85%29.aspx)

