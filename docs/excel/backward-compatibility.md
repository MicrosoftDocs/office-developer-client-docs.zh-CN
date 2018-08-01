---
title: 向后兼容性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 版本兼容性 [excel 2007]，XLL 兼容性 [Excel 2007] 中，向后兼容性 [Excel 2007]
localization_priority: Normal
ms.assetid: ac200824-0620-4f03-8bd2-59226c1e79d7
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 095961fa909a67b354ed43a7e093b79a9ebb4f18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773640"
---
# <a name="backward-compatibility"></a>向后兼容性

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
本主题介绍 XLL 不同版本的 Microsoft Excel 中的兼容性的问题。
  
## <a name="useful-constant-definitions"></a>有用的常量定义

考虑包括定义类似于以下 XLL 项目代码和替换文本的数字，在此上下文中使用的所有实例中。 这将阐述特定于，版本的代码，并降低版本相关的外观无关紧要的数字形式的错误的可能性。
  
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

## <a name="getting-the-running-version"></a>获取运行的版本

您应该会检测到哪些版本是否正在运行使用`Excel4(xlfGetWorkspace, &amp;version, 1, &amp;arg)`，其中`arg`为数值型**XLOPER**设置为 2 和版本是一个字符串**XLOPER**然后可以强制为一个整数值。 对于 Microsoft Excel 2013，这是 15.0。 在中，或[xlAutoOpen](xlautoopen.md)函数中，您应这样做。 然后，您可以设置通知的所有模块正在运行哪个版本的 Excel 项目中的全局变量。 代码然后可以决定是否要调用的 C API 使用**Excel12**和**XLOPER12**s，或使用**Excel4**使用**XLOPER**s。
  
您可以调用**XLCallVer**发现 C API 版本中，但这并不表示其正在运行的 Excel 2007 版本。 
  
## <a name="creating-add-ins-that-export-dual-interfaces"></a>创建外接程序导出双重接口

请考虑采用的字符串，并返回一个值，它可以是任何工作表数据类型的 XLL 函数。 您无法导出键入"PD"注册和原型的函数，如下所示其中长度计数字节字符串形式传递的字符串。
  
`LPXLOPER WINAPI my_xll_fn(unsigned char *arg);`
  
尽管这非常好工作，但有以下几种原因这不是启动 Excel 2007 中代码的理想接口：
  
- 它受限制的 C API 字节字符串，并且无法访问 Excel 2007 中启动长 Unicode 字符串支持。
    
- 尽管从 Excel 2007 开始，Excel 可以传递和接受**XLOPER**s、 内部它将其转换为**XLOPER12**s，因此不存在的 Excel 的早期版本中的代码运行时的 Excel 2007 中启动隐式转换开销。
    
- 可能的此函数可线程安全的但如果字符串类型更改为`PD$`，在 Excel 2007 之前开始注册失败。
    
出于以上原因，理想情况下，在 Excel 2007 中启动应导出函数为用户的已注册为`QD%$`，假定您的代码线程安全和原型如下所示。
  
`LPXLOPER12 WINAPI my_xll_fn_v12(wchar_t *arg);`
  
为什么您可能要注册不同函数启动 Excel 2007 中的另一个原因是它还允许 XLL 函数带最多 255 个参数，而不是早期版本的 30 限制。
  
幸运的是，您可以同时按从您的项目导出两个版本的好处。 您可以然后检测正在运行的 Excel 版本，并有条件地注册最适当的函数。 有关详细信息和实现示例，请参阅[Developing 加载项 （xll （英文）） 在 Excel 2007 中](http://msdn.microsoft.com/en-us/library/aa730920.aspx)。
  
此方法会导致在 Excel 2003 中运行的工作表无法显示不同的结果运行启动 Excel 2007 中的同一工作表的可能性。 例如，Excel 2003 会将 Excel 2003 工作表单元格的 Unicode 字符串映射到 ASCII 字节字符串，然后截断它传递到 XLL 函数之前。 从 Excel 2007 开始，Excel 会将未转换的 Unicode 字符串传递给以正确的方式中注册的 XLL 函数。 这可能导致不同的结果。 您应注意这种可能性和后果给用户，而不仅仅是升级中。 例如，一些内置的数值函数进行了改进 Excel 2000 和 Excel 2003 之间。
  
## <a name="new-worksheet-functions-and-analysis-toolpak-functions"></a>新工作表函数和分析工具库函数

分析工具库 (ATP) 函数是启动 Excel 2007 中的 Excel 的一部分。 以前，XLL 仅可以使用[xlUDF](xludf.md)调用 ATP 函数。 从 Excel 2007 开始，ATP 函数应该调用使用 xlcall.h 中定义的函数枚举。 从 Dll 调用用户定义函数中的示例演示两个不同的方法。
  
## <a name="see-also"></a>另请参阅

- [C API 回调函数 Excel4、Excel12](c-api-callback-functions-excel4-excel12.md) 
- [�� Excel ��ʹ�� C API ���б��](programming-with-the-c-api-in-excel.md)
- [适用于 Excel 的 C API 中的新增功能](what-s-new-in-the-c-api-for-excel.md)

