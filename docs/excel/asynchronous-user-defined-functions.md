---
title: 异步的用户定义函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 142eb27e-fb6f-4da3-bfb7-a88115bbb5d5
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5b64dfd4308da4efb5e94010fe1dc9d758a1199c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773624"
---
# <a name="asynchronous-user-defined-functions"></a><span data-ttu-id="1fadd-103">异步的用户定义函数</span><span class="sxs-lookup"><span data-stu-id="1fadd-103">Asynchronous user-defined functions</span></span>

<span data-ttu-id="1fadd-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1fadd-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="1fadd-105">Microsoft Excel 2013 可以异步调用用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="1fadd-105">Microsoft Excel 2013 can call user-defined functions asynchronously.</span></span> <span data-ttu-id="1fadd-106">异步调用的函数可以同时运行的几个计算，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="1fadd-106">Calling functions asynchronously can improve performance by allowing several calculations to run at the same time.</span></span> <span data-ttu-id="1fadd-107">在计算群集上运行用户定义的函数时，异步调用的函数允许多个计算机要用于完成计算。</span><span class="sxs-lookup"><span data-stu-id="1fadd-107">When you run user-defined functions on a compute cluster, calling functions asynchronously enables several computers to be used to complete the calculations.</span></span>
  
## <a name="when-to-use-asynchronous-user-defined-functions"></a><span data-ttu-id="1fadd-108">何时使用异步的用户定义函数</span><span class="sxs-lookup"><span data-stu-id="1fadd-108">When to use asynchronous user-defined functions</span></span>

<span data-ttu-id="1fadd-109">用户定义的一些功能必须等待外部资源。</span><span class="sxs-lookup"><span data-stu-id="1fadd-109">Some user-defined functions must wait for external resources.</span></span> <span data-ttu-id="1fadd-110">等待，Excel 计算线程而被阻止。</span><span class="sxs-lookup"><span data-stu-id="1fadd-110">While they wait, the Excel calculation thread is blocked.</span></span> <span data-ttu-id="1fadd-111">在 Excel 2013 中的用户定义函数可异步运行。</span><span class="sxs-lookup"><span data-stu-id="1fadd-111">In Excel 2013, user-defined functions can run asynchronously.</span></span> <span data-ttu-id="1fadd-112">这样可释放的计算线程时的用户定义的函数等待运行其他计算。</span><span class="sxs-lookup"><span data-stu-id="1fadd-112">This frees the calculation thread to run other calculations while the user-defined function waits.</span></span>
  
<span data-ttu-id="1fadd-113">在 Excel 2007 中，程序员无法运行多个用户定义函数同时通过增大多线程的重新计算中使用的线程数。</span><span class="sxs-lookup"><span data-stu-id="1fadd-113">In Excel 2007, programmers could run multiple user-defined functions at the same time by increasing the number of threads used in multiple-thread recalculations.</span></span> <span data-ttu-id="1fadd-114">此方法有缺点主要由于的线程数向应用程序范围的设置且不能在单个函数或外接程序级别控制。</span><span class="sxs-lookup"><span data-stu-id="1fadd-114">This method has drawbacks primarily because the number of threads is a setting scoped to an application and cannot be controlled at the level of a single function or an add-in.</span></span>
  
<span data-ttu-id="1fadd-115">程序员应使用用户定义的异步函数调用时函数必须等待外部资源。</span><span class="sxs-lookup"><span data-stu-id="1fadd-115">Programmers should use asynchronous user-defined function calls when the function must wait for external resources.</span></span> <span data-ttu-id="1fadd-116">例如，通过 Internet 发送的 SOAP 请求的函数必须等待的网络发送请求，以完成请求，远程服务器和网络返回的结果。</span><span class="sxs-lookup"><span data-stu-id="1fadd-116">For example, a function that sends a SOAP request over the Internet must wait for the network to deliver the request, the remote server to complete the request, and the network to return the result.</span></span> <span data-ttu-id="1fadd-117">在这种情况下，没有任何重要的计算出现并 Excel 可以继续执行其他计算。</span><span class="sxs-lookup"><span data-stu-id="1fadd-117">In this case, there is no significant computing occurring and Excel can continue with other calculations.</span></span>
  
