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
ms.openlocfilehash: ca3752e8f7e910994811dec85cc2f1b00e184661
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584806"
---
# <a name="mapi-interfaces"></a><span data-ttu-id="ef675-103">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="ef675-103">MAPI Interfaces</span></span>

  
  
<span data-ttu-id="ef675-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ef675-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ef675-105">每个接口的文档包含介绍性部分，包含后跟一个表，包含以下信息的接口的用途的简要说明。</span><span class="sxs-lookup"><span data-stu-id="ef675-105">The documentation for each interface consists of an introductory section that includes a brief description of the interface's purpose followed by a table that contains the following information.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ef675-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ef675-106">Header file:</span></span>  <br/> |<span data-ttu-id="ef675-107">其中定义接口，并且必须包含源代码编译头文件。</span><span class="sxs-lookup"><span data-stu-id="ef675-107">The header file where the interface is defined and that must be included when you compile your source code.</span></span>  <br/> |
|<span data-ttu-id="ef675-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="ef675-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="ef675-109">公开接口的对象。</span><span class="sxs-lookup"><span data-stu-id="ef675-109">The object that exposes the interface.</span></span>  <br/> |
|<span data-ttu-id="ef675-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ef675-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="ef675-111">提供了实现接口的组件列表。</span><span class="sxs-lookup"><span data-stu-id="ef675-111">A list of the components that provide an implementation of the interface.</span></span>  <br/> |
|<span data-ttu-id="ef675-112">调用：</span><span class="sxs-lookup"><span data-stu-id="ef675-112">Called by:</span></span>  <br/> |<span data-ttu-id="ef675-113">通常调用接口的方法的组件列表。</span><span class="sxs-lookup"><span data-stu-id="ef675-113">A list of the components that typically call the methods of the interface.</span></span>  <br/> |
|<span data-ttu-id="ef675-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="ef675-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="ef675-115">接口标识符 GUID。</span><span class="sxs-lookup"><span data-stu-id="ef675-115">The interface identifier GUID.</span></span>  <br/> |
|<span data-ttu-id="ef675-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="ef675-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="ef675-117">公开接口对象的指针类型。</span><span class="sxs-lookup"><span data-stu-id="ef675-117">The pointer type for the object that exposes the interface.</span></span>  <br/> |
|<span data-ttu-id="ef675-118">事务模型：</span><span class="sxs-lookup"><span data-stu-id="ef675-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="ef675-119">接口派生自[IMAPIProp](imapipropiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="ef675-119">For interfaces derived from [IMAPIProp](imapipropiunknown.md).</span></span> <span data-ttu-id="ef675-120">如果 nontransacted，更改将立即生效。如果事务处理，更改执行操作会生效，直到调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md) 。</span><span class="sxs-lookup"><span data-stu-id="ef675-120">If nontransacted, changes take effect immediately; if transacted, changes do not take effect until [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span>  <br/> |
   
<span data-ttu-id="ef675-121">后面的第一个表格是另一个表中列出此接口按 vtable 顺序排列的所有方法。</span><span class="sxs-lookup"><span data-stu-id="ef675-121">Following the first table is another table that lists all the methods of this interface in vtable order.</span></span> <span data-ttu-id="ef675-122">Vtable 是一个函数指针包含每个方法的 MAPI 对象的一个函数指针编译器所创建的数组。</span><span class="sxs-lookup"><span data-stu-id="ef675-122">A vtable is an array of function pointers created by the compiler containing one function pointer for each method of a MAPI object.</span></span> <span data-ttu-id="ef675-123">声明它们的相同顺序列出了的方法。</span><span class="sxs-lookup"><span data-stu-id="ef675-123">The methods are listed in the same order that they are declared.</span></span> <span data-ttu-id="ef675-124">方法继承自其他接口 Vtable 顺序排列表中未显示，但可使用相同的方式，定义其界面中所述。</span><span class="sxs-lookup"><span data-stu-id="ef675-124">Methods inherited from other interfaces are not shown in the Vtable Order table but can be used in the same way as documented in the interface that defines them.</span></span>
  
<span data-ttu-id="ef675-125">每个接口主题后接口方法然后记录以字母顺序列出。</span><span class="sxs-lookup"><span data-stu-id="ef675-125">After each interface topic, the interface's methods are then documented in alphabetical order.</span></span> <span data-ttu-id="ef675-126">针对每种方法，文档中包含的简短用途语句语法块和以下信息。</span><span class="sxs-lookup"><span data-stu-id="ef675-126">For each method, the documentation includes a brief purpose statement, a syntax block, and the following information.</span></span>
  
|<span data-ttu-id="ef675-127">**标题**</span><span class="sxs-lookup"><span data-stu-id="ef675-127">**Heading**</span></span>|<span data-ttu-id="ef675-128">**内容**</span><span class="sxs-lookup"><span data-stu-id="ef675-128">**Content**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ef675-129">参数</span><span class="sxs-lookup"><span data-stu-id="ef675-129">Parameters</span></span>  <br/> |<span data-ttu-id="ef675-130">在方法中的每个参数的说明。</span><span class="sxs-lookup"><span data-stu-id="ef675-130">A description of each parameter in the method.</span></span>  <br/> |
|<span data-ttu-id="ef675-131">返回值</span><span class="sxs-lookup"><span data-stu-id="ef675-131">Return Value</span></span>  <br/> |<span data-ttu-id="ef675-132">该方法可返回唯一值的说明。</span><span class="sxs-lookup"><span data-stu-id="ef675-132">A description of the unique values that the method can return.</span></span> <span data-ttu-id="ef675-133">这些是在其代码应检查呼叫者的值。</span><span class="sxs-lookup"><span data-stu-id="ef675-133">These are the values that callers should check for in their code.</span></span>  <br/> |
|<span data-ttu-id="ef675-134">注解</span><span class="sxs-lookup"><span data-stu-id="ef675-134">Remarks</span></span>  <br/> |<span data-ttu-id="ef675-135">为什么以及如何使用该方法的说明。</span><span class="sxs-lookup"><span data-stu-id="ef675-135">A description of why and how the method is used.</span></span>  <br/> |
|<span data-ttu-id="ef675-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef675-136">See Also</span></span>  <br/> |<span data-ttu-id="ef675-137">对此引用中的其他主题的交叉引用。</span><span class="sxs-lookup"><span data-stu-id="ef675-137">Cross-references to other topics in this Reference.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ef675-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef675-138">See also</span></span>



[<span data-ttu-id="ef675-139">MAPI 引用</span><span class="sxs-lookup"><span data-stu-id="ef675-139">MAPI Reference</span></span>](mapi-reference.md)

