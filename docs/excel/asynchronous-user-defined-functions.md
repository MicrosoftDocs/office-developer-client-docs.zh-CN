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
# <a name="asynchronous-user-defined-functions"></a>用户定义的异步函数

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 2013可以异步调用用户定义的函数。 异步调用函数可通过允许同时运行多个计算来提高性能。 在计算机群集中运行用户定义函数时，异步调用函数允许使用多台计算机完成计算。
  
## <a name="when-to-use-asynchronous-user-defined-functions"></a>何时使用异步用户定义函数

某些用户定义的函数必须等待外部资源。 当他们等待时，Excel计算线程将被阻止。 在 Excel 2013 中，用户定义的函数可以异步运行。 这将释放计算线程，以在用户定义的函数等待时运行其他计算。
  
在 Excel 2007 中，编程人员可以通过增加多线程重新计算中使用的线程数来同时运行多个用户定义函数。 此方法有缺点，主要是因为线程数是一个作用域为应用程序的设置，不能在单个函数或外接程序的级别进行控制。
  
当函数必须等待外部资源时，程序员应该使用异步用户定义的函数调用。 例如，通过 Internet 发送 SOAP 请求的函数必须等待网络传递请求、远程服务器完成请求以及网络返回结果。 在这种情况下，不会进行重大计算，Excel继续进行其他计算。
  
当函数向计算群集发送请求时，编程人员还可使用异步用户定义函数。 在这种情况下，不仅存在等待的网络延迟，而且群集可以在单独的服务器上执行单独的调用。 通过不等待每个调用完成，可以重叠调用以提高性能。 在某些情况下，此改进很显著。
  
> [!NOTE]
> 用户定义的函数不能同时注册为异步和群集安全。 
  
## <a name="writing-an-asynchronous-user-defined-function"></a>编写异步用户定义函数

异步用户定义函数必须跟踪句柄，并使用该句柄在通知用户Excel函数调用已完成时使用该句柄。 异步用户定义函数拆分为两个部分。 第一部分是标准 UDF 入口点，它将启动第二个单独的异步操作。 应在 UDF Excel期间回调到 Excel。 然后，函数的第一个启动部分会返回计算线程的控制权Excel，这将继续进行计算。 当第二个异步操作完成时，它必须回Excel并提供Excel返回结果。 
  
> [!NOTE]
> 传入异步部分函数所需的 UDF 的任何参数都必须深层复制，因为当 UDF 入口点返回时，Excel释放这些参数。 
  
Excel提供了一组事件，XLL 加载项可以使用这些事件来管理异步 UDF 调用的生命周期。 这些事件指示Excel已完成计算或已取消计算。
  
### <a name="declaring-an-asynchronous-function"></a>声明异步函数

注册异步用户定义函数时，必须将这些函数声明为异步。 这是通过添加一个参数来执行的，该参数指向 UDF 参数列表中任意位置的注册类型字符串中的"X"表示的 XLOPER12 结构。 Excel使用此参数传递异步调用句柄。 当结果准备就绪时，XLL 加载项必须将异步调用句柄和函数结果Excel传递回代码。 此外，UDF 的返回类型应为 **void**，由">"指定为类型字符串的第一个字符。 返回类型为 void，因为 UDF 的同步部分不会将值返回到Excel。 相反，XLL 加载项通过回调异步返回值。 
  
你可以将异步函数声明为线程安全函数，然后在多线程重新计算中使用 UDF 的同步部分。 
  
以下代码示例演示使用"QX"作为注册类型字符串注册的异步 \> 用户定义函数：
  
```cpp
void MyAsyncUDF(LPXLOPER12 arg1, LPXLOPER12 pxAsyncHandle)
{
…
}
```

### <a name="returning-values"></a>返回值

异步调用的结果准备就绪后，XLL 加载项通过执行[xlAsyncReturn](xlasyncreturn.md)类型的回调Excel将结果返回到客户端。
  
**xlAsyncReturn** 是可以在重新计算期间在非计算线程上使用的唯一回调。 因此，异步 UDF 的异步部分不应执行任何其他回调。 
  
### <a name="handling-events"></a>处理事件

从 Excel 2010 开始，XLL 可以接收旨在管理异步函数生命周期的事件。 有关详细信息，请参阅 [处理事件](handling-events.md)。
  
## <a name="see-also"></a>另请参阅

- [开发 Excel XLL](developing-excel-xlls.md)

