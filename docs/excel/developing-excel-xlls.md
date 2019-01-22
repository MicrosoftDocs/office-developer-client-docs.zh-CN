---
title: 开发 Excel XLL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 加载项 - [excel 2007],开发 XLL - [Excel 2007],XLL - [Excel 2007],开发
ms.assetid: dd27ae4d-ef97-47db-885c-ddd955816900
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: d05041f2629694c4a96240ea83b6e84b17f9be38
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28701093"
---
# <a name="developing-excel-xlls"></a><span data-ttu-id="80eb8-104">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="80eb8-104">Developing Excel XLLs</span></span>

<span data-ttu-id="80eb8-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="80eb8-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="80eb8-106">编写 Microsoft Excel XLL 和使用 C API 主要是为了创建高性能工作表函数。</span><span class="sxs-lookup"><span data-stu-id="80eb8-106">The primary reason for writing Microsoft Excel XLLs and using the C API is to create high-performance worksheet functions.</span></span> <span data-ttu-id="80eb8-107">应用高性能函数以及自 Excel 2007 起支持能够编写对功能强大服务器资源的多线程接口，都是 Excel 扩展性的非常重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="80eb8-107">The applications of high-performance functions—and, starting in Excel 2007, the ability to write multithreaded interfaces to powerful server resources—make it a very important part of Excel extensibility.</span></span> <span data-ttu-id="80eb8-108">通过新增数据类型以及最为重要的多线程支持，Excel 2007 进一步增强了 XLL 性能。</span><span class="sxs-lookup"><span data-stu-id="80eb8-108">The performance of XLLs was further enhanced in Excel 2007 by the addition of new data types and, most important, support for multithreading.</span></span>
  
<span data-ttu-id="80eb8-109">C API 不提供 Microsoft Visual Basic for Applications (VBA)、COM 或 Microsoft .NET Framework 的更高级别快速开发功能。</span><span class="sxs-lookup"><span data-stu-id="80eb8-109">The C API has none of the higher-level rapid development features of Microsoft Visual Basic for Applications (VBA), COM, or the Microsoft .NET Framework.</span></span> <span data-ttu-id="80eb8-110">由于内存管理是低级别的，因此开发人员的责任更大。</span><span class="sxs-lookup"><span data-stu-id="80eb8-110">Memory management is low level, and therefore puts greater responsibility on the developer.</span></span> <span data-ttu-id="80eb8-111">通过 COM 公开的许多 Excel 功能（通过 VBA 和 .NET Framework 可用）不向 C API 公开。</span><span class="sxs-lookup"><span data-stu-id="80eb8-111">Many Excel features that are exposed through COM, making them available through VBA and the .NET Framework, are not exposed to the C API.</span></span>


- [<span data-ttu-id="80eb8-112">Excel 编程概念</span><span class="sxs-lookup"><span data-stu-id="80eb8-112">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
  
- [<span data-ttu-id="80eb8-113">使用 DLL</span><span class="sxs-lookup"><span data-stu-id="80eb8-113">Working with DLLs</span></span>](working-with-dlls.md)
  
- [<span data-ttu-id="80eb8-114">在 Excel 中访问 XLL 代码</span><span class="sxs-lookup"><span data-stu-id="80eb8-114">Accessing XLL code in Excel</span></span>](accessing-xll-code-in-excel.md)
  
- [<span data-ttu-id="80eb8-115">从“函数向导”或“替换”对话框调用 XLL 函数</span><span class="sxs-lookup"><span data-stu-id="80eb8-115">Call XLL functions from the Function Wizard or Replace dialog boxes</span></span>](how-to-call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes.md)
  
- [<span data-ttu-id="80eb8-116">从 DLL 或 XLL 调用 Excel</span><span class="sxs-lookup"><span data-stu-id="80eb8-116">Calling into Excel from the DLL or XLL</span></span>](calling-into-excel-from-the-dll-or-xll.md)
  
- [<span data-ttu-id="80eb8-117">创建 XLL</span><span class="sxs-lookup"><span data-stu-id="80eb8-117">Creating XLLs</span></span>](creating-xlls.md)
  
- [<span data-ttu-id="80eb8-118">求值名称和其他工作表公式表达式</span><span class="sxs-lookup"><span data-stu-id="80eb8-118">Evaluating Names and Other Worksheet Formula Expressions</span></span>](evaluating-names-and-other-worksheet-formula-expressions.md)
  
- [<span data-ttu-id="80eb8-119">多线程和内存管理</span><span class="sxs-lookup"><span data-stu-id="80eb8-119">Multithreading and memory management</span></span>](multithreading-and-memory-management.md)
  
- [<span data-ttu-id="80eb8-120">用户定义异步函数</span><span class="sxs-lookup"><span data-stu-id="80eb8-120">Asynchronous user-defined functions</span></span>](asynchronous-user-defined-functions.md)
  
- [<span data-ttu-id="80eb8-121">群集安全函数</span><span class="sxs-lookup"><span data-stu-id="80eb8-121">Cluster Safe Functions</span></span>](cluster-safe-functions.md)
  
- [<span data-ttu-id="80eb8-122">允许用户中断冗长操作</span><span class="sxs-lookup"><span data-stu-id="80eb8-122">Permitting user breaks in lengthy operations</span></span>](permitting-user-breaks-in-lengthy-operations.md)
  
- [<span data-ttu-id="80eb8-123">在 DLL 或 XLL 内显示对话框</span><span class="sxs-lookup"><span data-stu-id="80eb8-123">Displaying dialog boxes from within a DLL or XLL</span></span>](displaying-dialog-boxes-from-within-a-dll-or-xll.md)
  
- [<span data-ttu-id="80eb8-124">访问 Excel 实例和主窗口句柄</span><span class="sxs-lookup"><span data-stu-id="80eb8-124">Access Excel instance and main window handles</span></span>](how-to-access-excel-instance-and-main-window-handles.md)
  
- [<span data-ttu-id="80eb8-125">向后兼容性</span><span class="sxs-lookup"><span data-stu-id="80eb8-125">Backward compatibility</span></span>](backward-compatibility.md)
  

