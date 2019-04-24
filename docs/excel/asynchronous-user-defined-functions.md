---
title: 用户定义的异步函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 142eb27e-fb6f-4da3-bfb7-a88115bbb5d5
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7fdf3bd09914981865c911fd65a78d044ad582f4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304170"
---
# <a name="asynchronous-user-defined-functions"></a><span data-ttu-id="72768-103">用户定义的异步函数</span><span class="sxs-lookup"><span data-stu-id="72768-103">Asynchronous user-defined functions</span></span>

<span data-ttu-id="72768-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="72768-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="72768-105">Microsoft Excel 2013 可以异步调用用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="72768-105">Microsoft Excel 2013 can call user-defined functions asynchronously.</span></span> <span data-ttu-id="72768-106">通过允许多个计算同时运行, 异步调用函数可提高性能。</span><span class="sxs-lookup"><span data-stu-id="72768-106">Calling functions asynchronously can improve performance by allowing several calculations to run at the same time.</span></span> <span data-ttu-id="72768-107">在计算机群集中运行用户定义函数时，异步调用函数允许使用多台计算机完成计算。</span><span class="sxs-lookup"><span data-stu-id="72768-107">When you run user-defined functions on a compute cluster, calling functions asynchronously enables several computers to be used to complete the calculations.</span></span>
  
## <a name="when-to-use-asynchronous-user-defined-functions"></a><span data-ttu-id="72768-108">何时使用异步用户定义函数</span><span class="sxs-lookup"><span data-stu-id="72768-108">When to use asynchronous user-defined functions</span></span>

<span data-ttu-id="72768-109">某些用户定义的函数必须等待外部资源。</span><span class="sxs-lookup"><span data-stu-id="72768-109">Some user-defined functions must wait for external resources.</span></span> <span data-ttu-id="72768-110">在等待时, Excel 计算线程将被阻止。</span><span class="sxs-lookup"><span data-stu-id="72768-110">While they wait, the Excel calculation thread is blocked.</span></span> <span data-ttu-id="72768-111">在 Excel 2013 中, 用户定义的函数可以异步运行。</span><span class="sxs-lookup"><span data-stu-id="72768-111">In Excel 2013, user-defined functions can run asynchronously.</span></span> <span data-ttu-id="72768-112">这将释放计算线程, 以便在用户定义的函数等待时运行其他计算。</span><span class="sxs-lookup"><span data-stu-id="72768-112">This frees the calculation thread to run other calculations while the user-defined function waits.</span></span>
  
<span data-ttu-id="72768-113">在 Excel 2007 中, 程序员可以通过增加多线程重新计算中使用的线程数同时运行多个用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="72768-113">In Excel 2007, programmers could run multiple user-defined functions at the same time by increasing the number of threads used in multiple-thread recalculations.</span></span> <span data-ttu-id="72768-114">此方法主要是因为线程的数目为应用程序范围的设置, 无法在单个函数或外接程序级别进行控制。</span><span class="sxs-lookup"><span data-stu-id="72768-114">This method has drawbacks primarily because the number of threads is a setting scoped to an application and cannot be controlled at the level of a single function or an add-in.</span></span>
  
<span data-ttu-id="72768-115">当函数必须等待外部资源时, 程序员应使用异步用户定义的函数调用。</span><span class="sxs-lookup"><span data-stu-id="72768-115">Programmers should use asynchronous user-defined function calls when the function must wait for external resources.</span></span> <span data-ttu-id="72768-116">例如, 通过 Internet 发送 SOAP 请求的函数必须等待网络传递请求, 远程服务器才能完成请求, 并使网络返回该结果。</span><span class="sxs-lookup"><span data-stu-id="72768-116">For example, a function that sends a SOAP request over the Internet must wait for the network to deliver the request, the remote server to complete the request, and the network to return the result.</span></span> <span data-ttu-id="72768-117">在这种情况下, 不会发生重大计算, Excel 可以继续进行其他计算。</span><span class="sxs-lookup"><span data-stu-id="72768-117">In this case, there is no significant computing occurring and Excel can continue with other calculations.</span></span>
  
