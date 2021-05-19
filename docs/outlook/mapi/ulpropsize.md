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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416900"
---
# <a name="ulpropsize"></a><span data-ttu-id="17892-103">UlPropSize</span><span class="sxs-lookup"><span data-stu-id="17892-103">UlPropSize</span></span>

  
  
<span data-ttu-id="17892-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="17892-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="17892-105">返回单个属性值的大小。</span><span class="sxs-lookup"><span data-stu-id="17892-105">Returns the size of a single property value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="17892-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="17892-106">Header file:</span></span>  <br/> |<span data-ttu-id="17892-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="17892-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="17892-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="17892-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="17892-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="17892-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="17892-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="17892-110">Called by:</span></span>  <br/> |<span data-ttu-id="17892-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="17892-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG UlPropSize(
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a><span data-ttu-id="17892-112">参数</span><span class="sxs-lookup"><span data-stu-id="17892-112">Parameters</span></span>

 <span data-ttu-id="17892-113">_lpSPropValue_</span><span class="sxs-lookup"><span data-stu-id="17892-113">_lpSPropValue_</span></span>
  
> <span data-ttu-id="17892-114">[in]指向 [定义要测量的属性的 SPropValue](spropvalue.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="17892-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining the property to be measured.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="17892-115">返回值</span><span class="sxs-lookup"><span data-stu-id="17892-115">Return value</span></span>

<span data-ttu-id="17892-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="17892-116">S_OK</span></span> 
  
> <span data-ttu-id="17892-117">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="17892-117">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="17892-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="17892-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="17892-119">意外或未知来源的错误阻止了操作完成。</span><span class="sxs-lookup"><span data-stu-id="17892-119">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="17892-120">备注</span><span class="sxs-lookup"><span data-stu-id="17892-120">Remarks</span></span>

<span data-ttu-id="17892-121">**UlPropSize** 函数返回指定属性的属性值的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="17892-121">The **UlPropSize** function returns the size, in bytes, of the property value for the specified property.</span></span> <span data-ttu-id="17892-122">它会忽略 **SPropValue** 结构的剩余部分的大小。</span><span class="sxs-lookup"><span data-stu-id="17892-122">It disregards the size of the remainder of the **SPropValue** structure.</span></span> 
  

