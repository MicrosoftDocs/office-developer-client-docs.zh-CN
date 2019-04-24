---
title: 向后兼容性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 版本兼容性 [excel 2007], XLL 兼容性 [excel 2007], 向后兼容性 [excel 2007]
localization_priority: Normal
ms.assetid: ac200824-0620-4f03-8bd2-59226c1e79d7
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3e1368ef55b96be947527456e0f01918afec6663
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301678"
---
# <a name="backward-compatibility"></a>向后兼容性

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
本主题解决不同版本的 Microsoft Excel 中的 XLL 兼容性问题。
  
## <a name="useful-constant-definitions"></a>有用的常量定义

请考虑在 XLL 项目代码中包括与以下内容类似的定义, 并替换此上下文中使用的文本编号的所有实例。 这将阐明特定于版本的代码, 并以看似无害的数字的形式降低与版本相关的 bug 的可能性。
  
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

应`Excel4(xlfGetWorkspace, &amp;version, 1, &amp;arg)`检测使用哪个版本正在运行, `arg`其中是将数值**XLOPER**设置为 2, 版本是字符串**XLOPER** , 然后可以将该字符串强制转换为整数。 对于 Microsoft Excel 2013, 此为15.0。 应在[xlAutoOpen](xlautoopen.md)函数中执行此操作。 然后, 您可以设置一个全局变量, 用于通知项目中的所有模块运行的是哪个版本的 Excel。 然后, 您的代码可以决定是使用**Excel12**和**XLOPER12**s 调用 C API, 还是使用**XLOPER**s 调用**Excel4** 。
  
您可以调用**XLCallVer**来发现 C API 版本, 但这并不表示运行的是 Excel 的前2007版本中的哪一个。 
  
## <a name="creating-add-ins-that-export-dual-interfaces"></a>创建导出双重接口的外接程序

考虑使用一个字符串的 XLL 函数, 并返回一个可以是任何工作表数据类型的值。 您可以导出注册为类型 "PD" 和 "原型" 的函数, 如下所示, 在将字符串作为长度计数的字节字符串传递。
  
`LPXLOPER WINAPI my_xll_fn(unsigned char *arg);`
  
虽然这非常有效, 但在 Excel 2007 中, 这并不是您的代码的理想界面的原因有以下几个:
  
- 它受 C API 字节字符串限制的限制, 无法访问在 Excel 2007 中开始支持的长 Unicode 字符串。
    
- [! 注意] 在 excel 2007 中, excel 可以传递和接受**XLOPER**s, 在内部它会将它们转换为**XLOPER12**s, 因此在 excel 2007 中, 在 excel 的早期版本中运行时, 不会出现从 excel 中开始的隐式转换开销。
    
- 可以使此函数成为线程安全的, 但如果类型字符串已更改为`PD$`, 则注册将在 Excel 2007 之前的启动过程中失败。
    
出于这些原因, 理想情况下, 从 Excel 2007 开始, 应导出注册为`QD%$`的用户的函数, 假定您的代码是线程安全和原型, 如下所示。
  
`LPXLOPER12 WINAPI my_xll_fn_v12(wchar_t *arg);`
  
您可能想要在 Excel 2007 中开始注册不同函数的另一个原因是, 它允许 XLL 函数最长为255个参数, 而不是较早版本的30个限制。
  
幸运的是, 可以通过从项目中导出这两个版本来获得这两个版本的好处。 然后, 您可以检测正在运行的 Excel 版本, 并有条件地注册最合适的函数。 有关详细信息和示例实现, 请参阅[在 Excel 2007 中开发外接程序 (xll)](https://msdn.microsoft.com/library/aa730920.aspx)。
  
此方法使运行在 excel 2003 中的工作表显示的结果可能与运行在 excel 2007 中的同一工作表显示不同的结果。 例如, excel 2003 会将 excel 2003 工作表单元格中的 Unicode 字符串映射为 ASCII 字节字符串, 并在将其传递给 XLL 函数之前将其截断。 从 excel 2007 开始, excel 会将未转换的 Unicode 字符串传递给以正确方式注册的 XLL 函数。 这可能会导致不同的结果。 您应了解这种可能性以及对用户产生的后果, 而不只是在升级中。 例如, 在 excel 2000 和 excel 2003 之间改进了一些内置数值函数。
  
## <a name="new-worksheet-functions-and-analysis-toolpak-functions"></a>新的工作表函数和分析工具库函数

分析工具库 (ATP) 函数是 excel 2007 中启动的 excel 的一部分。 以前, XLL 只能通过使用[xlUDF](xludf.md)调用 ATP 函数。 从 Excel 2007 开始, 应使用 xlcall.h 中定义的函数枚举调用 ATP 函数。 从 dll 调用用户定义的函数的示例演示了两种不同的方法。
  
## <a name="see-also"></a>另请参阅

- [C API 回调函数 Excel4、Excel12](c-api-callback-functions-excel4-excel12.md) 
- [在 Excel 中使用 C API 进行编程](programming-with-the-c-api-in-excel.md)
- [适用于 Excel 的 C API 中的新增功能](what-s-new-in-the-c-api-for-excel.md)

