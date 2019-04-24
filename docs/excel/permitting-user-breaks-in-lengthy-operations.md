---
title: 允许用户在漫长的操作中中断
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xlabort 函数 [excel 2007], 并发任务 [excel 2007], 用户中断 [excel 2007]
localization_priority: Normal
ms.assetid: 0e3df597-0aa6-497f-bc52-58c7dc064538
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 650af14e4e97ebd2642a4442a87965f313d3b556
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310379"
---
# <a name="permitting-user-breaks-in-lengthy-operations"></a>允许用户在漫长的操作中中断

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
尽管 Windows 使用抢先式多任务处理, 其中的函数或命令可能需要很长时间才能执行, 但很好的做法是立即为操作系统生成一些时间, 以帮助 it 计划并发任务。 使用本机 Windows 调用时, 可以通过使用 sleep 函数来执行此操作。 使用 C API, 您可以使用[xlAbort 函数](xlabort.md)执行此操作, 它不仅会生成即时处理器, 还会检查用户是否已按下 "取消" 键 ( **ESC**)。
  
因此, **xlAbort**函数使您的代码能够检查用户是否要结束该进程, 执行必要的清理, 然后将控制返回到 Excel。 函数还使您能够清除中断条件。 这将允许您的命令显示一个对话框, 以验证用户是否要结束该命令。 如果用户不希望结束命令, 则使用参数调用**xlAbort**函数将清除 break。 ** (默认参数为*TRUE* , 只检查条件但不清除它。) 
  
您可以从用户定义函数 (UDF) 或 XLL 命令调用**xlAbort**函数。 在 UDF 中, 当**xlAbort**函数返回**TRUE**时, 检测到用户中断, 通常会缩短函数计算的时间, 并返回一些值, 以指示计算未完成, 可能是错误或零。 您不能清除中断条件, 以便同时检查此条件的较长函数的其他实例也会中断。 在重新计算结束时, Excel 将隐式清除此条件。
  
在命令中检测到中断条件时, 通常会通过使用参数**FALSE**再次调用**xlAbort**函数来清除该条件, 尽管 Excel 会在命令结束时隐式清除此条件。
  
## <a name="see-also"></a>另请参阅



[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[Developing Excel XLLs](developing-excel-xlls.md)
  
[访问 Excel 实例和主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)

