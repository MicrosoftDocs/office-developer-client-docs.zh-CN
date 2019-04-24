---
title: 实现 IUnknown 接口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01bba63b-a2a1-490e-8b78-5c9ba8d9547b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5165476ea131e40153191e8625af5ea3c49f47b1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310043"
---
# <a name="implementing-the-iunknown-interface"></a><span data-ttu-id="37dae-103">实现 IUnknown 接口</span><span class="sxs-lookup"><span data-stu-id="37dae-103">Implementing the IUnknown Interface</span></span>

  
  
<span data-ttu-id="37dae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="37dae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="37dae-105">在每个 MAPI 对象中实现的[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)接口的方法, 支持 interobject 通信和对象管理。</span><span class="sxs-lookup"><span data-stu-id="37dae-105">The methods of the [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) interface, implemented in every MAPI object, support interobject communication and object management.</span></span> 
  
 <span data-ttu-id="37dae-106">**iunknown**具有三种方法: [iunknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)、 [IUnknown:: QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)和[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="37dae-106">**IUnknown** has three methods: [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx), [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx), and [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx).</span></span> <span data-ttu-id="37dae-107">通过**QueryInterface** , 一个对象可以确定另一个对象是否支持特定接口。</span><span class="sxs-lookup"><span data-stu-id="37dae-107">**QueryInterface** enables one object to determine whether another object supports a particular interface.</span></span> <span data-ttu-id="37dae-108">在**QueryInterface**中, 没有事先了解彼此的功能的两个对象可以进行交互。</span><span class="sxs-lookup"><span data-stu-id="37dae-108">With **QueryInterface**, two objects with no prior knowledge of each other's functionality can interact.</span></span> <span data-ttu-id="37dae-109">如果实现**QueryInterface**的对象确实支持所涉及的接口, 它将返回指向接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="37dae-109">If the object that implements **QueryInterface** does support the interface in question, it returns a pointer to the implementation of the interface.</span></span> <span data-ttu-id="37dae-110">如果对象不支持所请求的接口, 它将返回 MAPI_E_INTERFACE_NOT_SUPPORTED 值。</span><span class="sxs-lookup"><span data-stu-id="37dae-110">If the object does not support the requested interface, it returns the MAPI_E_INTERFACE_NOT_SUPPORTED value.</span></span> 
  
<span data-ttu-id="37dae-111">当**QueryInterface**返回请求的接口指针时, 它还必须增加新对象的引用计数。</span><span class="sxs-lookup"><span data-stu-id="37dae-111">When **QueryInterface** returns a requested interface pointer, it must also increase the new object's reference count.</span></span> <span data-ttu-id="37dae-112">对象的引用计数是用于管理对象的生命周期的数字值。</span><span class="sxs-lookup"><span data-stu-id="37dae-112">An object's reference count is a numeric value used to manage the object's lifespan.</span></span> <span data-ttu-id="37dae-113">当引用计数大于1时, 无法释放该对象的内存, 因为它正在使用中。</span><span class="sxs-lookup"><span data-stu-id="37dae-113">When the reference count is greater than 1, the object's memory cannot be freed because it is actively being used.</span></span> <span data-ttu-id="37dae-114">仅当该引用计数降至0时, 才能安全地释放该对象。</span><span class="sxs-lookup"><span data-stu-id="37dae-114">It is only when the reference count drops to 0 that the object can be released safely.</span></span> 
  
<span data-ttu-id="37dae-115">其他两个**IUnknown**方法**AddRef**和**Release**, 用于管理引用计数。</span><span class="sxs-lookup"><span data-stu-id="37dae-115">The other two **IUnknown** methods, **AddRef** and **Release**, manage the reference count.</span></span> <span data-ttu-id="37dae-116">**AddRef**会增加引用计数, 而**发布**会将其减少。</span><span class="sxs-lookup"><span data-stu-id="37dae-116">**AddRef** increments the reference count, while **Release** decrements it.</span></span> <span data-ttu-id="37dae-117">返回接口指针 (如**QueryInterface**) 的所有方法或 API 函数都必须调用**AddRef**以递增引用计数。</span><span class="sxs-lookup"><span data-stu-id="37dae-117">All methods or API functions that return interface pointers, such as **QueryInterface**, must call **AddRef** to increment the reference count.</span></span> <span data-ttu-id="37dae-118">接收接口指针的方法的所有实现都必须调用**Release**以在指针不再需要时减小计数。</span><span class="sxs-lookup"><span data-stu-id="37dae-118">All implementations of methods that receive interface pointers must call **Release** to decrement the count when the pointer is no longer needed.</span></span> <span data-ttu-id="37dae-119">**发布**检查现有的引用计数, 仅在计数为0时释放与接口关联的内存。</span><span class="sxs-lookup"><span data-stu-id="37dae-119">**Release** checks for an existing reference count, freeing the memory associated with the interface only if the count is 0.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="37dae-120">由于**AddRef**和**Release**不需要返回准确的值, 因此这些方法的调用方不得使用返回值来确定对象是否仍有效或已被销毁。</span><span class="sxs-lookup"><span data-stu-id="37dae-120">Because **AddRef** and **Release** are not required to return accurate values, callers of these methods must not use the return values to determine whether an object is still valid or has been destroyed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="37dae-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37dae-121">See also</span></span>



[<span data-ttu-id="37dae-122">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="37dae-122">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)

