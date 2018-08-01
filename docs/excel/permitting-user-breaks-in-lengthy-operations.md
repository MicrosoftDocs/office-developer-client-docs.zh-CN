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
# <a name="permitting-user-breaks-in-lengthy-operations"></a><span data-ttu-id="a125b-104">在长时间的操作中允许用户中断</span><span class="sxs-lookup"><span data-stu-id="a125b-104">Permitting User Breaks in Lengthy Operations</span></span>

 <span data-ttu-id="a125b-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a125b-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a125b-106">即使 Windows 使用预防多任务，您的函数或命令花费很长时间才能执行，最好归纳出到操作系统和再次现在以帮助其安排并发任务一些时间。</span><span class="sxs-lookup"><span data-stu-id="a125b-106">Even though Windows uses preemptive multitasking, where your functions or commands can take a long time to execute, it is good practice to yield some time to the operating system now and again to help it schedule concurrent tasks.</span></span> <span data-ttu-id="a125b-107">使用本机 Windows 呼叫，您可以执行此操作使用休眠函数。</span><span class="sxs-lookup"><span data-stu-id="a125b-107">Using native Windows calls, you can do this by using the sleep function.</span></span> <span data-ttu-id="a125b-108">使用 C API，您可以执行它使用[xlAbort 函数](xlabort.md)，它们不仅参加即时，会产生处理器，但也检查用户已按取消键， **esc 键**。</span><span class="sxs-lookup"><span data-stu-id="a125b-108">Using the C API, you can do it by using the [xlAbort function](xlabort.md), which not only yields the processor for an instant, but also checks to see if the user has pressed the cancel key, **ESC**.</span></span>
  
<span data-ttu-id="a125b-109">**XlAbort**函数因此允许您的代码以检查用户是否想要结束过程、 执行必要清理，并将返回到 Excel 的控件。</span><span class="sxs-lookup"><span data-stu-id="a125b-109">The **xlAbort** function therefore enables your code to check whether the user wants to end the process, do the necessary cleanup, and then return control to Excel.</span></span> <span data-ttu-id="a125b-110">该函数还可以清除中断条件。</span><span class="sxs-lookup"><span data-stu-id="a125b-110">The function also enables you to clear the break condition.</span></span> <span data-ttu-id="a125b-111">这使您的命令以显示一个对话框，以验证用户是否要结束命令。</span><span class="sxs-lookup"><span data-stu-id="a125b-111">This enables your commands to display a dialog box to verify whether the user wants to end the command.</span></span> <span data-ttu-id="a125b-112">如果用户不希望结束命令，调用带*FALSE*参数**xlAbort**函数清除断开。</span><span class="sxs-lookup"><span data-stu-id="a125b-112">If the user does not want to end the command, calling the **xlAbort** function with the argument  *FALSE*  clears the break.</span></span> <span data-ttu-id="a125b-113">（默认参数为*TRUE* ，这只检查条件，但不清除其。）</span><span class="sxs-lookup"><span data-stu-id="a125b-113">(The default argument is  *TRUE*  , which simply checks the condition but does not clear it.)</span></span> 
  
<span data-ttu-id="a125b-114">从用户定义函数 (UDF) 或 XLL 命令，您可以调用**xlAbort**函数。</span><span class="sxs-lookup"><span data-stu-id="a125b-114">You can call the **xlAbort** function from a user-defined function (UDF) or from an XLL command.</span></span> <span data-ttu-id="a125b-115">在 UDF， **xlAbort**函数将返回**TRUE**，具有检测到用户换时可以将通常剪切短函数计算和返回某个值来指示计算未完成，可能出现错误或零。</span><span class="sxs-lookup"><span data-stu-id="a125b-115">In a UDF, when the **xlAbort** function returns **TRUE**, having detected a user break, you would typically cut short the function calculation and return some value to indicate that the calculation was not completed, perhaps an error or zero.</span></span> <span data-ttu-id="a125b-116">不会清除中断条件，以便还检查此条件的长函数的其他实例还中断。</span><span class="sxs-lookup"><span data-stu-id="a125b-116">You would not clear the break condition so that other instances of lengthy functions that also check this condition also break.</span></span> <span data-ttu-id="a125b-117">Excel 重新计算结束时将隐式清除此条件。</span><span class="sxs-lookup"><span data-stu-id="a125b-117">Excel implicitly clears this condition when a recalculation ends.</span></span>
  
<span data-ttu-id="a125b-118">当您在命令检测中断条件时，通常通过调用**xlAbort**函数再次使用**FALSE**，参数清除条件，虽然命令结束后，Excel 将隐式清除此条件。</span><span class="sxs-lookup"><span data-stu-id="a125b-118">When you detect a break condition in a command, you typically clear the condition by calling the **xlAbort** function again with the argument **FALSE**, although Excel implicitly clears this condition when a command ends.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a125b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a125b-119">See also</span></span>



[<span data-ttu-id="a125b-120">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="a125b-120">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[<span data-ttu-id="a125b-121">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="a125b-121">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
  
[<span data-ttu-id="a125b-122">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="a125b-122">Developing Excel XLLs</span></span>](developing-excel-xlls.md)
  
[<span data-ttu-id="a125b-123">访问 Excel 实例和主窗口句柄</span><span class="sxs-lookup"><span data-stu-id="a125b-123">Access Excel Instance and Main Window Handles</span></span>](how-to-access-excel-instance-and-main-window-handles.md)

