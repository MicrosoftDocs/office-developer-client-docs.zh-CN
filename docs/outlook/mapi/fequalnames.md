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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334879"
---
# <a name="fequalnames"></a><span data-ttu-id="73f26-103">FEqualNames</span><span class="sxs-lookup"><span data-stu-id="73f26-103">FEqualNames</span></span>

  
  
<span data-ttu-id="73f26-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="73f26-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="73f26-105">确定两个 MAPI 命名属性是否相同。</span><span class="sxs-lookup"><span data-stu-id="73f26-105">Determines whether two MAPI named properties are the same.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="73f26-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="73f26-106">Header file:</span></span>  <br/> |<span data-ttu-id="73f26-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="73f26-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="73f26-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="73f26-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="73f26-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="73f26-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="73f26-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="73f26-110">Called by:</span></span>  <br/> |<span data-ttu-id="73f26-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="73f26-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FEqualNames(
  LPMAPINAMEID lpName1,
  LPMAPINAMEID lpName2
);
```

## <a name="parameters"></a><span data-ttu-id="73f26-112">参数</span><span class="sxs-lookup"><span data-stu-id="73f26-112">Parameters</span></span>

 <span data-ttu-id="73f26-113">_lpName1_</span><span class="sxs-lookup"><span data-stu-id="73f26-113">_lpName1_</span></span>
  
> <span data-ttu-id="73f26-114">实时指向描述第一个命名属性的[MAPINAMEID](mapinameid.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="73f26-114">[in] Pointer to a [MAPINAMEID](mapinameid.md) structure describing the first named property.</span></span> 
    
 <span data-ttu-id="73f26-115">_lpName2_</span><span class="sxs-lookup"><span data-stu-id="73f26-115">_lpName2_</span></span>
  
> <span data-ttu-id="73f26-116">实时指向描述第二个命名属性的**MAPINAMEID**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="73f26-116">[in] Pointer to a **MAPINAMEID** structure describing the second named property.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="73f26-117">返回值</span><span class="sxs-lookup"><span data-stu-id="73f26-117">Return value</span></span>

<span data-ttu-id="73f26-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="73f26-118">TRUE</span></span> 
  
> <span data-ttu-id="73f26-119">这两个属性名称相等。</span><span class="sxs-lookup"><span data-stu-id="73f26-119">The two property names are equal.</span></span> 
    
<span data-ttu-id="73f26-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="73f26-120">FALSE</span></span> 
  
> <span data-ttu-id="73f26-121">这两个属性名称不相等。</span><span class="sxs-lookup"><span data-stu-id="73f26-121">The two property names are not equal.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="73f26-122">注解</span><span class="sxs-lookup"><span data-stu-id="73f26-122">Remarks</span></span>

<span data-ttu-id="73f26-123">**FEqualNames**函数很有用, 因为**MAPINAMEID**结构包含一个[GUID](guid.md) , 并且可以通过多种方式表示属性名称本身。</span><span class="sxs-lookup"><span data-stu-id="73f26-123">The **FEqualNames** function is useful because the **MAPINAMEID** structure contains a [GUID](guid.md) and can represent the property name itself in more than one way.</span></span> <span data-ttu-id="73f26-124">这意味着, 不能通过简单的二进制方法比较这两个结构。</span><span class="sxs-lookup"><span data-stu-id="73f26-124">This means the two structures cannot be compared by simple binary methods.</span></span> 
  
<span data-ttu-id="73f26-125">测试过程对于属性名称字符串而言是区分大小写的。</span><span class="sxs-lookup"><span data-stu-id="73f26-125">The testing process is case-sensitive for the property name strings.</span></span> 
  

