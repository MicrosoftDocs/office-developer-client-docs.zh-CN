---
title: 用户定义的异步函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 142eb27e-fb6f-4da3-bfb7-a88115bbb5d5
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7fdf3bd09914981865c911fd65a78d044ad582f4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412308"
---
# <a name="asynchronous-user-defined-functions"></a><span data-ttu-id="2a31b-103">用户定义的异步函数</span><span class="sxs-lookup"><span data-stu-id="2a31b-103">Asynchronous user-defined functions</span></span>

<span data-ttu-id="2a31b-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a31b-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2a31b-105">Microsoft Excel 2013可以异步调用用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="2a31b-105">Microsoft Excel 2013 can call user-defined functions asynchronously.</span></span> <span data-ttu-id="2a31b-106">异步调用函数可通过允许同时运行多个计算来提高性能。</span><span class="sxs-lookup"><span data-stu-id="2a31b-106">Calling functions asynchronously can improve performance by allowing several calculations to run at the same time.</span></span> <span data-ttu-id="2a31b-107">在计算机群集中运行用户定义函数时，异步调用函数允许使用多台计算机完成计算。</span><span class="sxs-lookup"><span data-stu-id="2a31b-107">When you run user-defined functions on a compute cluster, calling functions asynchronously enables several computers to be used to complete the calculations.</span></span>
  
## <a name="when-to-use-asynchronous-user-defined-functions"></a><span data-ttu-id="2a31b-108">何时使用异步用户定义函数</span><span class="sxs-lookup"><span data-stu-id="2a31b-108">When to use asynchronous user-defined functions</span></span>

<span data-ttu-id="2a31b-109">某些用户定义的函数必须等待外部资源。</span><span class="sxs-lookup"><span data-stu-id="2a31b-109">Some user-defined functions must wait for external resources.</span></span> <span data-ttu-id="2a31b-110">当他们等待时，Excel计算线程将被阻止。</span><span class="sxs-lookup"><span data-stu-id="2a31b-110">While they wait, the Excel calculation thread is blocked.</span></span> <span data-ttu-id="2a31b-111">在 Excel 2013 中，用户定义的函数可以异步运行。</span><span class="sxs-lookup"><span data-stu-id="2a31b-111">In Excel 2013, user-defined functions can run asynchronously.</span></span> <span data-ttu-id="2a31b-112">这将释放计算线程，以在用户定义的函数等待时运行其他计算。</span><span class="sxs-lookup"><span data-stu-id="2a31b-112">This frees the calculation thread to run other calculations while the user-defined function waits.</span></span>
  
<span data-ttu-id="2a31b-113">在 Excel 2007 中，编程人员可以通过增加多线程重新计算中使用的线程数来同时运行多个用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="2a31b-113">In Excel 2007, programmers could run multiple user-defined functions at the same time by increasing the number of threads used in multiple-thread recalculations.</span></span> <span data-ttu-id="2a31b-114">此方法有缺点，主要是因为线程数是一个作用域为应用程序的设置，不能在单个函数或外接程序的级别进行控制。</span><span class="sxs-lookup"><span data-stu-id="2a31b-114">This method has drawbacks primarily because the number of threads is a setting scoped to an application and cannot be controlled at the level of a single function or an add-in.</span></span>
  
<span data-ttu-id="2a31b-115">当函数必须等待外部资源时，程序员应该使用异步用户定义的函数调用。</span><span class="sxs-lookup"><span data-stu-id="2a31b-115">Programmers should use asynchronous user-defined function calls when the function must wait for external resources.</span></span> <span data-ttu-id="2a31b-116">例如，通过 Internet 发送 SOAP 请求的函数必须等待网络传递请求、远程服务器完成请求以及网络返回结果。</span><span class="sxs-lookup"><span data-stu-id="2a31b-116">For example, a function that sends a SOAP request over the Internet must wait for the network to deliver the request, the remote server to complete the request, and the network to return the result.</span></span> <span data-ttu-id="2a31b-117">在这种情况下，不会进行重大计算，Excel继续进行其他计算。</span><span class="sxs-lookup"><span data-stu-id="2a31b-117">In this case, there is no significant computing occurring and Excel can continue with other calculations.</span></span>
  
