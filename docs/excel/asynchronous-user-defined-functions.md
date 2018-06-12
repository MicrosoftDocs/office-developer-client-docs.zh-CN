---
title: 异步的用户定义函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 142eb27e-fb6f-4da3-bfb7-a88115bbb5d5
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 5b64dfd4308da4efb5e94010fe1dc9d758a1199c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773624"
---
# <a name="asynchronous-user-defined-functions"></a>异步的用户定义函数

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
Microsoft Excel 2013 可以异步调用用户定义函数。 异步调用的函数可以同时运行的几个计算，从而提高性能。 在计算群集上运行用户定义的函数时，异步调用的函数允许多个计算机要用于完成计算。
  
## <a name="when-to-use-asynchronous-user-defined-functions"></a>何时使用异步的用户定义函数

用户定义的一些功能必须等待外部资源。 等待，Excel 计算线程而被阻止。 在 Excel 2013 中的用户定义函数可异步运行。 这样可释放的计算线程时的用户定义的函数等待运行其他计算。
  
在 Excel 2007 中，程序员无法运行多个用户定义函数同时通过增大多线程的重新计算中使用的线程数。 此方法有缺点主要由于的线程数向应用程序范围的设置且不能在单个函数或外接程序级别控制。
  
程序员应使用用户定义的异步函数调用时函数必须等待外部资源。 例如，通过 Internet 发送的 SOAP 请求的函数必须等待的网络发送请求，以完成请求，远程服务器和网络返回的结果。 在这种情况下，没有任何重要的计算出现并 Excel 可以继续执行其他计算。
  
程序员函数将请求发送到群集时，还可以使用异步的用户定义函数。 在这种情况下，不是仅网络延迟要等待的时间，但群集可以在单独服务器上执行单独的调用。 通过不等待完成每个呼叫时，可以重叠呼叫以提高性能。 在某些情况下此改进非常重要。
  
> [!NOTE]
> 无法注册为异步和群集安全用户定义函数。 
  
## <a name="writing-an-asynchronous-user-defined-function"></a>编写异步的用户定义函数

用户定义的异步函数必须保持联系的句柄并告知 Excel 函数调用完毕时使用该句柄。 异步的用户定义的函数分为两条。 第一条将启动第二个单独的异步操作的标准 UDF 入口点。 导入 Excel 回调应当期间的 UDF 入口点。 该函数的第一个启动部分将返回到 Excel，将继续计算其计算线程的控制。 第二个异步操作完成后，它必须回调到 Excel 和 Excel 提供其结果。 
  
> [!NOTE]
> 通过异步部分所需的任何参数传递给 UDF 函数必须深入复制，因为 Excel 释放这些参数时返回的 UDF 入口点。 
  
Excel 提供了一组 XLL 加载项可以使用来管理生命周期的异步 UDF 调用的事件。 这些事件指示 Excel 完毕与计算或计算已取消。
  
### <a name="declaring-an-asynchronous-function"></a>声明的异步函数

在注册时，您必须声明为异步异步的用户定义的函数。 执行此操作的任意位置的 UDF 参数列表中添加的注册的类型字符串中的"X"XLOPER12 结构中，指向表示一个参数。 Excel 使用此参数传递的异步调用句柄。 XLL 加载项必须通过异步调用句柄和函数的结果返回到 Excel 结果就绪时。 此外，UDF 的返回类型应**void**，指定">"作为类型字符串中的第一个字符。 返回类型是 void，因为 UDF 的同步部分不会返回到 Excel 的值。 相反，XLL 加载项返回异步通过回拨值。 
  
可以将异步函数声明为线程安全，然后在多线程的重新计算中使用 UDF 的同步部分。 
  
下面的代码示例显示注册使用异步的用户定义函数"\>QX"为注册类型字符串：
  
```cpp
void MyAsyncUDF(LPXLOPER12 arg1, LPXLOPER12 pxAsyncHandle)
{
…
}
```

### <a name="returning-values"></a>返回值

异步调用的结果准备就绪后，XLL 加载项将结果返回给 Excel 通过执行类型[xlAsyncReturn](xlasyncreturn.md)回调。
  
**xlAsyncReturn**是您可以使用非计算线程重新计算过程中仅回调。 因此，异步 UDF 的异步部分不应执行任何其他回调。 
  
### <a name="handling-events"></a>处理事件

启动在 Excel 2010 xll （英文） 可以接收旨在管理的异步函数生命周期的事件。 有关详细信息，请参阅[处理事件](handling-events.md)。
  
## <a name="see-also"></a>另请参阅

- [Developing Excel XLLs](developing-excel-xlls.md)

