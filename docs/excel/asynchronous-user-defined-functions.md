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
# <a name="asynchronous-user-defined-functions"></a>用户定义的异步函数

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 2013 可以异步调用用户定义的函数。 通过允许多个计算同时运行, 异步调用函数可提高性能。 在计算机群集中运行用户定义函数时，异步调用函数允许使用多台计算机完成计算。
  
## <a name="when-to-use-asynchronous-user-defined-functions"></a>何时使用异步用户定义函数

某些用户定义的函数必须等待外部资源。 在等待时, Excel 计算线程将被阻止。 在 Excel 2013 中, 用户定义的函数可以异步运行。 这将释放计算线程, 以便在用户定义的函数等待时运行其他计算。
  
在 Excel 2007 中, 程序员可以通过增加多线程重新计算中使用的线程数同时运行多个用户定义的函数。 此方法主要是因为线程的数目为应用程序范围的设置, 无法在单个函数或外接程序级别进行控制。
  
当函数必须等待外部资源时, 程序员应使用异步用户定义的函数调用。 例如, 通过 Internet 发送 SOAP 请求的函数必须等待网络传递请求, 远程服务器才能完成请求, 并使网络返回该结果。 在这种情况下, 不会发生重大计算, Excel 可以继续进行其他计算。
  
当函数向计算群集发送请求时, 程序员也可以使用异步用户定义的函数。 在这种情况下, 不仅存在等待的网络延迟, 而且群集可以在单独的服务器上执行单独的调用。 通过不等待每个调用完成, 可以重叠呼叫以提高性能。 在某些情况下, 这种改进是非常重要的。
  
> [!NOTE]
> 用户定义的函数不能注册为异步和群集安全。 
  
## <a name="writing-an-asynchronous-user-defined-function"></a>编写一个异步用户定义的函数

异步用户定义的函数必须跟踪句柄, 并在通知 Excel 函数调用完成时使用该句柄。 将一个异步用户定义的函数拆分为两个块。 第一部分是标准 UDF 入口点, 它将启动另一个单独的异步操作。 应在 UDF 入口点期间对 Excel 进行回调。 然后, 函数的第一个启动部分将把其计算线程的控制权返回给 Excel, 这将继续计算。 在第二个异步操作完成后, 它必须回调 excel 并向 excel 提供其结果。 
  
> [!NOTE]
> 传递到异步部分的 udf 中的任何参数该函数必须进行深层复制, 因为在 udf 入口点返回时, Excel 将释放这些参数。 
  
Excel 提供了一组可供 XLL 外接程序用来管理异步 UDF 调用的生命周期的事件。 这些事件表明 Excel 已完成计算或取消了计算。
  
### <a name="declaring-an-asynchronous-function"></a>声明异步函数

注册时, 必须将异步用户定义的函数声明为异步。 这是通过添加指向 XLOPER12 结构的参数执行的, 该参数由注册类型字符串中的 "X" 表示, 在 UDF 参数列表中的任何位置。 Excel 使用此参数传递异步调用句柄。 在结果准备就绪后, XLL 加载项必须将异步调用句柄和函数结果传递回 Excel。 此外, UDF 的返回类型应为**void**, 由 ">" 指定为类型字符串中的第一个字符。 由于 UDF 的同步部分不会向 Excel 返回值, 因此返回类型为 void。 相反, XLL 加载项通过回调异步返回值。 
  
可以将异步函数声明为线程安全的, 然后在多线程重新计算中使用 UDF 的同步部分。 
  
下面的代码示例演示使用 "\>QX" 注册为注册类型字符串的异步用户定义的函数:
  
```cpp
void MyAsyncUDF(LPXLOPER12 arg1, LPXLOPER12 pxAsyncHandle)
{
…
}
```

### <a name="returning-values"></a>返回值

异步调用的结果准备就绪后, XLL 加载项将通过执行[xlAsyncReturn](xlasyncreturn.md)类型的回调将结果返回到 Excel。
  
**xlAsyncReturn**是您可以在重新计算期间对非计算线程使用的唯一回调。 因此, 异步 UDF 的异步部分不应执行任何其他回调。 
  
### <a name="handling-events"></a>处理事件

从 Excel 2010 开始, xll 可以接收旨在管理异步函数生命周期的事件。 有关详细信息, 请参阅[处理事件](handling-events.md)。
  
## <a name="see-also"></a>另请参阅

- [开发 Excel XLL](developing-excel-xlls.md)

