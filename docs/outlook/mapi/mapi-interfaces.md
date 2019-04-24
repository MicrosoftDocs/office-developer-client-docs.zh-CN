---
title: MAPI 接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 34a66cf0-b4e0-4fd5-b937-cd157888961d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4f5d6a5d2dbb48a86363896bf14b61ed28118330
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346681"
---
# <a name="mapi-interfaces"></a><span data-ttu-id="c069f-103">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="c069f-103">MAPI Interfaces</span></span>

  
  
<span data-ttu-id="c069f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c069f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c069f-105">每个接口的文档包含一个介绍性部分, 其中包括接口用途的简短说明以及包含以下信息的表。</span><span class="sxs-lookup"><span data-stu-id="c069f-105">The documentation for each interface consists of an introductory section that includes a brief description of the interface's purpose followed by a table that contains the following information.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c069f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c069f-106">Header file:</span></span>  <br/> |<span data-ttu-id="c069f-107">在编译源代码时, 定义接口的头文件和必须包含的头文件。</span><span class="sxs-lookup"><span data-stu-id="c069f-107">The header file where the interface is defined and that must be included when you compile your source code.</span></span>  <br/> |
|<span data-ttu-id="c069f-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="c069f-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="c069f-109">公开接口的对象。</span><span class="sxs-lookup"><span data-stu-id="c069f-109">The object that exposes the interface.</span></span>  <br/> |
|<span data-ttu-id="c069f-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="c069f-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="c069f-111">提供接口实现的组件的列表。</span><span class="sxs-lookup"><span data-stu-id="c069f-111">A list of the components that provide an implementation of the interface.</span></span>  <br/> |
|<span data-ttu-id="c069f-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="c069f-112">Called by:</span></span>  <br/> |<span data-ttu-id="c069f-113">通常调用接口方法的组件的列表。</span><span class="sxs-lookup"><span data-stu-id="c069f-113">A list of the components that typically call the methods of the interface.</span></span>  <br/> |
|<span data-ttu-id="c069f-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="c069f-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="c069f-115">接口标识符 GUID。</span><span class="sxs-lookup"><span data-stu-id="c069f-115">The interface identifier GUID.</span></span>  <br/> |
|<span data-ttu-id="c069f-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="c069f-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="c069f-117">公开接口的对象的指针类型。</span><span class="sxs-lookup"><span data-stu-id="c069f-117">The pointer type for the object that exposes the interface.</span></span>  <br/> |
|<span data-ttu-id="c069f-118">事务模型:</span><span class="sxs-lookup"><span data-stu-id="c069f-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="c069f-119">对于从[IMAPIProp](imapipropiunknown.md)派生的接口。</span><span class="sxs-lookup"><span data-stu-id="c069f-119">For interfaces derived from [IMAPIProp](imapipropiunknown.md).</span></span> <span data-ttu-id="c069f-120">如果 nontransacted, 更改会立即生效;如果进行了事务处理, 则在[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用之前, 更改不会生效。</span><span class="sxs-lookup"><span data-stu-id="c069f-120">If nontransacted, changes take effect immediately; if transacted, changes do not take effect until [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span>  <br/> |
   
<span data-ttu-id="c069f-121">遵循第一个表是另一个表, 它按 vtable 顺序列出此接口的所有方法。</span><span class="sxs-lookup"><span data-stu-id="c069f-121">Following the first table is another table that lists all the methods of this interface in vtable order.</span></span> <span data-ttu-id="c069f-122">vtable 是由编译器创建的一系列函数指针, 其中包含每个 MAPI 对象方法的函数指针。</span><span class="sxs-lookup"><span data-stu-id="c069f-122">A vtable is an array of function pointers created by the compiler containing one function pointer for each method of a MAPI object.</span></span> <span data-ttu-id="c069f-123">这些方法按照声明它们的顺序列出。</span><span class="sxs-lookup"><span data-stu-id="c069f-123">The methods are listed in the same order that they are declared.</span></span> <span data-ttu-id="c069f-124">从其他接口继承的方法不会显示在 Vtable 顺序表中, 但可以按照在定义它们的接口中记录的相同方式使用。</span><span class="sxs-lookup"><span data-stu-id="c069f-124">Methods inherited from other interfaces are not shown in the Vtable Order table but can be used in the same way as documented in the interface that defines them.</span></span>
  
<span data-ttu-id="c069f-125">在每个接口主题之后, 将按字母顺序对接口的方法进行记录。</span><span class="sxs-lookup"><span data-stu-id="c069f-125">After each interface topic, the interface's methods are then documented in alphabetical order.</span></span> <span data-ttu-id="c069f-126">对于每个方法, 文档都包含一个简短的目的语句、一个语法块和以下信息。</span><span class="sxs-lookup"><span data-stu-id="c069f-126">For each method, the documentation includes a brief purpose statement, a syntax block, and the following information.</span></span>
  
|<span data-ttu-id="c069f-127">**标题**</span><span class="sxs-lookup"><span data-stu-id="c069f-127">**Heading**</span></span>|<span data-ttu-id="c069f-128">**Content**</span><span class="sxs-lookup"><span data-stu-id="c069f-128">**Content**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c069f-129">参数</span><span class="sxs-lookup"><span data-stu-id="c069f-129">Parameters</span></span>  <br/> |<span data-ttu-id="c069f-130">方法中的每个参数的说明。</span><span class="sxs-lookup"><span data-stu-id="c069f-130">A description of each parameter in the method.</span></span>  <br/> |
|<span data-ttu-id="c069f-131">返回值</span><span class="sxs-lookup"><span data-stu-id="c069f-131">Return Value</span></span>  <br/> |<span data-ttu-id="c069f-132">该方法可以返回的唯一值的说明。</span><span class="sxs-lookup"><span data-stu-id="c069f-132">A description of the unique values that the method can return.</span></span> <span data-ttu-id="c069f-133">这些是调用方在其代码中应检查的值。</span><span class="sxs-lookup"><span data-stu-id="c069f-133">These are the values that callers should check for in their code.</span></span>  <br/> |
|<span data-ttu-id="c069f-134">注解</span><span class="sxs-lookup"><span data-stu-id="c069f-134">Remarks</span></span>  <br/> |<span data-ttu-id="c069f-135">描述使用方法的原因和方式。</span><span class="sxs-lookup"><span data-stu-id="c069f-135">A description of why and how the method is used.</span></span>  <br/> |
|<span data-ttu-id="c069f-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c069f-136">See Also</span></span>  <br/> |<span data-ttu-id="c069f-137">本参考中对其他主题的交叉引用。</span><span class="sxs-lookup"><span data-stu-id="c069f-137">Cross-references to other topics in this Reference.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c069f-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c069f-138">See also</span></span>



[<span data-ttu-id="c069f-139">MAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c069f-139">MAPI Reference</span></span>](mapi-reference.md)

