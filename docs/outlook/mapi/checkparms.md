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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422276"
---
# <a name="checkparms"></a><span data-ttu-id="dbd88-103">CheckParms</span><span class="sxs-lookup"><span data-stu-id="dbd88-103">CheckParms</span></span>

  
  
<span data-ttu-id="dbd88-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dbd88-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dbd88-105">调用内部函数来验证 MAPI 调用的服务提供程序方法的调试参数。</span><span class="sxs-lookup"><span data-stu-id="dbd88-105">Calls an internal function to validate debugging parameters on service provider methods called by MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dbd88-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="dbd88-106">Header file:</span></span>  <br/> |<span data-ttu-id="dbd88-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="dbd88-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="dbd88-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="dbd88-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="dbd88-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="dbd88-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="dbd88-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="dbd88-110">Called by:</span></span>  <br/> |<span data-ttu-id="dbd88-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="dbd88-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT CheckParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="dbd88-112">参数</span><span class="sxs-lookup"><span data-stu-id="dbd88-112">Parameters</span></span>

 <span data-ttu-id="dbd88-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="dbd88-113">_eMethod_</span></span>
  
> <span data-ttu-id="dbd88-114">实时通过枚举指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="dbd88-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="dbd88-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="dbd88-115">_First_</span></span>
  
> <span data-ttu-id="dbd88-116">实时指向堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="dbd88-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="dbd88-117">返回值</span><span class="sxs-lookup"><span data-stu-id="dbd88-117">Return value</span></span>

<span data-ttu-id="dbd88-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbd88-118">S_OK</span></span> 
  
> <span data-ttu-id="dbd88-119">调用成功。</span><span class="sxs-lookup"><span data-stu-id="dbd88-119">The call succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dbd88-120">说明</span><span class="sxs-lookup"><span data-stu-id="dbd88-120">Remarks</span></span>

<span data-ttu-id="dbd88-121">与[ValidateParms](validateparms.md)和[UlValidateParms](ulvalidateparms.md)宏相反, **CheckParms**宏不执行完整参数验证。</span><span class="sxs-lookup"><span data-stu-id="dbd88-121">In contrast to the [ValidateParms](validateparms.md) and [UlValidateParms](ulvalidateparms.md) macros, the **CheckParms** macro does not perform a full parameter validation.</span></span> <span data-ttu-id="dbd88-122">假定在 MAPI 和服务提供程序之间传递的参数是正确的, 因此**CheckParms**仅执行调试验证。</span><span class="sxs-lookup"><span data-stu-id="dbd88-122">Parameters passed between MAPI and service providers are assumed to be correct, so **CheckParms** performs a debug validation only.</span></span> 
  

