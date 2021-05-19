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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418720"
---
# <a name="getinstance"></a><span data-ttu-id="a5ad2-103">GetInstance</span><span class="sxs-lookup"><span data-stu-id="a5ad2-103">GetInstance</span></span>

  
  
<span data-ttu-id="a5ad2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a5ad2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a5ad2-105">将多值属性中的一个值复制到同一类型的单值属性。</span><span class="sxs-lookup"><span data-stu-id="a5ad2-105">Copies one value within a multivalued property to a single-valued property of the same type.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a5ad2-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a5ad2-106">Header file:</span></span>  <br/> |<span data-ttu-id="a5ad2-107">MAPIUTIL。H</span><span class="sxs-lookup"><span data-stu-id="a5ad2-107">MAPIUTIL.H</span></span>  <br/> |
|<span data-ttu-id="a5ad2-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="a5ad2-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a5ad2-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a5ad2-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a5ad2-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="a5ad2-110">Called by:</span></span>  <br/> |<span data-ttu-id="a5ad2-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="a5ad2-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID GetInstance(
  LPSPropValue pvalMv,
  LPSPropValue pvalSv,
  ULONG uliInst
);
```

## <a name="parameters"></a><span data-ttu-id="a5ad2-112">参数</span><span class="sxs-lookup"><span data-stu-id="a5ad2-112">Parameters</span></span>

 <span data-ttu-id="a5ad2-113">_pvalMv_</span><span class="sxs-lookup"><span data-stu-id="a5ad2-113">_pvalMv_</span></span>
  
> <span data-ttu-id="a5ad2-114">[in]指向定义多值属性的 [SPropValue](spropvalue.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a5ad2-114">[in] Pointer to an [SPropValue](spropvalue.md) structure defining a multivalued property.</span></span> 
    
 <span data-ttu-id="a5ad2-115">_pvalSv_</span><span class="sxs-lookup"><span data-stu-id="a5ad2-115">_pvalSv_</span></span>
  
> <span data-ttu-id="a5ad2-116">[in]指向用于接收数据的单值属性的指针。</span><span class="sxs-lookup"><span data-stu-id="a5ad2-116">[in] Pointer to a single-valued property to receive data.</span></span> 
    
 <span data-ttu-id="a5ad2-117">_uliInst_</span><span class="sxs-lookup"><span data-stu-id="a5ad2-117">_uliInst_</span></span>
  
> <span data-ttu-id="a5ad2-118">[in]从  _pvalMv_ 参数指示的结构复制的值的实例编号，即数组元素。</span><span class="sxs-lookup"><span data-stu-id="a5ad2-118">[in] The instance number, that is, the array element, of the value being copied from the structure indicated by the  _pvalMv_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a5ad2-119">返回值</span><span class="sxs-lookup"><span data-stu-id="a5ad2-119">Return value</span></span>

<span data-ttu-id="a5ad2-120">无。</span><span class="sxs-lookup"><span data-stu-id="a5ad2-120">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a5ad2-121">说明</span><span class="sxs-lookup"><span data-stu-id="a5ad2-121">Remarks</span></span>

<span data-ttu-id="a5ad2-122">如果复制的值对于分配的内存太大， **则 GetInstance** 函数仅复制指针，而不是分配新内存。</span><span class="sxs-lookup"><span data-stu-id="a5ad2-122">If the value copied is too large for the allocated memory, the **GetInstance** function only copies pointers instead of allocating new memory.</span></span> 
  

