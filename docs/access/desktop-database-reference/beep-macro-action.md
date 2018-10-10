---
title: Beep 宏操作 （访问桌面数据库参考 （英文）
TOCTitle: Beep Macro Action
ms:assetid: 5ca1600f-7934-3b3d-19fd-f305cda0e5d8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194572(v=office.15)
ms:contentKeyID: 48545092
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm11853
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 7024734b09544042fa58b8cd95127d8195e5788a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468322"
---
# <a name="beep-macro-action"></a><span data-ttu-id="95dc5-102">Beep 宏操作</span><span class="sxs-lookup"><span data-stu-id="95dc5-102">Beep Macro Action</span></span>


<span data-ttu-id="95dc5-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="95dc5-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="95dc5-104">可以使用 **Beep** 操作通过计算机扬声器发出嘟嘟声。</span><span class="sxs-lookup"><span data-stu-id="95dc5-104">You can use the **Beep** action to sound a beep tone through the computer's speaker.</span></span>

## <a name="setting"></a><span data-ttu-id="95dc5-105">设置</span><span class="sxs-lookup"><span data-stu-id="95dc5-105">Setting</span></span>

<span data-ttu-id="95dc5-106">**Beep** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="95dc5-106">The **Beep** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="95dc5-107">说明</span><span class="sxs-lookup"><span data-stu-id="95dc5-107">Remarks</span></span>

<span data-ttu-id="95dc5-108">可以使用 **Beep** 操作在出现以下情况时发出信号：</span><span class="sxs-lookup"><span data-stu-id="95dc5-108">You can use the **Beep** action to signal the following occurrences:</span></span>

  - <span data-ttu-id="95dc5-109">屏幕发生重要更改。</span><span class="sxs-lookup"><span data-stu-id="95dc5-109">Important screen changes have occurred.</span></span>

  - <span data-ttu-id="95dc5-p101">在控件中输入了错误的数据类型。例如，用户在文本框控件中输入了数值数据。</span><span class="sxs-lookup"><span data-stu-id="95dc5-p101">The wrong kind of data has been entered in a control. For example, the user has entered numeric data in a text box control.</span></span>

  - <span data-ttu-id="95dc5-112">宏已到达指定的点或已完成其操作。</span><span class="sxs-lookup"><span data-stu-id="95dc5-112">A macro has reached a specified point or has completed its actions.</span></span>

<span data-ttu-id="95dc5-113">嘟嘟声的频率和持续时间取决于硬件，因此可能会因计算机而异。</span><span class="sxs-lookup"><span data-stu-id="95dc5-113">The frequency and duration of the beep depend on the hardware, which may vary between computers.</span></span>

<span data-ttu-id="95dc5-114">要在 Visual Basic for Applications (VBA) 模块中运行 **Beep** 操作，请使用 **DoCmd** 对象的 **Beep** 方法。</span><span class="sxs-lookup"><span data-stu-id="95dc5-114">To run the **Beep** action in a Visual Basic for Applications (VBA) module, use the **Beep** method of the **DoCmd** object.</span></span>

