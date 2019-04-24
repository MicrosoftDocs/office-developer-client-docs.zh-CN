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
ms.openlocfilehash: cc1547ad7d881b707825630f96987d4c40ad4863
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315300"
---
# <a name="ulpropsize"></a><span data-ttu-id="ba0f3-103">UlPropSize</span><span class="sxs-lookup"><span data-stu-id="ba0f3-103">UlPropSize</span></span>

  
  
<span data-ttu-id="ba0f3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ba0f3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ba0f3-105">返回单个属性值的大小。</span><span class="sxs-lookup"><span data-stu-id="ba0f3-105">Returns the size of a single property value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ba0f3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ba0f3-106">Header file:</span></span>  <br/> |<span data-ttu-id="ba0f3-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ba0f3-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="ba0f3-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="ba0f3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ba0f3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ba0f3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ba0f3-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="ba0f3-110">Called by:</span></span>  <br/> |<span data-ttu-id="ba0f3-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="ba0f3-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG UlPropSize(
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a><span data-ttu-id="ba0f3-112">参数</span><span class="sxs-lookup"><span data-stu-id="ba0f3-112">Parameters</span></span>

 <span data-ttu-id="ba0f3-113">_lpSPropValue_</span><span class="sxs-lookup"><span data-stu-id="ba0f3-113">_lpSPropValue_</span></span>
  
> <span data-ttu-id="ba0f3-114">实时指向定义要度量的属性的[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="ba0f3-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining the property to be measured.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ba0f3-115">返回值</span><span class="sxs-lookup"><span data-stu-id="ba0f3-115">Return value</span></span>

<span data-ttu-id="ba0f3-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba0f3-116">S_OK</span></span> 
  
> <span data-ttu-id="ba0f3-117">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="ba0f3-117">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="ba0f3-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="ba0f3-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="ba0f3-119">意外或未知来源的错误阻止操作完成。</span><span class="sxs-lookup"><span data-stu-id="ba0f3-119">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ba0f3-120">注解</span><span class="sxs-lookup"><span data-stu-id="ba0f3-120">Remarks</span></span>

<span data-ttu-id="ba0f3-121">**UlPropSize**函数返回指定属性的属性值的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="ba0f3-121">The **UlPropSize** function returns the size, in bytes, of the property value for the specified property.</span></span> <span data-ttu-id="ba0f3-122">它不会忽略**SPropValue**结构的其余部分的大小。</span><span class="sxs-lookup"><span data-stu-id="ba0f3-122">It disregards the size of the remainder of the **SPropValue** structure.</span></span> 
  

