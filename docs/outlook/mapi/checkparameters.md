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
ms.openlocfilehash: a922b8bb21bfd534935d4d1706a6ccfd15c2da5c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433393"
---
# <a name="checkparameters"></a><span data-ttu-id="8f8da-103">CheckParameters</span><span class="sxs-lookup"><span data-stu-id="8f8da-103">CheckParameters</span></span>

  
  
<span data-ttu-id="8f8da-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8f8da-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8f8da-105">调用内部函数来验证 MAPI 调用的服务提供程序方法的调试参数。</span><span class="sxs-lookup"><span data-stu-id="8f8da-105">Calls an internal function to validate debugging parameters on service provider methods called by MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8f8da-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="8f8da-106">Header file:</span></span>  <br/> |<span data-ttu-id="8f8da-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="8f8da-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="8f8da-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="8f8da-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="8f8da-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="8f8da-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="8f8da-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="8f8da-110">Called by:</span></span>  <br/> |<span data-ttu-id="8f8da-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="8f8da-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT CheckParameters(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="8f8da-112">参数</span><span class="sxs-lookup"><span data-stu-id="8f8da-112">Parameters</span></span>

 <span data-ttu-id="8f8da-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="8f8da-113">_eMethod_</span></span>
  
> <span data-ttu-id="8f8da-114">实时通过枚举指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="8f8da-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="8f8da-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="8f8da-115">_First_</span></span>
  
> <span data-ttu-id="8f8da-116">实时指向堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="8f8da-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8f8da-117">返回值</span><span class="sxs-lookup"><span data-stu-id="8f8da-117">Return value</span></span>

<span data-ttu-id="8f8da-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f8da-118">S_OK</span></span> 
  
> <span data-ttu-id="8f8da-119">调用成功。</span><span class="sxs-lookup"><span data-stu-id="8f8da-119">The call succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8f8da-120">说明</span><span class="sxs-lookup"><span data-stu-id="8f8da-120">Remarks</span></span>

<span data-ttu-id="8f8da-121">**CheckParameters**宏已被[CheckParms](checkparms.md)宏取代。</span><span class="sxs-lookup"><span data-stu-id="8f8da-121">The **CheckParameters** macro has been superseded by the [CheckParms](checkparms.md) macro.</span></span> <span data-ttu-id="8f8da-122">建议在所有平台上使用**CheckParms** 。</span><span class="sxs-lookup"><span data-stu-id="8f8da-122">**CheckParms** is recommended on all platforms.</span></span> 
  

