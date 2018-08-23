---
title: 实施 IUnknown 接口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01bba63b-a2a1-490e-8b78-5c9ba8d9547b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f9ab3b75743d882aca0145b73b8ef707204cc8de
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571897"
---
# <a name="implementing-the-iunknown-interface"></a><span data-ttu-id="2823f-103">实施 IUnknown 接口</span><span class="sxs-lookup"><span data-stu-id="2823f-103">Implementing the IUnknown Interface</span></span>

  
  
<span data-ttu-id="2823f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2823f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2823f-105">[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx)接口中每个 MAPI 对象，, 实现的方法支持 interobject 通信和对象管理。</span><span class="sxs-lookup"><span data-stu-id="2823f-105">The methods of the [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx) interface, implemented in every MAPI object, support interobject communication and object management.</span></span> 
  
 <span data-ttu-id="2823f-106">**IUnknown**具有三个方法： [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)、 [IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)和[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2823f-106">**IUnknown** has three methods: [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx), [IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx), and [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx).</span></span> <span data-ttu-id="2823f-107">**QueryInterface**启用一个对象，以确定另一个对象是否支持特定的接口。</span><span class="sxs-lookup"><span data-stu-id="2823f-107">**QueryInterface** enables one object to determine whether another object supports a particular interface.</span></span> <span data-ttu-id="2823f-108">与**QueryInterface**，事先不了解彼此的功能与两个对象可以进行交互。</span><span class="sxs-lookup"><span data-stu-id="2823f-108">With **QueryInterface**, two objects with no prior knowledge of each other's functionality can interact.</span></span> <span data-ttu-id="2823f-109">如果实现**QueryInterface**的对象不支持问题的接口，它将返回的实现的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2823f-109">If the object that implements **QueryInterface** does support the interface in question, it returns a pointer to the implementation of the interface.</span></span> <span data-ttu-id="2823f-110">如果对象不支持所请求的接口，则返回的 MAPI_E_INTERFACE_NOT_SUPPORTED 值。</span><span class="sxs-lookup"><span data-stu-id="2823f-110">If the object does not support the requested interface, it returns the MAPI_E_INTERFACE_NOT_SUPPORTED value.</span></span> 
  
<span data-ttu-id="2823f-111">当**QueryInterface**返回请求的接口指针时，它还必须增加新对象的引用计数。</span><span class="sxs-lookup"><span data-stu-id="2823f-111">When **QueryInterface** returns a requested interface pointer, it must also increase the new object's reference count.</span></span> <span data-ttu-id="2823f-112">对象的引用计数是用于管理对象的生命周期的数值。</span><span class="sxs-lookup"><span data-stu-id="2823f-112">An object's reference count is a numeric value used to manage the object's lifespan.</span></span> <span data-ttu-id="2823f-113">当引用计数大于 1 时，因为正在使用它无法释放对象的内存。</span><span class="sxs-lookup"><span data-stu-id="2823f-113">When the reference count is greater than 1, the object's memory cannot be freed because it is actively being used.</span></span> <span data-ttu-id="2823f-114">它是仅当引用计数降至 0 对象可以安全地释放。</span><span class="sxs-lookup"><span data-stu-id="2823f-114">It is only when the reference count drops to 0 that the object can be released safely.</span></span> 
  
<span data-ttu-id="2823f-115">其他两个**IUnknown**方法， **AddRef**和**Release**，管理引用计数。</span><span class="sxs-lookup"><span data-stu-id="2823f-115">The other two **IUnknown** methods, **AddRef** and **Release**, manage the reference count.</span></span> <span data-ttu-id="2823f-116">**AddRef**增加引用计数，**版本**递减时它。</span><span class="sxs-lookup"><span data-stu-id="2823f-116">**AddRef** increments the reference count, while **Release** decrements it.</span></span> <span data-ttu-id="2823f-117">所有方法或 API 函数的返回接口的指针，如**QueryInterface**，必须都调用**AddRef**以增加引用计数。</span><span class="sxs-lookup"><span data-stu-id="2823f-117">All methods or API functions that return interface pointers, such as **QueryInterface**, must call **AddRef** to increment the reference count.</span></span> <span data-ttu-id="2823f-118">接收接口指针的方法的所有实现必须都调用**Release**递减计数，当不再需要将指针。</span><span class="sxs-lookup"><span data-stu-id="2823f-118">All implementations of methods that receive interface pointers must call **Release** to decrement the count when the pointer is no longer needed.</span></span> <span data-ttu-id="2823f-119">**版本**检查现有的引用计数，仅当在计数为 0 与接口关联所内存。</span><span class="sxs-lookup"><span data-stu-id="2823f-119">**Release** checks for an existing reference count, freeing the memory associated with the interface only if the count is 0.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2823f-120">由于无需**AddRef**和**Release**返回正确的值，这些方法的调用方不必须使用的返回值来确定对象是否仍然有效或已损坏。</span><span class="sxs-lookup"><span data-stu-id="2823f-120">Because **AddRef** and **Release** are not required to return accurate values, callers of these methods must not use the return values to determine whether an object is still valid or has been destroyed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2823f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2823f-121">See also</span></span>



[<span data-ttu-id="2823f-122">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="2823f-122">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)

