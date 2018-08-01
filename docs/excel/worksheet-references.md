---
title: 工作表引用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 引用 [excel 2007]、 工作表、 工作表引用 [Excel 2007]、 外部工作表引用 [Excel 2007]、 活动工作表 [Excel 2007]、 当前工作表 [Excel 2007]、 内部的工作表引用 [Excel 2007]
localization_priority: Normal
ms.assetid: 53406fb8-4ca5-4204-a6ad-b21ca9e6a100
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: b7089fb891c96be9182189e3a5f30057721cebbc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773835"
---
# <a name="worksheet-references"></a>工作表引用

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 中的引用是指的矩形块的单元格 （它可能只有一个单元格），或在某些情况下，非连续单元格块大量数据类型。 内部，Excel 将使用一个引用类型称为内部引用当前的工作表上的单元格。 不在当前工作表的任意单元格被描述另一种称为外部引用的引用。 请参阅定义活动和当前的下一节。
  
## <a name="active-vs-current"></a>与当前活动

在 Excel 中，用户正在查看指活动的术语。 活动工作簿和工作表是那些用户当前看，或已查看 Excel 已丢失焦点移到另一个应用程序，如果 Excel 最后一个具有焦点。 活动工作表始终是活动工作簿中。 活动工作表中所选的一个或多个单元格称为活动单元格。 嵌入的对象具有焦点，最后一次选定单元格仍处于活动状态。 
  
Excel 正在重新计算引用当前的术语。 当前工作簿和工作表是那些当前正在重新计算。 当前工作表始终是当前工作簿中。 正在重新计算的单元格称为作为当前单元格，或者，对于数组公式重新计算，当前的单元格。 
  
要记住的要点如下所示：
  
- 活动工作簿/工作表/单元格不是通常当前，但它可以是。
    
- 外接程序，无论在 Visual Basic for Applications (VBA) 模块或 DLL 或 XLL，始终从调用函数当前单元格上当前工作表，或对于多线程重新计算 (MTR) 两者之一。
    
提供有关单元格、 单元格区域或工作簿中的工作表信息的许多 Excel 函数区分活动工作簿、 工作表，或单元格和当前工作簿、 工作表或单元格。 这种差异会反映在用来描述引用单元格，块中下一节所述的数据类型。
  
## <a name="internal-and-external-worksheet-references"></a>内部和外部工作表引用

内部和外部引用之间的主要区别是外部引用数据类型包含工作表以及说明的单元格的引用的 ID。 内部参考包含对工作表不引用 — 它是隐式工作表是当前工作表。 
  
许多 C API 函数返回引用或带引用参数。 考虑引用参数任何 C API 函数接受内部或外部的引用，除**xlSheetNm**函数，这需要外部引用。 某些功能仅返回内部或外部的引用。 例如，C API 函数[xlfCaller](xlfcaller.md)返回引用调用单元格中，根据定义，当前工作表上。 返回的引用始终是内部的引用，但该函数可以返回非引用类型，函数将不调用从工作表单元格。 C API 函数[xlSheetId](xlsheetid.md)始终返回外部引用数据类型中包含的工作表的 ID。 
  
其他关键区别之间的内部和外部引用类型是外部引用数据类型可以描述在同一工作表上的多个非连续单元格块。 内部引用可以在当前工作表上描述单个块。 可以采用范围参数任何函数传递脱节的引用。
  
## <a name="see-also"></a>另请参阅



[Excel Programming Concepts](excel-programming-concepts.md)
  
[Evaluating Names and Other Worksheet Formula Expressions](evaluating-names-and-other-worksheet-formula-expressions.md)
  
[Excel 工作表和表达式计算](excel-worksheet-and-expression-evaluation.md)