<span data-ttu-id="2a31b-118">当函数向计算群集发送请求时，编程人员还可使用异步用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="2a31b-118">Programmers can also use asynchronous user-defined functions when a function is sending requests to a compute cluster.</span></span> <span data-ttu-id="2a31b-119">在这种情况下，不仅存在等待的网络延迟，而且群集可以在单独的服务器上执行单独的调用。</span><span class="sxs-lookup"><span data-stu-id="2a31b-119">In this case, there is not only network latency to wait for, but the cluster can execute separate calls on separate servers.</span></span> <span data-ttu-id="2a31b-120">通过不等待每个调用完成，可以重叠调用以提高性能。</span><span class="sxs-lookup"><span data-stu-id="2a31b-120">By not waiting for each call to finish, the calls can be overlapped to improve performance.</span></span> <span data-ttu-id="2a31b-121">在某些情况下，此改进很显著。</span><span class="sxs-lookup"><span data-stu-id="2a31b-121">In some cases this improvement is significant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a31b-122">用户定义的函数不能同时注册为异步和群集安全。</span><span class="sxs-lookup"><span data-stu-id="2a31b-122">User-defined functions cannot be registered as both asynchronous and cluster safe.</span></span> 
  
## <a name="writing-an-asynchronous-user-defined-function"></a><span data-ttu-id="2a31b-123">编写异步用户定义函数</span><span class="sxs-lookup"><span data-stu-id="2a31b-123">Writing an asynchronous user-defined function</span></span>

<span data-ttu-id="2a31b-124">异步用户定义函数必须跟踪句柄，并使用该句柄在通知用户Excel函数调用已完成时使用该句柄。</span><span class="sxs-lookup"><span data-stu-id="2a31b-124">Asynchronous user-defined functions must keep track of a handle and use that handle when informing Excel that the function call is finished.</span></span> <span data-ttu-id="2a31b-125">异步用户定义函数拆分为两个部分。</span><span class="sxs-lookup"><span data-stu-id="2a31b-125">An asynchronous user-defined function is split into two pieces.</span></span> <span data-ttu-id="2a31b-126">第一部分是标准 UDF 入口点，它将启动第二个单独的异步操作。</span><span class="sxs-lookup"><span data-stu-id="2a31b-126">The first piece is the standard UDF entry point, which will launch a second, separate asynchronous operation.</span></span> <span data-ttu-id="2a31b-127">应在 UDF Excel期间回调到 Excel。</span><span class="sxs-lookup"><span data-stu-id="2a31b-127">Callbacks into Excel should be made during the UDF entry point.</span></span> <span data-ttu-id="2a31b-128">然后，函数的第一个启动部分会返回计算线程的控制权Excel，这将继续进行计算。</span><span class="sxs-lookup"><span data-stu-id="2a31b-128">The first launching portion of the function will then return control of its calculation thread to Excel, which will continue calculation.</span></span> <span data-ttu-id="2a31b-129">当第二个异步操作完成时，它必须回Excel并提供Excel返回结果。</span><span class="sxs-lookup"><span data-stu-id="2a31b-129">When the second asynchronous operation is complete, it must call back into Excel and provide Excel with its result.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2a31b-130">传入异步部分函数所需的 UDF 的任何参数都必须深层复制，因为当 UDF 入口点返回时，Excel释放这些参数。</span><span class="sxs-lookup"><span data-stu-id="2a31b-130">Any arguments passed into the UDF that are needed by the asynchronous portion the function must be deep copied because Excel frees these arguments when the UDF entry point returns.</span></span> 
  
<span data-ttu-id="2a31b-131">Excel提供了一组事件，XLL 加载项可以使用这些事件来管理异步 UDF 调用的生命周期。</span><span class="sxs-lookup"><span data-stu-id="2a31b-131">Excel provides a set of events that an XLL add-in can use in order to manage the life cycle of asynchronous UDF calls.</span></span> <span data-ttu-id="2a31b-132">这些事件指示Excel已完成计算或已取消计算。</span><span class="sxs-lookup"><span data-stu-id="2a31b-132">These events indicate that Excel is finished with calculations or that the calculation was canceled.</span></span>
  
### <a name="declaring-an-asynchronous-function"></a><span data-ttu-id="2a31b-133">声明异步函数</span><span class="sxs-lookup"><span data-stu-id="2a31b-133">Declaring an asynchronous function</span></span>