<span data-ttu-id="72768-118">当函数向计算群集发送请求时, 程序员也可以使用异步用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="72768-118">Programmers can also use asynchronous user-defined functions when a function is sending requests to a compute cluster.</span></span> <span data-ttu-id="72768-119">在这种情况下, 不仅存在等待的网络延迟, 而且群集可以在单独的服务器上执行单独的调用。</span><span class="sxs-lookup"><span data-stu-id="72768-119">In this case, there is not only network latency to wait for, but the cluster can execute separate calls on separate servers.</span></span> <span data-ttu-id="72768-120">通过不等待每个调用完成, 可以重叠呼叫以提高性能。</span><span class="sxs-lookup"><span data-stu-id="72768-120">By not waiting for each call to finish, the calls can be overlapped to improve performance.</span></span> <span data-ttu-id="72768-121">在某些情况下, 这种改进是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="72768-121">In some cases this improvement is significant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="72768-122">用户定义的函数不能注册为异步和群集安全。</span><span class="sxs-lookup"><span data-stu-id="72768-122">User-defined functions cannot be registered as both asynchronous and cluster safe.</span></span> 
  
## <a name="writing-an-asynchronous-user-defined-function"></a><span data-ttu-id="72768-123">编写一个异步用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="72768-123">Writing an asynchronous user-defined function</span></span>

<span data-ttu-id="72768-124">异步用户定义的函数必须跟踪句柄, 并在通知 Excel 函数调用完成时使用该句柄。</span><span class="sxs-lookup"><span data-stu-id="72768-124">Asynchronous user-defined functions must keep track of a handle and use that handle when informing Excel that the function call is finished.</span></span> <span data-ttu-id="72768-125">将一个异步用户定义的函数拆分为两个块。</span><span class="sxs-lookup"><span data-stu-id="72768-125">An asynchronous user-defined function is split into two pieces.</span></span> <span data-ttu-id="72768-126">第一部分是标准 UDF 入口点, 它将启动另一个单独的异步操作。</span><span class="sxs-lookup"><span data-stu-id="72768-126">The first piece is the standard UDF entry point, which will launch a second, separate asynchronous operation.</span></span> <span data-ttu-id="72768-127">应在 UDF 入口点期间对 Excel 进行回调。</span><span class="sxs-lookup"><span data-stu-id="72768-127">Callbacks into Excel should be made during the UDF entry point.</span></span> <span data-ttu-id="72768-128">然后, 函数的第一个启动部分将把其计算线程的控制权返回给 Excel, 这将继续计算。</span><span class="sxs-lookup"><span data-stu-id="72768-128">The first launching portion of the function will then return control of its calculation thread to Excel, which will continue calculation.</span></span> <span data-ttu-id="72768-129">在第二个异步操作完成后, 它必须回调 excel 并向 excel 提供其结果。</span><span class="sxs-lookup"><span data-stu-id="72768-129">When the second asynchronous operation is complete, it must call back into Excel and provide Excel with its result.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="72768-130">传递到异步部分的 udf 中的任何参数该函数必须进行深层复制, 因为在 udf 入口点返回时, Excel 将释放这些参数。</span><span class="sxs-lookup"><span data-stu-id="72768-130">Any arguments passed into the UDF that are needed by the asynchronous portion the function must be deep copied because Excel frees these arguments when the UDF entry point returns.</span></span> 
  
<span data-ttu-id="72768-131">Excel 提供了一组可供 XLL 外接程序用来管理异步 UDF 调用的生命周期的事件。</span><span class="sxs-lookup"><span data-stu-id="72768-131">Excel provides a set of events that an XLL add-in can use in order to manage the life cycle of asynchronous UDF calls.</span></span> <span data-ttu-id="72768-132">这些事件表明 Excel 已完成计算或取消了计算。</span><span class="sxs-lookup"><span data-stu-id="72768-132">These events indicate that Excel is finished with calculations or that the calculation was canceled.</span></span>
  
### <a name="declaring-an-asynchronous-function"></a><span data-ttu-id="72768-133">声明异步函数</span><span class="sxs-lookup"><span data-stu-id="72768-133">Declaring an asynchronous function</span></span>

