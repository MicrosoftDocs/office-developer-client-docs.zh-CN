---
title: GetInstance
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.GetInstance
api_type:
- COM
ms.assetid: cb432d52-6c96-45d2-bbde-45b0de3f915c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 936a20c4236ab76e5acdb178737c3044d3f53bfe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299543"
---
# <a name="getinstance"></a><span data-ttu-id="05a52-103">GetInstance</span><span class="sxs-lookup"><span data-stu-id="05a52-103">GetInstance</span></span>

  
  
<span data-ttu-id="05a52-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="05a52-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="05a52-105">将多值属性中的一个值复制到同一类型的单值属性。</span><span class="sxs-lookup"><span data-stu-id="05a52-105">Copies one value within a multivalued property to a single-valued property of the same type.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="05a52-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="05a52-106">Header file:</span></span>  <br/> |<span data-ttu-id="05a52-107">MAPIUTIL。水平</span><span class="sxs-lookup"><span data-stu-id="05a52-107">MAPIUTIL.H</span></span>  <br/> |
|<span data-ttu-id="05a52-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="05a52-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="05a52-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="05a52-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="05a52-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="05a52-110">Called by:</span></span>  <br/> |<span data-ttu-id="05a52-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="05a52-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID GetInstance(
  LPSPropValue pvalMv,
  LPSPropValue pvalSv,
  ULONG uliInst
);
```

## <a name="parameters"></a><span data-ttu-id="05a52-112">参数</span><span class="sxs-lookup"><span data-stu-id="05a52-112">Parameters</span></span>

 <span data-ttu-id="05a52-113">_pvalMv_</span><span class="sxs-lookup"><span data-stu-id="05a52-113">_pvalMv_</span></span>
  
> <span data-ttu-id="05a52-114">实时指向定义多值属性的[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="05a52-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining a multivalued property.</span></span> 
    
 <span data-ttu-id="05a52-115">_pvalSv_</span><span class="sxs-lookup"><span data-stu-id="05a52-115">_pvalSv_</span></span>
  
> <span data-ttu-id="05a52-116">实时指向用于接收数据的单值属性的指针。</span><span class="sxs-lookup"><span data-stu-id="05a52-116">[in] Pointer to a single-valued property to receive data.</span></span> 
    
 <span data-ttu-id="05a52-117">_uliInst_</span><span class="sxs-lookup"><span data-stu-id="05a52-117">_uliInst_</span></span>
  
> <span data-ttu-id="05a52-118">实时从_pvalMv_参数指示的结构中复制的值的实例号, 即数组元素。</span><span class="sxs-lookup"><span data-stu-id="05a52-118">[in] The instance number, that is, the array element, of the value being copied from the structure indicated by the  _pvalMv_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="05a52-119">返回值</span><span class="sxs-lookup"><span data-stu-id="05a52-119">Return value</span></span>

<span data-ttu-id="05a52-120">无。</span><span class="sxs-lookup"><span data-stu-id="05a52-120">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="05a52-121">注解</span><span class="sxs-lookup"><span data-stu-id="05a52-121">Remarks</span></span>

<span data-ttu-id="05a52-122">如果复制的值对于分配的内存来说太大, 则**GetInstance**函数仅复制指针, 而不是分配新内存。</span><span class="sxs-lookup"><span data-stu-id="05a52-122">If the value copied is too large for the allocated memory, the **GetInstance** function only copies pointers instead of allocating new memory.</span></span> 
  

