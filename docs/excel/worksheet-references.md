---
title: 工作表引用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- references [excel 2007]， worksheet，worksheet references [Excel 2007]，external worksheet references [Excel 2007]，active worksheet [Excel 2007]，current worksheet [Excel 2007]，internal worksheet references [Excel 2007]
localization_priority: Normal
ms.assetid: 53406fb8-4ca5-4204-a6ad-b21ca9e6a100
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 2944f73a3144837a4be8aff7c7fed9a8d2158203
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416459"
---
# <a name="worksheet-references"></a>工作表引用

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 中的引用是引用单元格 数据类型的矩形块 (该矩形块只能是一个单元格) ，在某些情况下，可以是多个不脱节的单元格块。 在内部Excel，对当前工作表上的单元格使用一种引用类型，称为内部引用。 不在当前工作表上的任何单元格都由另一种引用类型（称为外部引用）描述。 有关活动和当前的定义，请参阅下一节。
  
## <a name="active-vs-current"></a>活动与当前

在Excel中，术语 active 是指用户正在查看的内容。 活动工作簿和工作表是用户当前正在查看的工作簿和工作表，或者，如果Excel应用程序失去焦点，则查看上次Excel焦点的时间。 活动工作表始终位于活动工作簿中。 在活动工作表中选定的一个或多个单元格称为活动单元格。 如果嵌入对象具有焦点，则最后选定的单元格仍处于活动状态。 
  
术语"当前"是指Excel重新计算。 当前工作簿和工作表是当前正在重新计算的工作簿和工作表。 当前工作表始终在当前工作簿中。 重新计算的单元格称为当前单元格，在重新计算数组公式的情况下称为当前单元格。 
  
需要记住的要点如下：
  
- 活动工作簿/工作表/单元格通常不是当前工作簿/工作表/单元格，尽管它可以是当前工作簿/工作表/单元格。
    
- 外接程序函数（无论是在 Visual Basic for Applications (VBA) 模块中，还是 DLL 或 XLL 中）始终从当前工作表上的当前单元格调用，对于多线程重新计算 (MTR) ，始终调用其中一个函数。
    
许多Excel，这些函数提供有关工作簿中单元格、单元格区域或工作表的信息，以区分活动工作簿、工作表或单元格以及当前工作簿、工作表或单元格。 此差异反映在用于描述对单元格块的引用的数据类型中，如下一节所述。
  
## <a name="internal-and-external-worksheet-references"></a>内部和外部工作表引用

内部和外部引用之间的主要区别在于，外部引用引用数据包含工作表的 ID 以及引用哪些单元格的说明。 内部引用不包含对工作表的引用-它是隐式的，即工作表是当前工作表。 
  
许多 C API 函数返回引用或接受引用参数。 任何采用引用参数的 C API 函数都接受内部或外部引用 **，xlSheetNm** 函数除外，该函数需要外部引用。 某些函数仅返回内部或外部引用。 例如，C API 函数 [xlfCaller](xlfcaller.md) 根据定义返回对当前工作表上调用单元格的引用。 返回的引用始终是内部引用，尽管该函数可以返回非引用类型，其中函数不是从工作表单元格调用的。 C API 函数 [xlSheetId](xlsheetid.md) 始终返回外部数据库类型中包含的引用数据 ID。 
  
内部和外部引用类型之间的另一个关键区别是，外部引用引用数据可以描述同一工作表上多个不脱节的单元格块。 内部引用只能描述当前工作表上的单个块。 脱节引用可以传递给任何采用 range 参数的函数。
  
## <a name="see-also"></a>另请参阅



[Excel 编程概念](excel-programming-concepts.md)
  
[求值名称和其他工作表公式表达式](evaluating-names-and-other-worksheet-formula-expressions.md)
  
[Excel 工作表和表达式计算](excel-worksheet-and-expression-evaluation.md)

