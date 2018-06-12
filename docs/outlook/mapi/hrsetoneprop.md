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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 8af0d5c6eaff0c1e01e01c24c46f299e0c637f68
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775189"
---
# <a name="hrsetoneprop"></a><span data-ttu-id="2155e-103">HrSetOneProp</span><span class="sxs-lookup"><span data-stu-id="2155e-103">HrSetOneProp</span></span>

  
  
<span data-ttu-id="2155e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2155e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2155e-105">设置或更改单个属性接口，即接口派生自[IMAPIProp](imapipropiunknown.md)上属性的值。</span><span class="sxs-lookup"><span data-stu-id="2155e-105">Sets or changes the value of a single property on a property interface, that is, an interface derived from [IMAPIProp](imapipropiunknown.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2155e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2155e-106">Header file:</span></span>  <br/> |<span data-ttu-id="2155e-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="2155e-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="2155e-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2155e-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2155e-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2155e-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2155e-110">调用：</span><span class="sxs-lookup"><span data-stu-id="2155e-110">Called by:</span></span>  <br/> |<span data-ttu-id="2155e-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="2155e-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HrSetOneProp(
  LPMAPIPROP pmp,
  LPSPropValue pprop
);
```

## <a name="parameters"></a><span data-ttu-id="2155e-112">参数</span><span class="sxs-lookup"><span data-stu-id="2155e-112">Parameters</span></span>

 <span data-ttu-id="2155e-113">_pmp_</span><span class="sxs-lookup"><span data-stu-id="2155e-113">_pmp_</span></span>
  
> <span data-ttu-id="2155e-114">[in]该属性值为要设置或更改的[IMAPIProp](imapipropiunknown.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2155e-114">[in] Pointer to an [IMAPIProp](imapipropiunknown.md) interface on which the property value is to be set or changed.</span></span> 
    
 <span data-ttu-id="2155e-115">_pprop_</span><span class="sxs-lookup"><span data-stu-id="2155e-115">_pprop_</span></span>
  
> <span data-ttu-id="2155e-116">[in]定义要对_pmp_属性设置的值的[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="2155e-116">[in] Pointer to the [SPropValue](spropvalue.md) structure defining the value to be set on the  _pmp_ property.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2155e-117">返回值</span><span class="sxs-lookup"><span data-stu-id="2155e-117">Return value</span></span>

<span data-ttu-id="2155e-118">无。</span><span class="sxs-lookup"><span data-stu-id="2155e-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2155e-119">备注</span><span class="sxs-lookup"><span data-stu-id="2155e-119">Remarks</span></span>

<span data-ttu-id="2155e-120">不同的[IMAPIProp::SetProps](imapiprop-setprops.md)方法， **HrSetOneProp**函数永远不会返回任何警告。</span><span class="sxs-lookup"><span data-stu-id="2155e-120">Unlike the [IMAPIProp::SetProps](imapiprop-setprops.md) method, the **HrSetOneProp** function never returns any warnings.</span></span> <span data-ttu-id="2155e-121">设置只有一个属性，因为它只是成功或失败。</span><span class="sxs-lookup"><span data-stu-id="2155e-121">Because it sets only one property, it simply either succeeds or fails.</span></span> <span data-ttu-id="2155e-122">设置或更改多个属性， **SetProps**是更快。</span><span class="sxs-lookup"><span data-stu-id="2155e-122">For setting or changing multiple properties, **SetProps** is faster.</span></span> 
  
<span data-ttu-id="2155e-123">您可以检索[HrGetOneProp](hrgetoneprop.md)函数的单个属性。</span><span class="sxs-lookup"><span data-stu-id="2155e-123">You can retrieve a single property with the [HrGetOneProp](hrgetoneprop.md) function.</span></span> 
  

