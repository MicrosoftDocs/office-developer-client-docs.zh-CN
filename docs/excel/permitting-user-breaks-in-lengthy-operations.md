---
title: 允许用户在冗长操作中中断
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xlabort 函数 [excel 2007]，并发任务 [Excel 2007]，用户中断 [Excel 2007]
localization_priority: Normal
ms.assetid: 0e3df597-0aa6-497f-bc52-58c7dc064538
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 650af14e4e97ebd2642a4442a87965f313d3b556
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414688"
---
# <a name="permitting-user-breaks-in-lengthy-operations"></a>允许用户在冗长操作中中断

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
即使Windows使用抢先的多任务处理（其中函数或命令可能需要很长时间来执行）也是一种好的做法，现在再三向操作系统提供一些时间以帮助其安排并发任务。 使用本机Windows调用，可以通过使用睡眠函数实现此操作。 使用 C API，可以使用 [xlAbort](xlabort.md)函数实现，该函数不仅可立即生成处理器，还可以检查用户是否按下了取消键 **ESC。**
  
因此 **，xlAbort** 函数允许您的代码检查用户是否要结束该过程，执行必要的清理，然后将控制权返回给Excel。 函数还允许您清除中断条件。 这样，命令可以显示一个对话框来验证用户是否要结束该命令。 如果用户不想结束该命令，则使用参数 *FALSE* 调用 **xlAbort** 函数将清除中断。  (默认参数为  *TRUE*  ，它只检查条件但不清除它。)  
  
可以从 UDF 函数或 XLL (函数) **xlAbort** 函数。 在 UDF 中，当 **xlAbort** 函数返回 **TRUE** 时，检测到用户中断后，通常会截短函数计算并返回一个值，以指示计算未完成（可能是错误或零）。 您不会清除中断条件，以便同时检查此条件的长函数的其他实例也会中断。 Excel重新计算结束时隐式清除此条件。
  
在命令中检测中断条件时，通常使用参数 **FALSE** 再次调用 **xlAbort** 函数来清除该条件，尽管命令结束时，Excel隐式清除此条件。
  
## <a name="see-also"></a>另请参阅



[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[开发 Excel XLL](developing-excel-xlls.md)
  
[访问 Excel 实例和主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)

