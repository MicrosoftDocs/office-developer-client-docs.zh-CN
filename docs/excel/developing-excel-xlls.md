---
title: 开发 Excel XLL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 外接程序-[excel 2007，] 开发 xll （英文)-[Excel 2007]，Xll-[Excel 2007，] 开发
localization_priority: Normal
ms.assetid: dd27ae4d-ef97-47db-885c-ddd955816900
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: cb2483b9cd1b11bcfeee81bba02b6d593e8818fc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773649"
---
# <a name="developing-excel-xlls"></a><span data-ttu-id="69a59-104">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="69a59-104">Developing Excel XLLs</span></span>

<span data-ttu-id="69a59-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="69a59-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="69a59-106">编写 Microsoft Excel Xll 和使用 C API 的主要原因是创建高性能工作表函数。</span><span class="sxs-lookup"><span data-stu-id="69a59-106">The primary reason for writing Microsoft Excel XLLs and using the C API is to create high-performance worksheet functions.</span></span> <span data-ttu-id="69a59-107">高性能函数的应用程序 — 和启动在 Excel 2007 中，多线程的接口写入强大的服务器资源能力 — 使其非常重要 Excel 可扩展性的一部分。</span><span class="sxs-lookup"><span data-stu-id="69a59-107">The applications of high-performance functions—and, starting in Excel 2007, the ability to write multithreaded interfaces to powerful server resources—make it a very important part of Excel extensibility.</span></span> <span data-ttu-id="69a59-108">Xll 的性能已进一步增强 Excel 2007 中的新数据类型和，最重要、 支持多线程。</span><span class="sxs-lookup"><span data-stu-id="69a59-108">The performance of XLLs was further enhanced in Excel 2007 by the addition of new data types and, most important, support for multithreading.</span></span>
  
<span data-ttu-id="69a59-109">C API 有无较高级别的快速开发功能的 Microsoft Visual Basic for Applications (VBA)、 COM 或 Microsoft.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="69a59-109">The C API has none of the higher-level rapid development features of Microsoft Visual Basic for Applications (VBA), COM, or the Microsoft .NET Framework.</span></span> <span data-ttu-id="69a59-110">内存管理是低级别，因此负有开发人员更高版本的责任。</span><span class="sxs-lookup"><span data-stu-id="69a59-110">Memory management is low level, and therefore puts greater responsibility on the developer.</span></span> <span data-ttu-id="69a59-111">与 C API 不公开 COM，使其可通过 VBA 和.NET Framework 中，通过公开的许多 Excel 功能。</span><span class="sxs-lookup"><span data-stu-id="69a59-111">Many Excel features that are exposed through COM, making them available through VBA and the .NET Framework, are not exposed to the C API.</span></span>


- [<span data-ttu-id="69a59-112">Excel Programming Concepts</span><span class="sxs-lookup"><span data-stu-id="69a59-112">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
  
- [<span data-ttu-id="69a59-113">使用 DLL</span><span class="sxs-lookup"><span data-stu-id="69a59-113">Working with DLLs</span></span>](working-with-dlls.md)
  
- [<span data-ttu-id="69a59-114">在 Excel 中访问 XLL 代码</span><span class="sxs-lookup"><span data-stu-id="69a59-114">Accessing XLL Code in Excel</span></span>](accessing-xll-code-in-excel.md)
  
- [<span data-ttu-id="69a59-115">从函数向导或替换对话框调用 XLL 函数</span><span class="sxs-lookup"><span data-stu-id="69a59-115">Call XLL Functions from the Function Wizard or Replace Dialog Boxes</span></span>](how-to-call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes.md)
  
- [<span data-ttu-id="69a59-116">从 DLL 或 XLL 调用 Excel</span><span class="sxs-lookup"><span data-stu-id="69a59-116">Calling into Excel from the DLL or XLL</span></span>](calling-into-excel-from-the-dll-or-xll.md)
  
- [<span data-ttu-id="69a59-117">创建 XLL</span><span class="sxs-lookup"><span data-stu-id="69a59-117">Creating XLLs</span></span>](creating-xlls.md)
  
- [<span data-ttu-id="69a59-118">Evaluating Names and Other Worksheet Formula Expressions</span><span class="sxs-lookup"><span data-stu-id="69a59-118">Evaluating Names and Other Worksheet Formula Expressions</span></span>](evaluating-names-and-other-worksheet-formula-expressions.md)
  
- [<span data-ttu-id="69a59-119">多线程处理和内存管理</span><span class="sxs-lookup"><span data-stu-id="69a59-119">Multithreading and Memory Management</span></span>](multithreading-and-memory-management.md)
  
- [<span data-ttu-id="69a59-120">用户定义的异步函数</span><span class="sxs-lookup"><span data-stu-id="69a59-120">Asynchronous User-Defined Functions</span></span>](asynchronous-user-defined-functions.md)
  
- [<span data-ttu-id="69a59-121">群集安全函数</span><span class="sxs-lookup"><span data-stu-id="69a59-121">Cluster Safe Functions</span></span>](cluster-safe-functions.md)
  
- [<span data-ttu-id="69a59-122">在长时间的操作中允许用户中断</span><span class="sxs-lookup"><span data-stu-id="69a59-122">Permitting User Breaks in Lengthy Operations</span></span>](permitting-user-breaks-in-lengthy-operations.md)
  
- [<span data-ttu-id="69a59-123">从 DLL 或 XLL 内显示对话框</span><span class="sxs-lookup"><span data-stu-id="69a59-123">Displaying Dialog Boxes from Within a DLL or XLL</span></span>](displaying-dialog-boxes-from-within-a-dll-or-xll.md)
  
- [<span data-ttu-id="69a59-124">访问 Excel 实例和主窗口句柄</span><span class="sxs-lookup"><span data-stu-id="69a59-124">Access Excel Instance and Main Window Handles</span></span>](how-to-access-excel-instance-and-main-window-handles.md)
  
- [<span data-ttu-id="69a59-125">向后兼容性</span><span class="sxs-lookup"><span data-stu-id="69a59-125">Backward Compatibility</span></span>](backward-compatibility.md)
  

