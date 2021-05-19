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
# <a name="permitting-user-breaks-in-lengthy-operations"></a><span data-ttu-id="74085-104">允许用户在冗长操作中中断</span><span class="sxs-lookup"><span data-stu-id="74085-104">Permitting User Breaks in Lengthy Operations</span></span>

 <span data-ttu-id="74085-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="74085-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="74085-106">即使Windows使用抢先的多任务处理（其中函数或命令可能需要很长时间来执行）也是一种好的做法，现在再三向操作系统提供一些时间以帮助其安排并发任务。</span><span class="sxs-lookup"><span data-stu-id="74085-106">Even though Windows uses preemptive multitasking, where your functions or commands can take a long time to execute, it is good practice to yield some time to the operating system now and again to help it schedule concurrent tasks.</span></span> <span data-ttu-id="74085-107">使用本机Windows调用，可以通过使用睡眠函数实现此操作。</span><span class="sxs-lookup"><span data-stu-id="74085-107">Using native Windows calls, you can do this by using the sleep function.</span></span> <span data-ttu-id="74085-108">使用 C API，可以使用 [xlAbort](xlabort.md)函数实现，该函数不仅可立即生成处理器，还可以检查用户是否按下了取消键 **ESC。**</span><span class="sxs-lookup"><span data-stu-id="74085-108">Using the C API, you can do it by using the [xlAbort function](xlabort.md), which not only yields the processor for an instant, but also checks to see if the user has pressed the cancel key, **ESC**.</span></span>
  
<span data-ttu-id="74085-109">因此 **，xlAbort** 函数允许您的代码检查用户是否要结束该过程，执行必要的清理，然后将控制权返回给Excel。</span><span class="sxs-lookup"><span data-stu-id="74085-109">The **xlAbort** function therefore enables your code to check whether the user wants to end the process, do the necessary cleanup, and then return control to Excel.</span></span> <span data-ttu-id="74085-110">函数还允许您清除中断条件。</span><span class="sxs-lookup"><span data-stu-id="74085-110">The function also enables you to clear the break condition.</span></span> <span data-ttu-id="74085-111">这样，命令可以显示一个对话框来验证用户是否要结束该命令。</span><span class="sxs-lookup"><span data-stu-id="74085-111">This enables your commands to display a dialog box to verify whether the user wants to end the command.</span></span> <span data-ttu-id="74085-112">如果用户不想结束该命令，则使用参数 *FALSE* 调用 **xlAbort** 函数将清除中断。</span><span class="sxs-lookup"><span data-stu-id="74085-112">If the user does not want to end the command, calling the **xlAbort** function with the argument  *FALSE*  clears the break.</span></span> <span data-ttu-id="74085-113"> (默认参数为  *TRUE*  ，它只检查条件但不清除它。) </span><span class="sxs-lookup"><span data-stu-id="74085-113">(The default argument is  *TRUE*  , which simply checks the condition but does not clear it.)</span></span> 
  
<span data-ttu-id="74085-114">可以从 UDF 函数或 XLL (函数) **xlAbort** 函数。</span><span class="sxs-lookup"><span data-stu-id="74085-114">You can call the **xlAbort** function from a user-defined function (UDF) or from an XLL command.</span></span> <span data-ttu-id="74085-115">在 UDF 中，当 **xlAbort** 函数返回 **TRUE** 时，检测到用户中断后，通常会截短函数计算并返回一个值，以指示计算未完成（可能是错误或零）。</span><span class="sxs-lookup"><span data-stu-id="74085-115">In a UDF, when the **xlAbort** function returns **TRUE**, having detected a user break, you would typically cut short the function calculation and return some value to indicate that the calculation was not completed, perhaps an error or zero.</span></span> <span data-ttu-id="74085-116">您不会清除中断条件，以便同时检查此条件的长函数的其他实例也会中断。</span><span class="sxs-lookup"><span data-stu-id="74085-116">You would not clear the break condition so that other instances of lengthy functions that also check this condition also break.</span></span> <span data-ttu-id="74085-117">Excel重新计算结束时隐式清除此条件。</span><span class="sxs-lookup"><span data-stu-id="74085-117">Excel implicitly clears this condition when a recalculation ends.</span></span>
  
<span data-ttu-id="74085-118">在命令中检测中断条件时，通常使用参数 **FALSE** 再次调用 **xlAbort** 函数来清除该条件，尽管命令结束时，Excel隐式清除此条件。</span><span class="sxs-lookup"><span data-stu-id="74085-118">When you detect a break condition in a command, you typically clear the condition by calling the **xlAbort** function again with the argument **FALSE**, although Excel implicitly clears this condition when a command ends.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="74085-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74085-119">See also</span></span>



[<span data-ttu-id="74085-120">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="74085-120">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[<span data-ttu-id="74085-121">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="74085-121">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
  
[<span data-ttu-id="74085-122">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="74085-122">Developing Excel XLLs</span></span>](developing-excel-xlls.md)
  
[<span data-ttu-id="74085-123">访问 Excel 实例和主窗口句柄</span><span class="sxs-lookup"><span data-stu-id="74085-123">Access Excel Instance and Main Window Handles</span></span>](how-to-access-excel-instance-and-main-window-handles.md)

