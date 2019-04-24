---
title: CheckParms
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.CheckParms
api_type:
- COM
ms.assetid: 328f12f0-e4e7-407f-8eb8-0d4bf543962d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ffa1b596b2f60bce35f24df8a20326502be8165a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331799"
---
# <a name="checkparms"></a><span data-ttu-id="6b540-103">CheckParms</span><span class="sxs-lookup"><span data-stu-id="6b540-103">CheckParms</span></span>

  
  
<span data-ttu-id="6b540-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6b540-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6b540-105">调用内部函数来验证 MAPI 调用的服务提供程序方法的调试参数。</span><span class="sxs-lookup"><span data-stu-id="6b540-105">Calls an internal function to validate debugging parameters on service provider methods called by MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6b540-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6b540-106">Header file:</span></span>  <br/> |<span data-ttu-id="6b540-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="6b540-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="6b540-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="6b540-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="6b540-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="6b540-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="6b540-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="6b540-110">Called by:</span></span>  <br/> |<span data-ttu-id="6b540-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="6b540-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT CheckParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="6b540-112">参数</span><span class="sxs-lookup"><span data-stu-id="6b540-112">Parameters</span></span>

 <span data-ttu-id="6b540-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="6b540-113">_eMethod_</span></span>
  
> <span data-ttu-id="6b540-114">实时通过枚举指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="6b540-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="6b540-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="6b540-115">_First_</span></span>
  
> <span data-ttu-id="6b540-116">实时指向堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="6b540-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6b540-117">返回值</span><span class="sxs-lookup"><span data-stu-id="6b540-117">Return value</span></span>

<span data-ttu-id="6b540-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b540-118">S_OK</span></span> 
  
> <span data-ttu-id="6b540-119">调用成功。</span><span class="sxs-lookup"><span data-stu-id="6b540-119">The call succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6b540-120">注解</span><span class="sxs-lookup"><span data-stu-id="6b540-120">Remarks</span></span>

<span data-ttu-id="6b540-121">与[ValidateParms](validateparms.md)和[UlValidateParms](ulvalidateparms.md)宏相反, **CheckParms**宏不执行完整参数验证。</span><span class="sxs-lookup"><span data-stu-id="6b540-121">In contrast to the [ValidateParms](validateparms.md) and [UlValidateParms](ulvalidateparms.md) macros, the **CheckParms** macro does not perform a full parameter validation.</span></span> <span data-ttu-id="6b540-122">假定在 MAPI 和服务提供程序之间传递的参数是正确的, 因此**CheckParms**仅执行调试验证。</span><span class="sxs-lookup"><span data-stu-id="6b540-122">Parameters passed between MAPI and service providers are assumed to be correct, so **CheckParms** performs a debug validation only.</span></span> 
  