<span data-ttu-id="1fadd-118">程序员函数将请求发送到群集时，还可以使用异步的用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="1fadd-118">Programmers can also use asynchronous user-defined functions when a function is sending requests to a compute cluster.</span></span> <span data-ttu-id="1fadd-119">在这种情况下，不是仅网络延迟要等待的时间，但群集可以在单独服务器上执行单独的调用。</span><span class="sxs-lookup"><span data-stu-id="1fadd-119">In this case, there is not only network latency to wait for, but the cluster can execute separate calls on separate servers.</span></span> <span data-ttu-id="1fadd-120">通过不等待完成每个呼叫时，可以重叠呼叫以提高性能。</span><span class="sxs-lookup"><span data-stu-id="1fadd-120">By not waiting for each call to finish, the calls can be overlapped to improve performance.</span></span> <span data-ttu-id="1fadd-121">在某些情况下此改进非常重要。</span><span class="sxs-lookup"><span data-stu-id="1fadd-121">In some cases this improvement is significant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fadd-122">无法注册为异步和群集安全用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="1fadd-122">User-defined functions cannot be registered as both asynchronous and cluster safe.</span></span> 
  
## <a name="writing-an-asynchronous-user-defined-function"></a><span data-ttu-id="1fadd-123">编写异步的用户定义函数</span><span class="sxs-lookup"><span data-stu-id="1fadd-123">Writing an asynchronous user-defined function</span></span>

<span data-ttu-id="1fadd-124">用户定义的异步函数必须保持联系的句柄并告知 Excel 函数调用完毕时使用该句柄。</span><span class="sxs-lookup"><span data-stu-id="1fadd-124">Asynchronous user-defined functions must keep track of a handle and use that handle when informing Excel that the function call is finished.</span></span> <span data-ttu-id="1fadd-125">异步的用户定义的函数分为两条。</span><span class="sxs-lookup"><span data-stu-id="1fadd-125">An asynchronous user-defined function is split into two pieces.</span></span> <span data-ttu-id="1fadd-126">第一条将启动第二个单独的异步操作的标准 UDF 入口点。</span><span class="sxs-lookup"><span data-stu-id="1fadd-126">The first piece is the standard UDF entry point, which will launch a second, separate asynchronous operation.</span></span> <span data-ttu-id="1fadd-127">导入 Excel 回调应当期间的 UDF 入口点。</span><span class="sxs-lookup"><span data-stu-id="1fadd-127">Callbacks into Excel should be made during the UDF entry point.</span></span> <span data-ttu-id="1fadd-128">该函数的第一个启动部分将返回到 Excel，将继续计算其计算线程的控制。</span><span class="sxs-lookup"><span data-stu-id="1fadd-128">The first launching portion of the function will then return control of its calculation thread to Excel, which will continue calculation.</span></span> <span data-ttu-id="1fadd-129">第二个异步操作完成后，它必须回调到 Excel 和 Excel 提供其结果。</span><span class="sxs-lookup"><span data-stu-id="1fadd-129">When the second asynchronous operation is complete, it must call back into Excel and provide Excel with its result.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1fadd-130">通过异步部分所需的任何参数传递给 UDF 函数必须深入复制，因为 Excel 释放这些参数时返回的 UDF 入口点。</span><span class="sxs-lookup"><span data-stu-id="1fadd-130">Any arguments passed into the UDF that are needed by the asynchronous portion the function must be deep copied because Excel frees these arguments when the UDF entry point returns.</span></span> 
  
<span data-ttu-id="1fadd-131">Excel 提供了一组 XLL 加载项可以使用来管理生命周期的异步 UDF 调用的事件。</span><span class="sxs-lookup"><span data-stu-id="1fadd-131">Excel provides a set of events that an XLL add-in can use in order to manage the life cycle of asynchronous UDF calls.</span></span> <span data-ttu-id="1fadd-132">这些事件指示 Excel 完毕与计算或计算已取消。</span><span class="sxs-lookup"><span data-stu-id="1fadd-132">These events indicate that Excel is finished with calculations or that the calculation was canceled.</span></span>
  
### <a name="declaring-an-asynchronous-function"></a><span data-ttu-id="1fadd-133">声明的异步函数</span><span class="sxs-lookup"><span data-stu-id="1fadd-133">Declaring an asynchronous function</span></span>

