---
title: UlPropSize
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlPropSize
api_type:
- COM
ms.assetid: 240f1144-0805-4cd1-9e7d-f2a550a2f160
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bc00270b167c9f7317fa466d790d5020d961676f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779020"
---
# <a name="ulpropsize"></a><span data-ttu-id="96743-103">UlPropSize</span><span class="sxs-lookup"><span data-stu-id="96743-103">UlPropSize</span></span>

  
  
<span data-ttu-id="96743-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="96743-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="96743-105">返回的单个属性值的大小。</span><span class="sxs-lookup"><span data-stu-id="96743-105">Returns the size of a single property value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="96743-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="96743-106">Header file:</span></span>  <br/> |<span data-ttu-id="96743-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="96743-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="96743-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="96743-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="96743-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="96743-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="96743-110">调用：</span><span class="sxs-lookup"><span data-stu-id="96743-110">Called by:</span></span>  <br/> |<span data-ttu-id="96743-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="96743-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG UlPropSize(
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a><span data-ttu-id="96743-112">参数</span><span class="sxs-lookup"><span data-stu-id="96743-112">Parameters</span></span>

 <span data-ttu-id="96743-113">_lpSPropValue_</span><span class="sxs-lookup"><span data-stu-id="96743-113">_lpSPropValue_</span></span>
  
> <span data-ttu-id="96743-114">[in]指向[SPropValue](spropvalue.md)结构定义要测量的属性。</span><span class="sxs-lookup"><span data-stu-id="96743-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining the property to be measured.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="96743-115">返回值</span><span class="sxs-lookup"><span data-stu-id="96743-115">Return value</span></span>

<span data-ttu-id="96743-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="96743-116">S_OK</span></span> 
  
> <span data-ttu-id="96743-117">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="96743-117">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="96743-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="96743-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="96743-119">意外或未知的原点出现错误，无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="96743-119">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="96743-120">说明</span><span class="sxs-lookup"><span data-stu-id="96743-120">Remarks</span></span>

<span data-ttu-id="96743-121">**UlPropSize**函数返回的大小，以字节为单位指定的属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="96743-121">The **UlPropSize** function returns the size, in bytes, of the property value for the specified property.</span></span> <span data-ttu-id="96743-122">它将忽略**SPropValue**结构的其余部分的大小。</span><span class="sxs-lookup"><span data-stu-id="96743-122">It disregards the size of the remainder of the **SPropValue** structure.</span></span> 
  