<span data-ttu-id="72768-134">注册时, 必须将异步用户定义的函数声明为异步。</span><span class="sxs-lookup"><span data-stu-id="72768-134">You must declare asynchronous user-defined functions as asynchronous when they are registered.</span></span> <span data-ttu-id="72768-135">这是通过添加指向 XLOPER12 结构的参数执行的, 该参数由注册类型字符串中的 "X" 表示, 在 UDF 参数列表中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="72768-135">This is performed by adding a parameter that points to a XLOPER12 structure, represented by "X" in the registration type string, anywhere in the list of UDF parameters.</span></span> <span data-ttu-id="72768-136">Excel 使用此参数传递异步调用句柄。</span><span class="sxs-lookup"><span data-stu-id="72768-136">Excel uses this parameter to pass the asynchronous call handle.</span></span> <span data-ttu-id="72768-137">在结果准备就绪后, XLL 加载项必须将异步调用句柄和函数结果传递回 Excel。</span><span class="sxs-lookup"><span data-stu-id="72768-137">The XLL add-in must pass the asynchronous call handle and the result of the function back to Excel when the result is ready.</span></span> <span data-ttu-id="72768-138">此外, UDF 的返回类型应为**void**, 由 ">" 指定为类型字符串中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="72768-138">In addition, the return type of the UDF should be **void**, designated by ">" as the first character in the type string.</span></span> <span data-ttu-id="72768-139">由于 UDF 的同步部分不会向 Excel 返回值, 因此返回类型为 void。</span><span class="sxs-lookup"><span data-stu-id="72768-139">The return type is void because the synchronous part of the UDF does not return a value to Excel.</span></span> <span data-ttu-id="72768-140">相反, XLL 加载项通过回调异步返回值。</span><span class="sxs-lookup"><span data-stu-id="72768-140">Instead, the XLL add-in returns a value asynchronously through a callback.</span></span> 
  
<span data-ttu-id="72768-141">可以将异步函数声明为线程安全的, 然后在多线程重新计算中使用 UDF 的同步部分。</span><span class="sxs-lookup"><span data-stu-id="72768-141">You can declare asynchronous functions as thread-safe and then the synchronous part of the UDF is used in a multi-threaded recalculation.</span></span> 
  
<span data-ttu-id="72768-142">下面的代码示例演示使用 "\>QX" 注册为注册类型字符串的异步用户定义的函数:</span><span class="sxs-lookup"><span data-stu-id="72768-142">The following code example shows an asynchronous user-defined function registered by using "\>QX" as the registration type string:</span></span>
  
```cpp
void MyAsyncUDF(LPXLOPER12 arg1, LPXLOPER12 pxAsyncHandle)
{
…
}
```

### <a name="returning-values"></a><span data-ttu-id="72768-143">返回值</span><span class="sxs-lookup"><span data-stu-id="72768-143">Returning values</span></span>

<span data-ttu-id="72768-144">异步调用的结果准备就绪后, XLL 加载项将通过执行[xlAsyncReturn](xlasyncreturn.md)类型的回调将结果返回到 Excel。</span><span class="sxs-lookup"><span data-stu-id="72768-144">When the result of the asynchronous call is ready, the XLL add-in returns the result to Excel by performing a callback of type [xlAsyncReturn](xlasyncreturn.md).</span></span>
  
<span data-ttu-id="72768-145">**xlAsyncReturn**是您可以在重新计算期间对非计算线程使用的唯一回调。</span><span class="sxs-lookup"><span data-stu-id="72768-145">**xlAsyncReturn** is the only callback you can use on non-calculation threads during recalculation.</span></span> <span data-ttu-id="72768-146">因此, 异步 UDF 的异步部分不应执行任何其他回调。</span><span class="sxs-lookup"><span data-stu-id="72768-146">Therefore, the asynchronous part of an asynchronous UDF should not perform any other callbacks.</span></span> 
  
### <a name="handling-events"></a><span data-ttu-id="72768-147">处理事件</span><span class="sxs-lookup"><span data-stu-id="72768-147">Handling events</span></span>

<span data-ttu-id="72768-148">从 Excel 2010 开始, xll 可以接收旨在管理异步函数生命周期的事件。</span><span class="sxs-lookup"><span data-stu-id="72768-148">Starting in Excel 2010, XLLs can receive events designed to manage the asynchronous function life cycle.</span></span> <span data-ttu-id="72768-149">有关详细信息, 请参阅[处理事件](handling-events.md)。</span><span class="sxs-lookup"><span data-stu-id="72768-149">For more information, see [Handling Events](handling-events.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="72768-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72768-150">See also</span></span>

- [<span data-ttu-id="72768-151">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="72768-151">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

