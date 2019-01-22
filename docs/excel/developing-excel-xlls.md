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
# <a name="developing-excel-xlls"></a>开发 Excel XLL

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
编写 Microsoft Excel XLL 和使用 C API 主要是为了创建高性能工作表函数。 应用高性能函数以及自 Excel 2007 起支持能够编写对功能强大服务器资源的多线程接口，都是 Excel 扩展性的非常重要组成部分。 通过新增数据类型以及最为重要的多线程支持，Excel 2007 进一步增强了 XLL 性能。
  
C API 不提供 Microsoft Visual Basic for Applications (VBA)、COM 或 Microsoft .NET Framework 的更高级别快速开发功能。 由于内存管理是低级别的，因此开发人员的责任更大。 通过 COM 公开的许多 Excel 功能（通过 VBA 和 .NET Framework 可用）不向 C API 公开。


- [Excel 编程概念](excel-programming-concepts.md)
  
- [使用 DLL](working-with-dlls.md)
  
- [在 Excel 中访问 XLL 代码](accessing-xll-code-in-excel.md)
  
- [从“函数向导”或“替换”对话框调用 XLL 函数](how-to-call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes.md)
  
- [从 DLL 或 XLL 调用 Excel](calling-into-excel-from-the-dll-or-xll.md)
  
- [创建 XLL](creating-xlls.md)
  
- [求值名称和其他工作表公式表达式](evaluating-names-and-other-worksheet-formula-expressions.md)
  
- [多线程和内存管理](multithreading-and-memory-management.md)
  
- [用户定义异步函数](asynchronous-user-defined-functions.md)
  
- [群集安全函数](cluster-safe-functions.md)
  
- [允许用户中断冗长操作](permitting-user-breaks-in-lengthy-operations.md)
  
- [在 DLL 或 XLL 内显示对话框](displaying-dialog-boxes-from-within-a-dll-or-xll.md)
  
- [访问 Excel 实例和主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)
  
- [向后兼容性](backward-compatibility.md)
  