<span data-ttu-id="1fadd-134">在注册时，您必须声明为异步异步的用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="1fadd-134">You must declare asynchronous user-defined functions as asynchronous when they are registered.</span></span> <span data-ttu-id="1fadd-135">执行此操作的任意位置的 UDF 参数列表中添加的注册的类型字符串中的"X"XLOPER12 结构中，指向表示一个参数。</span><span class="sxs-lookup"><span data-stu-id="1fadd-135">This is performed by adding a parameter that points to a XLOPER12 structure, represented by "X" in the registration type string, anywhere in the list of UDF parameters.</span></span> <span data-ttu-id="1fadd-136">Excel 使用此参数传递的异步调用句柄。</span><span class="sxs-lookup"><span data-stu-id="1fadd-136">Excel uses this parameter to pass the asynchronous call handle.</span></span> <span data-ttu-id="1fadd-137">XLL 加载项必须通过异步调用句柄和函数的结果返回到 Excel 结果就绪时。</span><span class="sxs-lookup"><span data-stu-id="1fadd-137">The XLL add-in must pass the asynchronous call handle and the result of the function back to Excel when the result is ready.</span></span> <span data-ttu-id="1fadd-138">此外，UDF 的返回类型应**void**，指定">"作为类型字符串中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="1fadd-138">In addition, the return type of the UDF should be **void**, designated by ">" as the first character in the type string.</span></span> <span data-ttu-id="1fadd-139">返回类型是 void，因为 UDF 的同步部分不会返回到 Excel 的值。</span><span class="sxs-lookup"><span data-stu-id="1fadd-139">The return type is void because the synchronous part of the UDF does not return a value to Excel.</span></span> <span data-ttu-id="1fadd-140">相反，XLL 加载项返回异步通过回拨值。</span><span class="sxs-lookup"><span data-stu-id="1fadd-140">Instead, the XLL add-in returns a value asynchronously through a callback.</span></span> 
  
<span data-ttu-id="1fadd-141">可以将异步函数声明为线程安全，然后在多线程的重新计算中使用 UDF 的同步部分。</span><span class="sxs-lookup"><span data-stu-id="1fadd-141">You can declare asynchronous functions as thread-safe and then the synchronous part of the UDF is used in a multi-threaded recalculation.</span></span> 
  
<span data-ttu-id="1fadd-142">下面的代码示例显示注册使用异步的用户定义函数"\>QX"为注册类型字符串：</span><span class="sxs-lookup"><span data-stu-id="1fadd-142">The following code example shows an asynchronous user-defined function registered by using "\>QX" as the registration type string:</span></span>
  
```cpp
void MyAsyncUDF(LPXLOPER12 arg1, LPXLOPER12 pxAsyncHandle)
{
…
}
```

### <a name="returning-values"></a><span data-ttu-id="1fadd-143">返回值</span><span class="sxs-lookup"><span data-stu-id="1fadd-143">Returning values</span></span>

<span data-ttu-id="1fadd-144">异步调用的结果准备就绪后，XLL 加载项将结果返回给 Excel 通过执行类型[xlAsyncReturn](xlasyncreturn.md)回调。</span><span class="sxs-lookup"><span data-stu-id="1fadd-144">When the result of the asynchronous call is ready, the XLL add-in returns the result to Excel by performing a callback of type [xlAsyncReturn](xlasyncreturn.md).</span></span>
  
<span data-ttu-id="1fadd-145">**xlAsyncReturn**是您可以使用非计算线程重新计算过程中仅回调。</span><span class="sxs-lookup"><span data-stu-id="1fadd-145">**xlAsyncReturn** is the only callback you can use on non-calculation threads during recalculation.</span></span> <span data-ttu-id="1fadd-146">因此，异步 UDF 的异步部分不应执行任何其他回调。</span><span class="sxs-lookup"><span data-stu-id="1fadd-146">Therefore, the asynchronous part of an asynchronous UDF should not perform any other callbacks.</span></span> 
  
### <a name="handling-events"></a><span data-ttu-id="1fadd-147">处理事件</span><span class="sxs-lookup"><span data-stu-id="1fadd-147">Handling events</span></span>

<span data-ttu-id="1fadd-148">启动在 Excel 2010 xll （英文） 可以接收旨在管理的异步函数生命周期的事件。</span><span class="sxs-lookup"><span data-stu-id="1fadd-148">Starting in Excel 2010, XLLs can receive events designed to manage the asynchronous function life cycle.</span></span> <span data-ttu-id="1fadd-149">有关详细信息，请参阅[处理事件](handling-events.md)。</span><span class="sxs-lookup"><span data-stu-id="1fadd-149">For more information, see [Handling Events](handling-events.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1fadd-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fadd-150">See also</span></span>

- [<span data-ttu-id="1fadd-151">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="1fadd-151">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

