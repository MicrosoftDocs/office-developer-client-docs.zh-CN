---
title: 向后兼容性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- version compatibility [excel 2007]，XLL compatibility [Excel 2007]，backward compatibility [Excel 2007]
localization_priority: Normal
ms.assetid: ac200824-0620-4f03-8bd2-59226c1e79d7
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3e1368ef55b96be947527456e0f01918afec6663
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301678"
---
# <a name="backward-compatibility"></a>向后兼容性

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
本主题解决不同版本的 Microsoft Excel 中的 XLL 兼容性问题。
  
## <a name="useful-constant-definitions"></a>有用的常量定义

请考虑在 XLL 项目代码中包含与这些类似的定义，并替换此上下文中使用文字编号的所有实例。 这将阐明特定于版本的代码，并减少与版本相关的错误的可能性，形式为不一样的数字。
  
```cpp
#define MAX_XL11_ROWS            65536
#define MAX_XL11_COLS              256
#define MAX_XL12_ROWS          1048576
#define MAX_XL12_COLS            16384
#define MAX_XL11_UDF_ARGS           30
#define MAX_XL12_UDF_ARGS          255
#define MAX_XL4_STR_LEN           255u
#define MAX_XL12_STR_LEN        32767u
```

## <a name="getting-the-running-version"></a>获取正在运行的版本

应检测使用 运行的版本，其中 是设置为 2 的数字  `Excel4(xlfGetWorkspace, &amp;version, 1, &amp;arg)`  `arg` **XLOPER，version** 是字符串 **XLOPER，** 然后可以强制转换为整数。 对于 Microsoft Excel 2013，这是 15.0。 应在 xlAutoOpen 函数中或从 [xlAutoOpen 函数中执行](xlautoopen.md) 此操作。 然后，您可以设置一个全局变量，该变量通知项目中的所有模块正在运行哪个版本的 Excel。 然后，代码可以决定是使用 **Excel12** 和 **XLOPER12** 调用 C API，还是使用 **XLOPER** s 使用 **Excel4。**
  
您可以调用 **XLCallVer** 来发现 C API 版本，但这并不意味着您运行的是 Excel 2007 之前的版本。 
  
## <a name="creating-add-ins-that-export-dual-interfaces"></a>创建导出双接口的外接程序

请考虑一个 XLL 函数，该函数接受一个字符串并返回一个可以是任何工作表数据类型的值。 您可以导出注册为类型"PD"的函数，并按如下方式建立原型，其中字符串作为长度计数字节字符串传递。
  
`LPXLOPER WINAPI my_xll_fn(unsigned char *arg);`
  
尽管这运行良好，但有几个原因导致这不是从 Excel 2007 开始的代码的理想接口：
  
- 它受 C API 字节字符串的限制，无法访问自 Excel 2007 起支持的长 Unicode 字符串。
    
- 尽管从 Excel 2007 开始，Excel 可以传递和接受 **XLOPER，** 但它在内部会将其转换为 **XLOPER12，** 因此从 Excel 2007 开始存在隐式转换开销，当代码在早期版本的 Excel 中运行时，不存在此开销。
    
- 此函数可能是使线程安全函数，但如果类型字符串更改为 ，在  `PD$` Excel 2007 之前注册将失败。
    
出于这些原因，理想情况下，从 Excel 2007 开始，您应该为注册为 的用户导出函数，假定您的代码是线程安全的，并按如下所示  `QD%$` 进行原型制作。
  
`LPXLOPER12 WINAPI my_xll_fn_v12(wchar_t *arg);`
  
您可能想要从 Excel 2007 开始注册其他函数的另一个原因是，它允许 XLL 函数最多使用 255 个参数，而不是早期版本的 30 个限制。
  
幸运的是，通过从项目中导出这两个版本，您可以同时获得这两个优势。 然后，您可以检测正在运行的 Excel 版本，并按条件注册最合适的函数。 有关详细信息和示例实现，请参阅 Developing [Add-ins (XLL) in Excel 2007。](https://msdn.microsoft.com/library/aa730920.aspx)
  
此方法导致在 Excel 2003 中运行的工作表显示的结果可能不同于从 Excel 2007 开始运行的同一工作表的结果。 例如，Excel 2003 将 Excel 2003 工作表单元格中的 Unicode 字符串映射到 ASCII 字节字符串，并在将字符串传递给 XLL 函数之前截断该字符串。 从 Excel 2007 开始，Excel 将反向 Unicode 字符串传递给以正确方式注册的 XLL 函数。 这可能会导致不同的结果。 您应该了解此可能性以及给用户的后果，而不只是在升级过程中。 例如，在 Excel 2000 和 Excel 2003 之间改进了一些内置数值函数。
  
## <a name="new-worksheet-functions-and-analysis-toolpak-functions"></a>新的工作表函数和分析工具库函数

分析工具库 (ATP) 函数是自 Excel 2007 起 Excel 的一部分。 以前，XLL 只能使用 [xlUDF](xludf.md)调用 ATP 函数。 从 Excel 2007 开始，应该使用 xlcall.h 中定义的函数枚举来调用 ATP 函数。 从 DLL 调用用户定义函数中的示例演示了两种不同的方法。
  
## <a name="see-also"></a>另请参阅

- [C API 回调函数 Excel4、Excel12](c-api-callback-functions-excel4-excel12.md) 
- [在 Excel 中使用 C API 进行编程](programming-with-the-c-api-in-excel.md)
- [适用于 Excel 的 C API 中的新增功能](what-s-new-in-the-c-api-for-excel.md)