<span data-ttu-id="2a31b-134">注册异步用户定义函数时，必须将这些函数声明为异步。</span><span class="sxs-lookup"><span data-stu-id="2a31b-134">You must declare asynchronous user-defined functions as asynchronous when they are registered.</span></span> <span data-ttu-id="2a31b-135">这是通过添加一个参数来执行的，该参数指向 UDF 参数列表中任意位置的注册类型字符串中的"X"表示的 XLOPER12 结构。</span><span class="sxs-lookup"><span data-stu-id="2a31b-135">This is performed by adding a parameter that points to a XLOPER12 structure, represented by "X" in the registration type string, anywhere in the list of UDF parameters.</span></span> <span data-ttu-id="2a31b-136">Excel使用此参数传递异步调用句柄。</span><span class="sxs-lookup"><span data-stu-id="2a31b-136">Excel uses this parameter to pass the asynchronous call handle.</span></span> <span data-ttu-id="2a31b-137">当结果准备就绪时，XLL 加载项必须将异步调用句柄和函数结果Excel传递回代码。</span><span class="sxs-lookup"><span data-stu-id="2a31b-137">The XLL add-in must pass the asynchronous call handle and the result of the function back to Excel when the result is ready.</span></span> <span data-ttu-id="2a31b-138">此外，UDF 的返回类型应为 **void**，由">"指定为类型字符串的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="2a31b-138">In addition, the return type of the UDF should be **void**, designated by ">" as the first character in the type string.</span></span> <span data-ttu-id="2a31b-139">返回类型为 void，因为 UDF 的同步部分不会将值返回到Excel。</span><span class="sxs-lookup"><span data-stu-id="2a31b-139">The return type is void because the synchronous part of the UDF does not return a value to Excel.</span></span> <span data-ttu-id="2a31b-140">相反，XLL 加载项通过回调异步返回值。</span><span class="sxs-lookup"><span data-stu-id="2a31b-140">Instead, the XLL add-in returns a value asynchronously through a callback.</span></span> 
  
<span data-ttu-id="2a31b-141">你可以将异步函数声明为线程安全函数，然后在多线程重新计算中使用 UDF 的同步部分。</span><span class="sxs-lookup"><span data-stu-id="2a31b-141">You can declare asynchronous functions as thread-safe and then the synchronous part of the UDF is used in a multi-threaded recalculation.</span></span> 
  
<span data-ttu-id="2a31b-142">以下代码示例演示使用"QX"作为注册类型字符串注册的异步 \> 用户定义函数：</span><span class="sxs-lookup"><span data-stu-id="2a31b-142">The following code example shows an asynchronous user-defined function registered by using "\>QX" as the registration type string:</span></span>
  
```cpp
void MyAsyncUDF(LPXLOPER12 arg1, LPXLOPER12 pxAsyncHandle)
{
…
}
```

### <a name="returning-values"></a><span data-ttu-id="2a31b-143">返回值</span><span class="sxs-lookup"><span data-stu-id="2a31b-143">Returning values</span></span>

<span data-ttu-id="2a31b-144">异步调用的结果准备就绪后，XLL 加载项通过执行[xlAsyncReturn](xlasyncreturn.md)类型的回调Excel将结果返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="2a31b-144">When the result of the asynchronous call is ready, the XLL add-in returns the result to Excel by performing a callback of type [xlAsyncReturn](xlasyncreturn.md).</span></span>
  
<span data-ttu-id="2a31b-145">**xlAsyncReturn** 是可以在重新计算期间在非计算线程上使用的唯一回调。</span><span class="sxs-lookup"><span data-stu-id="2a31b-145">**xlAsyncReturn** is the only callback you can use on non-calculation threads during recalculation.</span></span> <span data-ttu-id="2a31b-146">因此，异步 UDF 的异步部分不应执行任何其他回调。</span><span class="sxs-lookup"><span data-stu-id="2a31b-146">Therefore, the asynchronous part of an asynchronous UDF should not perform any other callbacks.</span></span> 
  
### <a name="handling-events"></a><span data-ttu-id="2a31b-147">处理事件</span><span class="sxs-lookup"><span data-stu-id="2a31b-147">Handling events</span></span>

<span data-ttu-id="2a31b-148">从 Excel 2010 开始，XLL 可以接收旨在管理异步函数生命周期的事件。</span><span class="sxs-lookup"><span data-stu-id="2a31b-148">Starting in Excel 2010, XLLs can receive events designed to manage the asynchronous function life cycle.</span></span> <span data-ttu-id="2a31b-149">有关详细信息，请参阅 [处理事件](handling-events.md)。</span><span class="sxs-lookup"><span data-stu-id="2a31b-149">For more information, see [Handling Events](handling-events.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2a31b-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a31b-150">See also</span></span>

- [<span data-ttu-id="2a31b-151">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="2a31b-151">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

