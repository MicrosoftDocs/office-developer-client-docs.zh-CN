---
title: CheckParameters
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.CheckParameters
api_type:
- COM
ms.assetid: ba33866a-c9c4-454a-9549-72455c61ee97
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a693c06d933c7e93d384aac8da8d5311eaf1d9da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774684"
---
# <a name="checkparameters"></a><span data-ttu-id="91219-103">CheckParameters</span><span class="sxs-lookup"><span data-stu-id="91219-103">CheckParameters</span></span>

  
  
<span data-ttu-id="91219-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="91219-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="91219-105">调用的内部函数，以验证调试参数调用 MAPI 服务提供程序方法。</span><span class="sxs-lookup"><span data-stu-id="91219-105">Calls an internal function to validate debugging parameters on service provider methods called by MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="91219-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="91219-106">Header file:</span></span>  <br/> |<span data-ttu-id="91219-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="91219-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="91219-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="91219-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="91219-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="91219-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="91219-110">调用：</span><span class="sxs-lookup"><span data-stu-id="91219-110">Called by:</span></span>  <br/> |<span data-ttu-id="91219-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="91219-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT CheckParameters(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="91219-112">参数</span><span class="sxs-lookup"><span data-stu-id="91219-112">Parameters</span></span>

 <span data-ttu-id="91219-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="91219-113">_eMethod_</span></span>
  
> <span data-ttu-id="91219-114">[in]通过枚举，指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="91219-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="91219-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="91219-115">_First_</span></span>
  
> <span data-ttu-id="91219-116">[in]堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="91219-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="91219-117">返回值</span><span class="sxs-lookup"><span data-stu-id="91219-117">Return value</span></span>

<span data-ttu-id="91219-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="91219-118">S_OK</span></span> 
  
> <span data-ttu-id="91219-119">调用成功。</span><span class="sxs-lookup"><span data-stu-id="91219-119">The call succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="91219-120">说明</span><span class="sxs-lookup"><span data-stu-id="91219-120">Remarks</span></span>

<span data-ttu-id="91219-121">已由[CheckParms](checkparms.md)宏取代**CheckParameters**宏。</span><span class="sxs-lookup"><span data-stu-id="91219-121">The **CheckParameters** macro has been superseded by the [CheckParms](checkparms.md) macro.</span></span> <span data-ttu-id="91219-122">**CheckParms**建议所有平台上。</span><span class="sxs-lookup"><span data-stu-id="91219-122">**CheckParms** is recommended on all platforms.</span></span> 
  

