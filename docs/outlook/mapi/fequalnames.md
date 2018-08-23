---
title: FEqualNames
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FEqualNames
api_type:
- COM
ms.assetid: 4dd58b0b-dc39-4782-a9ec-05e353c90927
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 09c6540f2a224b7dc89a62c34cfb0c867cef4632
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570847"
---
# <a name="fequalnames"></a><span data-ttu-id="0670d-103">FEqualNames</span><span class="sxs-lookup"><span data-stu-id="0670d-103">FEqualNames</span></span>

  
  
<span data-ttu-id="0670d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0670d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0670d-105">确定两个 MAPI 命名属性是否相同。</span><span class="sxs-lookup"><span data-stu-id="0670d-105">Determines whether two MAPI named properties are the same.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0670d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="0670d-106">Header file:</span></span>  <br/> |<span data-ttu-id="0670d-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="0670d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="0670d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="0670d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="0670d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="0670d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="0670d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="0670d-110">Called by:</span></span>  <br/> |<span data-ttu-id="0670d-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="0670d-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FEqualNames(
  LPMAPINAMEID lpName1,
  LPMAPINAMEID lpName2
);
```

## <a name="parameters"></a><span data-ttu-id="0670d-112">参数</span><span class="sxs-lookup"><span data-stu-id="0670d-112">Parameters</span></span>

 <span data-ttu-id="0670d-113">_lpName1_</span><span class="sxs-lookup"><span data-stu-id="0670d-113">_lpName1_</span></span>
  
> <span data-ttu-id="0670d-114">[in]指向[MAPINAMEID](mapinameid.md)结构描述的第一个命名的属性。</span><span class="sxs-lookup"><span data-stu-id="0670d-114">[in] Pointer to a [MAPINAMEID](mapinameid.md) structure describing the first named property.</span></span> 
    
 <span data-ttu-id="0670d-115">_lpName2_</span><span class="sxs-lookup"><span data-stu-id="0670d-115">_lpName2_</span></span>
  
> <span data-ttu-id="0670d-116">[in]指向**MAPINAMEID**结构描述第二个命名的属性。</span><span class="sxs-lookup"><span data-stu-id="0670d-116">[in] Pointer to a **MAPINAMEID** structure describing the second named property.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0670d-117">返回值</span><span class="sxs-lookup"><span data-stu-id="0670d-117">Return value</span></span>

<span data-ttu-id="0670d-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="0670d-118">TRUE</span></span> 
  
> <span data-ttu-id="0670d-119">两个属性名称相等。</span><span class="sxs-lookup"><span data-stu-id="0670d-119">The two property names are equal.</span></span> 
    
<span data-ttu-id="0670d-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="0670d-120">FALSE</span></span> 
  
> <span data-ttu-id="0670d-121">两个属性名称不相等。</span><span class="sxs-lookup"><span data-stu-id="0670d-121">The two property names are not equal.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0670d-122">注解</span><span class="sxs-lookup"><span data-stu-id="0670d-122">Remarks</span></span>

<span data-ttu-id="0670d-123">**FEqualNames**函数很有用，因为**MAPINAMEID**结构包含[GUID](guid.md) ，并可以表示多种方式中的属性名称本身。</span><span class="sxs-lookup"><span data-stu-id="0670d-123">The **FEqualNames** function is useful because the **MAPINAMEID** structure contains a [GUID](guid.md) and can represent the property name itself in more than one way.</span></span> <span data-ttu-id="0670d-124">这意味着不能由简单二进制方法比较两个结构。</span><span class="sxs-lookup"><span data-stu-id="0670d-124">This means the two structures cannot be compared by simple binary methods.</span></span> 
  
<span data-ttu-id="0670d-125">区分大小写的属性名称字符串的测试过程。</span><span class="sxs-lookup"><span data-stu-id="0670d-125">The testing process is case-sensitive for the property name strings.</span></span> 
  

