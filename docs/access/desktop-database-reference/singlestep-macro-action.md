---
title: SingleStep 宏操作
TOCTitle: SingleStep Macro Action
ms:assetid: 2836fe1d-fb9b-6b42-acfd-c52e468161d4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191989(v=office.15)
ms:contentKeyID: 48543855
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm47687
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 747df6327dd73c51722b985c441feca08e1f4f42
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466799"
---
# <a name="singlestep-macro-action"></a><span data-ttu-id="66719-102">SingleStep 宏操作</span><span class="sxs-lookup"><span data-stu-id="66719-102">SingleStep Macro Action</span></span>


<span data-ttu-id="66719-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="66719-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="66719-104">可以使用 **SingleStep** 操作暂停宏的执行并打开 **"单步执行宏"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="66719-104">You can use the **SingleStep** action to pause macro execution and open the **Macro Single Step** dialog box.</span></span>

## <a name="setting"></a><span data-ttu-id="66719-105">设置</span><span class="sxs-lookup"><span data-stu-id="66719-105">Setting</span></span>

<span data-ttu-id="66719-106">**SingleStep** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="66719-106">The **SingleStep** action does not have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="66719-107">说明</span><span class="sxs-lookup"><span data-stu-id="66719-107">Remarks</span></span>

  - <span data-ttu-id="66719-p101">使用 **SingleStep** 操作可以找出并修复未正常工作的宏。可以将 **SingleStep** 操作添加到宏中紧邻您怀疑可能导致问题的操作的前面。该操作将暂停宏的执行并打开 **"单步执行宏"** 对话框。此对话框显示有关当前的宏操作的信息，例如宏名称、所有指定的条件、操作名称、参数以及错误号（如果有）。在该对话框中，您可以单击 **"单步执行"** 以前进到下一个宏操作，单击 **"停止所有宏"** 停止当前的宏和任何其他正在运行的宏，或者单击 **"继续"** 停止单步执行并恢复宏的正常运行。</span><span class="sxs-lookup"><span data-stu-id="66719-p101">Use the **SingleStep** action to troubleshoot a macro that is not working properly. You can add the **SingleStep** action to a macro just before an action that you suspect may be the cause of the problem. The action pauses the macro and opens the **Macro Single Step** dialog box. This dialog box displays information about the current macro action, such as the macro name, any specified conditions, the action name, arguments, and the error number, if applicable. In the dialog box, you can click **Step** to advance to the next macro action, **Stop All Macros** to stop the current macro and any other macros that are running, or **Continue** to stop single stepping and resume normal operation of the macro.</span></span>

  - <span data-ttu-id="66719-p102">**SingleStep** 操作等效于在"宏生成器"的 **"设计"** 选项卡上的 **"工具"** 组中单击 **"单步执行"**。这种操作与执行 **SingleStep** 操作之间的差别在于，通过运行 SingleStep 操作，可以将该操作精确地放在宏中您希望开始单步执行的位置。这样就不必单步执行前面的所有操作就能到达您想检查的操作。另一方面，在单击"宏生成器"中的 **"单步执行"** 时，必须先这样做，然后才能运行宏。在这种情况下，单步执行从宏中的第一个操作开始。</span><span class="sxs-lookup"><span data-stu-id="66719-p102">The **SingleStep** action has a similar effect to clicking **Single Step** in the **Tools** group on the **Design** tab of the Macro Builder. The difference between doing this and running the **SingleStep** action is that by running the action, you can place the action in the macro exactly where you want single stepping to begin. That way, you don't have to step through all the previous actions to get to the one you want to examine. On the other hand, when you click **Single Step** in the Macro Builder, you must do so before running the macro. In that case, single stepping begins at the first action in the macro.</span></span>


> [!NOTE]
> <P><span data-ttu-id="66719-p103">[!注释] 如果一直进行单步执行直到宏结束而不单击 <STRONG>"继续"</STRONG>，单步执行在宏执行完时仍将有效。后续运行的任何宏都将从单步执行模式下开始。要关闭单步执行，请单击 <STRONG>"单步执行宏"</STRONG>对话框中的 <STRONG>"继续"</STRONG>，或者在设计视图中打开一个宏，然后在 <STRONG>"设计"</STRONG>选项卡上的 <STRONG>"工具"</STRONG>组中单击 <STRONG>"单步执行"</STRONG>使其不再被选中。</span><span class="sxs-lookup"><span data-stu-id="66719-p103">If you single-step all the way to the end of a macro without clicking <STRONG>Continue</STRONG>, single stepping will still be in effect when the macro ends. Any subsequent macro you run will start in single step mode. To turn off single stepping, either click <STRONG>Continue</STRONG> in the <STRONG>Macro Single Step</STRONG> dialog box, or, with a macro open in Design view, on the <STRONG>Design</STRONG> tab, in the <STRONG>Tools</STRONG> group, click <STRONG>Single Step</STRONG> so that it is no longer selected.</span></span></P>


