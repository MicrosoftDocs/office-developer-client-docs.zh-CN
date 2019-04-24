---
title: HrSetOneProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrSetOneProp
api_type:
- COM
ms.assetid: 14ae3242-fddf-4199-a9a7-4ab153b31064
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 37e6560d859ce4731b7a06e571eb38eb160c3686
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347766"
---
# <a name="hrsetoneprop"></a><span data-ttu-id="2b6bf-103">HrSetOneProp</span><span class="sxs-lookup"><span data-stu-id="2b6bf-103">HrSetOneProp</span></span>

  
  
<span data-ttu-id="2b6bf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2b6bf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2b6bf-105">设置或更改属性接口上单个属性的值, 即从[IMAPIProp](imapipropiunknown.md)派生的接口。</span><span class="sxs-lookup"><span data-stu-id="2b6bf-105">Sets or changes the value of a single property on a property interface, that is, an interface derived from [IMAPIProp](imapipropiunknown.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2b6bf-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2b6bf-106">Header file:</span></span>  <br/> |<span data-ttu-id="2b6bf-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="2b6bf-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="2b6bf-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="2b6bf-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2b6bf-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2b6bf-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2b6bf-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="2b6bf-110">Called by:</span></span>  <br/> |<span data-ttu-id="2b6bf-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="2b6bf-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HrSetOneProp(
  LPMAPIPROP pmp,
  LPSPropValue pprop
);
```

## <a name="parameters"></a><span data-ttu-id="2b6bf-112">参数</span><span class="sxs-lookup"><span data-stu-id="2b6bf-112">Parameters</span></span>

 <span data-ttu-id="2b6bf-113">_pmp_</span><span class="sxs-lookup"><span data-stu-id="2b6bf-113">_pmp_</span></span>
  
> <span data-ttu-id="2b6bf-114">实时指向要在其上设置或更改属性值的[IMAPIProp](imapipropiunknown.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2b6bf-114">[in] Pointer to an [IMAPIProp](imapipropiunknown.md) interface on which the property value is to be set or changed.</span></span> 
    
 <span data-ttu-id="2b6bf-115">_pprop_</span><span class="sxs-lookup"><span data-stu-id="2b6bf-115">_pprop_</span></span>
  
> <span data-ttu-id="2b6bf-116">实时指向[SPropValue](spropvalue.md)结构的指针, 该结构定义要在_pmp_属性上设置的值。</span><span class="sxs-lookup"><span data-stu-id="2b6bf-116">[in] Pointer to the [SPropValue](spropvalue.md) structure defining the value to be set on the  _pmp_ property.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2b6bf-117">返回值</span><span class="sxs-lookup"><span data-stu-id="2b6bf-117">Return value</span></span>

<span data-ttu-id="2b6bf-118">无。</span><span class="sxs-lookup"><span data-stu-id="2b6bf-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2b6bf-119">注解</span><span class="sxs-lookup"><span data-stu-id="2b6bf-119">Remarks</span></span>

<span data-ttu-id="2b6bf-120">与[IMAPIProp:: SetProps](imapiprop-setprops.md)方法不同, **HrSetOneProp**函数永远不会返回任何警告。</span><span class="sxs-lookup"><span data-stu-id="2b6bf-120">Unlike the [IMAPIProp::SetProps](imapiprop-setprops.md) method, the **HrSetOneProp** function never returns any warnings.</span></span> <span data-ttu-id="2b6bf-121">由于它仅设置一个属性, 它只是 "成功" 或 "失败"。</span><span class="sxs-lookup"><span data-stu-id="2b6bf-121">Because it sets only one property, it simply either succeeds or fails.</span></span> <span data-ttu-id="2b6bf-122">若要设置或更改多个属性, **SetProps**速度更快。</span><span class="sxs-lookup"><span data-stu-id="2b6bf-122">For setting or changing multiple properties, **SetProps** is faster.</span></span> 
  
<span data-ttu-id="2b6bf-123">您可以使用[HrGetOneProp](hrgetoneprop.md)函数检索单个属性。</span><span class="sxs-lookup"><span data-stu-id="2b6bf-123">You can retrieve a single property with the [HrGetOneProp](hrgetoneprop.md) function.</span></span> 
  

