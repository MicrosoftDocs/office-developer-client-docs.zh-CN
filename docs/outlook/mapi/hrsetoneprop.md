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
ms.openlocfilehash: 31d2be027ef3b58fdd44e71c922677164d352feb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569125"
---
# <a name="hrsetoneprop"></a><span data-ttu-id="02a78-103">HrSetOneProp</span><span class="sxs-lookup"><span data-stu-id="02a78-103">HrSetOneProp</span></span>

  
  
<span data-ttu-id="02a78-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="02a78-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="02a78-105">设置或更改单个属性接口，即接口派生自[IMAPIProp](imapipropiunknown.md)上属性的值。</span><span class="sxs-lookup"><span data-stu-id="02a78-105">Sets or changes the value of a single property on a property interface, that is, an interface derived from [IMAPIProp](imapipropiunknown.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="02a78-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="02a78-106">Header file:</span></span>  <br/> |<span data-ttu-id="02a78-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="02a78-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="02a78-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="02a78-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="02a78-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="02a78-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="02a78-110">调用：</span><span class="sxs-lookup"><span data-stu-id="02a78-110">Called by:</span></span>  <br/> |<span data-ttu-id="02a78-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="02a78-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HrSetOneProp(
  LPMAPIPROP pmp,
  LPSPropValue pprop
);
```

## <a name="parameters"></a><span data-ttu-id="02a78-112">参数</span><span class="sxs-lookup"><span data-stu-id="02a78-112">Parameters</span></span>

 <span data-ttu-id="02a78-113">_pmp_</span><span class="sxs-lookup"><span data-stu-id="02a78-113">_pmp_</span></span>
  
> <span data-ttu-id="02a78-114">[in]该属性值为要设置或更改的[IMAPIProp](imapipropiunknown.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="02a78-114">[in] Pointer to an [IMAPIProp](imapipropiunknown.md) interface on which the property value is to be set or changed.</span></span> 
    
 <span data-ttu-id="02a78-115">_pprop_</span><span class="sxs-lookup"><span data-stu-id="02a78-115">_pprop_</span></span>
  
> <span data-ttu-id="02a78-116">[in]定义要对_pmp_属性设置的值的[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="02a78-116">[in] Pointer to the [SPropValue](spropvalue.md) structure defining the value to be set on the  _pmp_ property.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="02a78-117">返回值</span><span class="sxs-lookup"><span data-stu-id="02a78-117">Return value</span></span>

<span data-ttu-id="02a78-118">无。</span><span class="sxs-lookup"><span data-stu-id="02a78-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="02a78-119">注解</span><span class="sxs-lookup"><span data-stu-id="02a78-119">Remarks</span></span>

<span data-ttu-id="02a78-120">不同的[IMAPIProp::SetProps](imapiprop-setprops.md)方法， **HrSetOneProp**函数永远不会返回任何警告。</span><span class="sxs-lookup"><span data-stu-id="02a78-120">Unlike the [IMAPIProp::SetProps](imapiprop-setprops.md) method, the **HrSetOneProp** function never returns any warnings.</span></span> <span data-ttu-id="02a78-121">设置只有一个属性，因为它只是成功或失败。</span><span class="sxs-lookup"><span data-stu-id="02a78-121">Because it sets only one property, it simply either succeeds or fails.</span></span> <span data-ttu-id="02a78-122">设置或更改多个属性， **SetProps**是更快。</span><span class="sxs-lookup"><span data-stu-id="02a78-122">For setting or changing multiple properties, **SetProps** is faster.</span></span> 
  
<span data-ttu-id="02a78-123">您可以检索[HrGetOneProp](hrgetoneprop.md)函数的单个属性。</span><span class="sxs-lookup"><span data-stu-id="02a78-123">You can retrieve a single property with the [HrGetOneProp](hrgetoneprop.md) function.</span></span> 
  

