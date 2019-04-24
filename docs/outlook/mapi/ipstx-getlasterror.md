---
title: IPSTXGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTX.GetLastError
api_type:
- COM
ms.assetid: 68dc0ecc-881e-de69-faaa-90acb9857031
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1d0fb16ba63548a44dba3920670c0e65f8c700a1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315097"
---
# <a name="ipstxgetlasterror"></a><span data-ttu-id="d109c-103">IPSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="d109c-103">IPSTX::GetLastError</span></span>

  
  
<span data-ttu-id="d109c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d109c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d109c-105">获取有关上一个错误的扩展信息。</span><span class="sxs-lookup"><span data-stu-id="d109c-105">Gets extended information about the last error.</span></span>
  
```cpp
HRESULT GetLastError( 
    HRESULT hResult, 
    ULONG ulFlags, 
    LPMAPIERROR *lppMAPIError 
);
```

## <a name="parameters"></a><span data-ttu-id="d109c-106">参数</span><span class="sxs-lookup"><span data-stu-id="d109c-106">Parameters</span></span>

 <span data-ttu-id="d109c-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="d109c-107">_hResult_</span></span>
  
>  <span data-ttu-id="d109c-108">实时错误代码。</span><span class="sxs-lookup"><span data-stu-id="d109c-108">[in] Error code.</span></span> 
    
 <span data-ttu-id="d109c-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d109c-109">_ulFlags_</span></span>
  
>  <span data-ttu-id="d109c-110">[] in若要修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="d109c-110">[in] Flags to modify behavior.</span></span> <span data-ttu-id="d109c-111">该值必须为0。</span><span class="sxs-lookup"><span data-stu-id="d109c-111">This must be 0.</span></span> 
    
 <span data-ttu-id="d109c-112">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="d109c-112">_lppMAPIError_</span></span>
  
>  <span data-ttu-id="d109c-113">排除指向包含错误的扩展信息的**MAPIERROR**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="d109c-113">[out] Pointer to the **MAPIERROR** structure that contains the extended information for the error.</span></span> <span data-ttu-id="d109c-114">有关**LPMAPIERROR**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="d109c-114">See mapidefs.h for the type definition of **LPMAPIERROR**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="d109c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d109c-115">See also</span></span>



[<span data-ttu-id="d109c-116">IPSTX::EmulateSpooler</span><span class="sxs-lookup"><span data-stu-id="d109c-116">IPSTX::EmulateSpooler</span></span>](ipstx-emulatespooler.md)
  
[<span data-ttu-id="d109c-117">IPSTX::GetSyncObject</span><span class="sxs-lookup"><span data-stu-id="d109c-117">IPSTX::GetSyncObject</span></span>](ipstx-getsyncobject.md)

