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
ms.openlocfilehash: 8f71b30bd02af8f768da86218456feadda8ea1b6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414800"
---
# <a name="fequalnames"></a><span data-ttu-id="23ac0-103">FEqualNames</span><span class="sxs-lookup"><span data-stu-id="23ac0-103">FEqualNames</span></span>

  
  
<span data-ttu-id="23ac0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="23ac0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="23ac0-105">确定两个 MAPI 命名属性是否相同。</span><span class="sxs-lookup"><span data-stu-id="23ac0-105">Determines whether two MAPI named properties are the same.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23ac0-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="23ac0-106">Header file:</span></span>  <br/> |<span data-ttu-id="23ac0-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="23ac0-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="23ac0-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="23ac0-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="23ac0-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="23ac0-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="23ac0-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="23ac0-110">Called by:</span></span>  <br/> |<span data-ttu-id="23ac0-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="23ac0-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FEqualNames(
  LPMAPINAMEID lpName1,
  LPMAPINAMEID lpName2
);
```

## <a name="parameters"></a><span data-ttu-id="23ac0-112">参数</span><span class="sxs-lookup"><span data-stu-id="23ac0-112">Parameters</span></span>

 <span data-ttu-id="23ac0-113">_lpName1_</span><span class="sxs-lookup"><span data-stu-id="23ac0-113">_lpName1_</span></span>
  
> <span data-ttu-id="23ac0-114">[in]指向描述第一个命名属性的 [MAPINAMEID](mapinameid.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="23ac0-114">[in] Pointer to a [MAPINAMEID](mapinameid.md) structure describing the first named property.</span></span> 
    
 <span data-ttu-id="23ac0-115">_lpName2_</span><span class="sxs-lookup"><span data-stu-id="23ac0-115">_lpName2_</span></span>
  
> <span data-ttu-id="23ac0-116">[in]指向描述第二个命名属性的 **MAPINAMEID** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="23ac0-116">[in] Pointer to a **MAPINAMEID** structure describing the second named property.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="23ac0-117">返回值</span><span class="sxs-lookup"><span data-stu-id="23ac0-117">Return value</span></span>

<span data-ttu-id="23ac0-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="23ac0-118">TRUE</span></span> 
  
> <span data-ttu-id="23ac0-119">两个属性名称相等。</span><span class="sxs-lookup"><span data-stu-id="23ac0-119">The two property names are equal.</span></span> 
    
<span data-ttu-id="23ac0-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="23ac0-120">FALSE</span></span> 
  
> <span data-ttu-id="23ac0-121">这两个属性名称不相等。</span><span class="sxs-lookup"><span data-stu-id="23ac0-121">The two property names are not equal.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="23ac0-122">备注</span><span class="sxs-lookup"><span data-stu-id="23ac0-122">Remarks</span></span>

<span data-ttu-id="23ac0-123">**FEqualNames** 函数很有用，因为 **MAPINAMEID** 结构包含 [GUID，](guid.md)并且可以通过多个方式表示属性名称本身。</span><span class="sxs-lookup"><span data-stu-id="23ac0-123">The **FEqualNames** function is useful because the **MAPINAMEID** structure contains a [GUID](guid.md) and can represent the property name itself in more than one way.</span></span> <span data-ttu-id="23ac0-124">这意味着无法通过简单的二进制方法比较这两种结构。</span><span class="sxs-lookup"><span data-stu-id="23ac0-124">This means the two structures cannot be compared by simple binary methods.</span></span> 
  
<span data-ttu-id="23ac0-125">对于属性名称字符串，测试过程区分大小写。</span><span class="sxs-lookup"><span data-stu-id="23ac0-125">The testing process is case-sensitive for the property name strings.</span></span> 
  

