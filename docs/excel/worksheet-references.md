---
title: 工作表引用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 引用 [excel 2007], 工作表, 工作表引用 [excel 2007], 外部工作表引用 [excel 2007], 活动工作表 [excel 2007], 当前工作表 [excel 2007], 内部工作表引用 [excel 2007]
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
  
Microsoft Excel 中的引用是指矩形单元格块 (可以只是一个单元格) 的数据类型, 或者在某些情况下, 许多不连续的单元格块。 在内部, Excel 将对当前工作表上的单元格使用一种引用类型, 称为 "内部引用"。 不在当前工作表上的任何单元格由称为外部引用的另一种引用类型进行描述。 有关 active 和 current 的定义, 请参阅下一节。
  
## <a name="active-vs-current"></a>活动与当前

在 Excel 中, 术语 "活动" 表示用户正在查看的内容。 当前工作簿和工作表是用户当前正在查看的工作簿和工作表, 或者, 如果 excel 失去焦点到另一个应用程序, 则查看 excel 上次获得焦点的时间。 活动工作表始终在活动工作簿中。 在活动工作表中选择的一个或多个单元格称为活动单元格。 如果嵌入对象有焦点, 则最后选定的单元格仍处于活动状态。 
  
术语 current 指 Excel 要重新计算的内容。 当前的工作簿和工作表是当前正在重新计算的工作簿和工作表。 当前工作表始终在当前工作簿中。 要重新计算的单元格称为当前单元格, 或者, 如果要重新计算数组公式, 则为当前单元格。 
  
要记住的要点如下:
  
- 当前的工作簿/工作表/单元格通常不是当前工作簿/工作表/单元格, 但也是如此。
    
- 加载项函数 (无论是在 Visual Basic for Applications (VBA) 模块中还是在 DLL 或 XLL 中) 总是从当前工作表上的当前单元格调用, 或者是在多线程重新计算 (MTR) 的情况下调用其中的一个。
    
许多 Excel 函数, 提供有关单元格、单元格区域或工作簿中的工作表的信息区分活动工作簿、工作表或单元格与当前工作簿、工作表或单元格。 此差异反映在用于描述对单元格块的引用的数据类型中, 如下一节中所述。
  
## <a name="internal-and-external-worksheet-references"></a>内部和外部工作表引用

内部引用和外部引用的主要区别是外部引用数据类型包含工作表的 ID, 也是对单元格所引用的说明。 内部引用不包含对工作表的引用—它是隐式的工作表是当前工作表。 
  
许多 C API 函数返回引用或获取引用参数。 任何采用引用参数的 C API 函数都可接受内部引用或外部引用, 但**xlSheetNm**函数除外, 它需要外部引用。 某些函数仅返回内部或外部引用。 例如, C API 函数[xlfCaller](xlfcaller.md)按定义返回对当前工作表上的调用单元格的引用。 返回的引用始终是内部引用, 尽管函数可以返回不是从工作表单元格中调用函数的非引用类型。 C API 函数[xlSheetId](xlsheetid.md)始终返回包含在外部引用数据类型中的工作表的 ID。 
  
内部和外部引用类型之间的其他关键区别在于外部引用数据类型可以在同一工作表上描述多个脱节的单元格块。 内部引用只能描述当前工作表上的一个块。 不连续引用可传递给采用 range 参数的任何函数。
  
## <a name="see-also"></a>另请参阅



[Excel 编程概念](excel-programming-concepts.md)
  
[求值名称和其他工作表公式表达式](evaluating-names-and-other-worksheet-formula-expressions.md)
  
[Excel 工作表和表达式计算](excel-worksheet-and-expression-evaluation.md)

