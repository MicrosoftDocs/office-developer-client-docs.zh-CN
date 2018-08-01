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
ms.openlocfilehash: f65f047a73a2c06ca02251c554e5dca42352b6c6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775042"
---
# <a name="getinstance"></a><span data-ttu-id="89a42-103">GetInstance</span><span class="sxs-lookup"><span data-stu-id="89a42-103">GetInstance</span></span>

  
  
<span data-ttu-id="89a42-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="89a42-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="89a42-105">将一个多值属性中的值复制到同一类型的单值属性。</span><span class="sxs-lookup"><span data-stu-id="89a42-105">Copies one value within a multivalued property to a single-valued property of the same type.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="89a42-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="89a42-106">Header file:</span></span>  <br/> |<span data-ttu-id="89a42-107">MAPIUTIL。H</span><span class="sxs-lookup"><span data-stu-id="89a42-107">MAPIUTIL.H</span></span>  <br/> |
|<span data-ttu-id="89a42-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="89a42-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="89a42-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="89a42-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="89a42-110">调用：</span><span class="sxs-lookup"><span data-stu-id="89a42-110">Called by:</span></span>  <br/> |<span data-ttu-id="89a42-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="89a42-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID GetInstance(
  LPSPropValue pvalMv,
  LPSPropValue pvalSv,
  ULONG uliInst
);
```

## <a name="parameters"></a><span data-ttu-id="89a42-112">参数</span><span class="sxs-lookup"><span data-stu-id="89a42-112">Parameters</span></span>

 <span data-ttu-id="89a42-113">_pvalMv_</span><span class="sxs-lookup"><span data-stu-id="89a42-113">_pvalMv_</span></span>
  
> <span data-ttu-id="89a42-114">[in]定义一个多值的属性[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="89a42-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining a multivalued property.</span></span> 
    
 <span data-ttu-id="89a42-115">_pvalSv_</span><span class="sxs-lookup"><span data-stu-id="89a42-115">_pvalSv_</span></span>
  
> <span data-ttu-id="89a42-116">[in]指向要接收数据的单值属性。</span><span class="sxs-lookup"><span data-stu-id="89a42-116">[in] Pointer to a single-valued property to receive data.</span></span> 
    
 <span data-ttu-id="89a42-117">_uliInst_</span><span class="sxs-lookup"><span data-stu-id="89a42-117">_uliInst_</span></span>
  
> <span data-ttu-id="89a42-118">[in]实例数量，即，从结构由_pvalMv_参数指示复制值的数组元素。</span><span class="sxs-lookup"><span data-stu-id="89a42-118">[in] The instance number, that is, the array element, of the value being copied from the structure indicated by the  _pvalMv_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="89a42-119">返回值</span><span class="sxs-lookup"><span data-stu-id="89a42-119">Return value</span></span>

<span data-ttu-id="89a42-120">无。</span><span class="sxs-lookup"><span data-stu-id="89a42-120">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="89a42-121">说明</span><span class="sxs-lookup"><span data-stu-id="89a42-121">Remarks</span></span>

<span data-ttu-id="89a42-122">如果复制的值为太大，分配的内存， **GetInstance**函数仅复制指针而不是分配新内存。</span><span class="sxs-lookup"><span data-stu-id="89a42-122">If the value copied is too large for the allocated memory, the **GetInstance** function only copies pointers instead of allocating new memory.</span></span> 
  

