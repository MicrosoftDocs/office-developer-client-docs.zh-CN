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
ms.openlocfilehash: 5732dd3c1587c127cf153ebcadd9b791e6abb9ea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582033"
---
# <a name="checkparms"></a><span data-ttu-id="512c1-103">CheckParms</span><span class="sxs-lookup"><span data-stu-id="512c1-103">CheckParms</span></span>

  
  
<span data-ttu-id="512c1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="512c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="512c1-105">调用的内部函数，以验证调试参数调用 MAPI 服务提供程序方法。</span><span class="sxs-lookup"><span data-stu-id="512c1-105">Calls an internal function to validate debugging parameters on service provider methods called by MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="512c1-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="512c1-106">Header file:</span></span>  <br/> |<span data-ttu-id="512c1-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="512c1-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="512c1-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="512c1-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="512c1-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="512c1-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="512c1-110">调用：</span><span class="sxs-lookup"><span data-stu-id="512c1-110">Called by:</span></span>  <br/> |<span data-ttu-id="512c1-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="512c1-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT CheckParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="512c1-112">参数</span><span class="sxs-lookup"><span data-stu-id="512c1-112">Parameters</span></span>

 <span data-ttu-id="512c1-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="512c1-113">_eMethod_</span></span>
  
> <span data-ttu-id="512c1-114">[in]通过枚举，指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="512c1-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="512c1-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="512c1-115">_First_</span></span>
  
> <span data-ttu-id="512c1-116">[in]堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="512c1-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="512c1-117">返回值</span><span class="sxs-lookup"><span data-stu-id="512c1-117">Return value</span></span>

<span data-ttu-id="512c1-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="512c1-118">S_OK</span></span> 
  
> <span data-ttu-id="512c1-119">调用成功。</span><span class="sxs-lookup"><span data-stu-id="512c1-119">The call succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="512c1-120">注解</span><span class="sxs-lookup"><span data-stu-id="512c1-120">Remarks</span></span>

<span data-ttu-id="512c1-121">与[ValidateParms](validateparms.md)和[UlValidateParms](ulvalidateparms.md)宏**CheckParms**宏不执行完整参数验证。</span><span class="sxs-lookup"><span data-stu-id="512c1-121">In contrast to the [ValidateParms](validateparms.md) and [UlValidateParms](ulvalidateparms.md) macros, the **CheckParms** macro does not perform a full parameter validation.</span></span> <span data-ttu-id="512c1-122">MAPI 和服务之间传递参数提供程序假定已正确，因此**CheckParms**执行调试验证。</span><span class="sxs-lookup"><span data-stu-id="512c1-122">Parameters passed between MAPI and service providers are assumed to be correct, so **CheckParms** performs a debug validation only.</span></span> 
  

