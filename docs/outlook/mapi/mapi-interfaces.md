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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422661"
---
# <a name="mapi-interfaces"></a><span data-ttu-id="0451f-103">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="0451f-103">MAPI Interfaces</span></span>

  
  
<span data-ttu-id="0451f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0451f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0451f-105">每个接口的文档都包含一个介绍性部分，其中包括接口用途的简要说明，后跟一个包含以下信息的表。</span><span class="sxs-lookup"><span data-stu-id="0451f-105">The documentation for each interface consists of an introductory section that includes a brief description of the interface's purpose followed by a table that contains the following information.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0451f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0451f-106">Header file:</span></span>  <br/> |<span data-ttu-id="0451f-107">定义接口且编译源代码时必须包含的标头文件。</span><span class="sxs-lookup"><span data-stu-id="0451f-107">The header file where the interface is defined and that must be included when you compile your source code.</span></span>  <br/> |
|<span data-ttu-id="0451f-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="0451f-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="0451f-109">公开接口的对象。</span><span class="sxs-lookup"><span data-stu-id="0451f-109">The object that exposes the interface.</span></span>  <br/> |
|<span data-ttu-id="0451f-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="0451f-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="0451f-111">提供接口实现的组件列表。</span><span class="sxs-lookup"><span data-stu-id="0451f-111">A list of the components that provide an implementation of the interface.</span></span>  <br/> |
|<span data-ttu-id="0451f-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="0451f-112">Called by:</span></span>  <br/> |<span data-ttu-id="0451f-113">通常调用接口方法的组件列表。</span><span class="sxs-lookup"><span data-stu-id="0451f-113">A list of the components that typically call the methods of the interface.</span></span>  <br/> |
|<span data-ttu-id="0451f-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="0451f-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="0451f-115">接口标识符 GUID。</span><span class="sxs-lookup"><span data-stu-id="0451f-115">The interface identifier GUID.</span></span>  <br/> |
|<span data-ttu-id="0451f-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="0451f-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="0451f-117">公开接口的对象的指针类型。</span><span class="sxs-lookup"><span data-stu-id="0451f-117">The pointer type for the object that exposes the interface.</span></span>  <br/> |
|<span data-ttu-id="0451f-118">事务模型：</span><span class="sxs-lookup"><span data-stu-id="0451f-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="0451f-119">对于派生自 [IMAPIProp 的接口](imapipropiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="0451f-119">For interfaces derived from [IMAPIProp](imapipropiunknown.md).</span></span> <span data-ttu-id="0451f-120">如果未翻译，更改将立即生效;如果已处理，则更改在 [调用 IMAPIProp：：SaveChanges 之前](imapiprop-savechanges.md) 不会生效。</span><span class="sxs-lookup"><span data-stu-id="0451f-120">If nontransacted, changes take effect immediately; if transacted, changes do not take effect until [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span>  <br/> |
   
<span data-ttu-id="0451f-121">第一个表后是另一个以 vtable 顺序列出此接口的所有方法的表。</span><span class="sxs-lookup"><span data-stu-id="0451f-121">Following the first table is another table that lists all the methods of this interface in vtable order.</span></span> <span data-ttu-id="0451f-122">vtable 是由编译器创建的函数指针的数组，该数组包含 MAPI 对象的每个方法的一个函数指针。</span><span class="sxs-lookup"><span data-stu-id="0451f-122">A vtable is an array of function pointers created by the compiler containing one function pointer for each method of a MAPI object.</span></span> <span data-ttu-id="0451f-123">这些方法的列出顺序与声明方法的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="0451f-123">The methods are listed in the same order that they are declared.</span></span> <span data-ttu-id="0451f-124">从其他接口继承的方法未显示在 Vtable Order 表中，但可以使用与定义这些方法的接口中记录的方法相同的方式使用。</span><span class="sxs-lookup"><span data-stu-id="0451f-124">Methods inherited from other interfaces are not shown in the Vtable Order table but can be used in the same way as documented in the interface that defines them.</span></span>
  
<span data-ttu-id="0451f-125">在每个接口主题之后，将按字母顺序记录接口的方法。</span><span class="sxs-lookup"><span data-stu-id="0451f-125">After each interface topic, the interface's methods are then documented in alphabetical order.</span></span> <span data-ttu-id="0451f-126">对于每种方法，该文档都包括一个简短用途语句、一个语法块和以下信息。</span><span class="sxs-lookup"><span data-stu-id="0451f-126">For each method, the documentation includes a brief purpose statement, a syntax block, and the following information.</span></span>
  
|<span data-ttu-id="0451f-127">**标题**</span><span class="sxs-lookup"><span data-stu-id="0451f-127">**Heading**</span></span>|<span data-ttu-id="0451f-128">**Content**</span><span class="sxs-lookup"><span data-stu-id="0451f-128">**Content**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0451f-129">参数</span><span class="sxs-lookup"><span data-stu-id="0451f-129">Parameters</span></span>  <br/> |<span data-ttu-id="0451f-130">方法中每个参数的说明。</span><span class="sxs-lookup"><span data-stu-id="0451f-130">A description of each parameter in the method.</span></span>  <br/> |
|<span data-ttu-id="0451f-131">返回值</span><span class="sxs-lookup"><span data-stu-id="0451f-131">Return Value</span></span>  <br/> |<span data-ttu-id="0451f-132">方法可返回的唯一值的说明。</span><span class="sxs-lookup"><span data-stu-id="0451f-132">A description of the unique values that the method can return.</span></span> <span data-ttu-id="0451f-133">这些是调用方应在代码中检查的值。</span><span class="sxs-lookup"><span data-stu-id="0451f-133">These are the values that callers should check for in their code.</span></span>  <br/> |
|<span data-ttu-id="0451f-134">备注</span><span class="sxs-lookup"><span data-stu-id="0451f-134">Remarks</span></span>  <br/> |<span data-ttu-id="0451f-135">有关使用方法的原因和方式的说明。</span><span class="sxs-lookup"><span data-stu-id="0451f-135">A description of why and how the method is used.</span></span>  <br/> |
|<span data-ttu-id="0451f-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0451f-136">See Also</span></span>  <br/> |<span data-ttu-id="0451f-137">此参考中其他主题的交叉引用。</span><span class="sxs-lookup"><span data-stu-id="0451f-137">Cross-references to other topics in this Reference.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0451f-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0451f-138">See also</span></span>



[<span data-ttu-id="0451f-139">MAPI 引用</span><span class="sxs-lookup"><span data-stu-id="0451f-139">MAPI Reference</span></span>](mapi-reference.md)

