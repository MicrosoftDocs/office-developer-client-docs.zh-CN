---
title: 在长时间的操作中允许用户中断
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xlabort 函数 [excel 2007，] 并发任务 [Excel 2007，] 用户页符 [Excel 2007]
localization_priority: Normal
ms.assetid: 0e3df597-0aa6-497f-bc52-58c7dc064538
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: b13f9b9a8c0e5621b25df13537632bdbe5dfc29e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773804"
---
# <a name="permitting-user-breaks-in-lengthy-operations"></a>在长时间的操作中允许用户中断

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
即使 Windows 使用预防多任务，您的函数或命令花费很长时间才能执行，最好归纳出到操作系统和再次现在以帮助其安排并发任务一些时间。 使用本机 Windows 呼叫，您可以执行此操作使用休眠函数。 使用 C API，您可以执行它使用[xlAbort 函数](xlabort.md)，它们不仅参加即时，会产生处理器，但也检查用户已按取消键， **esc 键**。
  
**XlAbort**函数因此允许您的代码以检查用户是否想要结束过程、 执行必要清理，并将返回到 Excel 的控件。 该函数还可以清除中断条件。 这使您的命令以显示一个对话框，以验证用户是否要结束命令。 如果用户不希望结束命令，调用带*FALSE*参数**xlAbort**函数清除断开。 （默认参数为*TRUE* ，这只检查条件，但不清除其。） 
  
从用户定义函数 (UDF) 或 XLL 命令，您可以调用**xlAbort**函数。 在 UDF， **xlAbort**函数将返回**TRUE**，具有检测到用户换时可以将通常剪切短函数计算和返回某个值来指示计算未完成，可能出现错误或零。 不会清除中断条件，以便还检查此条件的长函数的其他实例还中断。 Excel 重新计算结束时将隐式清除此条件。
  
当您在命令检测中断条件时，通常通过调用**xlAbort**函数再次使用**FALSE**，参数清除条件，虽然命令结束后，Excel 将隐式清除此条件。
  
## <a name="see-also"></a>另请参阅



[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[Developing Excel XLLs](developing-excel-xlls.md)
  
[访问 Excel 实例和主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)

