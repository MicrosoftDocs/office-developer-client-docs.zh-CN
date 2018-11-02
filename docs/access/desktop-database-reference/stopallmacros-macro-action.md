---
title: StopAllMacros 宏操作
TOCTitle: StopAllMacros macro action
ms:assetid: 6afbf906-03b8-6e68-bbc9-7a4b141cf1c5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195440(v=office.15)
ms:contentKeyID: 48545442
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm104968
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 34dbfc3504744dd446a018e797ebacfb79066d96
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923348"
---
# <a name="stopallmacros-macro-action"></a><span data-ttu-id="c1cb6-102">StopAllMacros 宏操作</span><span class="sxs-lookup"><span data-stu-id="c1cb6-102">StopAllMacros macro action</span></span>


<span data-ttu-id="c1cb6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c1cb6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c1cb6-104">可以使用 **StopAllMacros** 操作停止当前正在运行的所有宏。</span><span class="sxs-lookup"><span data-stu-id="c1cb6-104">You can use the **StopAllMacros** action to stop all macros that are currently running.</span></span>

## <a name="setting"></a><span data-ttu-id="c1cb6-105">设置</span><span class="sxs-lookup"><span data-stu-id="c1cb6-105">Setting</span></span>

<span data-ttu-id="c1cb6-106">**StopAllMacros** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="c1cb6-106">The **StopAllMacros** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1cb6-107">说明</span><span class="sxs-lookup"><span data-stu-id="c1cb6-107">Remarks</span></span>

<span data-ttu-id="c1cb6-108">当由于某种错误情况而不得不停止所有宏时，通常可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="c1cb6-108">You typically use this action when an error condition makes it necessary to stop all macros.</span></span> <span data-ttu-id="c1cb6-109">可以在宏中包含此操作的操作行中使用条件表达式。</span><span class="sxs-lookup"><span data-stu-id="c1cb6-109">You can use a conditional expression in the macro's action row that contains this action.</span></span> <span data-ttu-id="c1cb6-110">当在表达式计算结果为**True** (– 1) 时，Microsoft Access 会停止所有宏。</span><span class="sxs-lookup"><span data-stu-id="c1cb6-110">When the expression evaluates to **True** (–1), Microsoft Access stops all macros.</span></span>

<span data-ttu-id="c1cb6-p102">例如，您可能有一个包含许多复杂操作（包括运行其他宏）的宏，其中的一个操作显示一个消息框。如果用户单击此消息框中的 **"取消"**， **StopAllMacros** 操作可以停止正在运行的所有宏。</span><span class="sxs-lookup"><span data-stu-id="c1cb6-p102">For example, you might have a macro that displays a message box as one of a number of complex actions, including running other macros. If the user clicks **Cancel** in this message box, the **StopAllMacros** action can stop all the macros that are running.</span></span>

<span data-ttu-id="c1cb6-113">如果宏已经使用 **Echo** 或 **SetWarnings** 操作将回响或系统消息的显示关闭， **StopAllMacros** 操作会自动将它们再打开。</span><span class="sxs-lookup"><span data-stu-id="c1cb6-113">If a macro has used the **Echo** or **SetWarnings** actions to turn echo or the display of system messages off, the **StopAllMacros** action automatically turns them back on.</span></span>

<span data-ttu-id="c1cb6-114">此操作在 Visual Basic for Applications (VBA) 模块中不可用。</span><span class="sxs-lookup"><span data-stu-id="c1cb6-114">This action isn't available in a Visual Basic for Applications (VBA) module.</span></span>

