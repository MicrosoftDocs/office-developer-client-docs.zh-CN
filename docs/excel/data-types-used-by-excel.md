---
title: Excel 使用的数据类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
keywords:
- 注册数据类型 [excel 2007],Excel 数据类型,字符串 [Excel 2007],数字 [Excel 2007],数据结构 [Excel 2007],数据类型 [Excel 2007]
ms.assetid: 8740a8fb-ad67-4232-a49b-d78967a786c2
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: c546fc80b212301689744d3279a59733d9cc5524
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310904"
---
# <a name="data-types-used-by-excel"></a>Excel 使用的数据类型

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 会交换多种 ANSI C/c ++ 类型，以及一些特定于 Excel 的数据结构。 本文介绍了这些内容，为其他部分提供上下文。有关详细信息，请参阅 [xlfRegister（窗体 1）](xlfregister-form-1.md)主题。 
  
## <a name="ansi-cc-types"></a>ANSI C/C++ 类型

### <a name="numbers"></a>数字

Excel 的所有版本：
  
- 8 字节双精度
    
- [signed] short [int] &ndash; 用于**布尔**值及整数 
    
- unsigned short [int]
    
- [signed long] int
    
### <a name="strings"></a>字符串

Excel 的所有版本：
  
- [signed] char \* &ndash; 最多包含 255 个字符的以 null 结尾的字节字符串
    
- unsigned char \* &ndash; 最多包含 255 个字符的长度计数型字节字符串
    
自 Excel 2007 起：
  
- unsigned short \* &ndash; 最多包含 32,767 个字符的 Unicode 字符串，可以是以 null 结尾的或长度计数型字符串
    
Excel 中的所有工作表数字均存储为双精度值，以便在与 Excel 交换整数类型时无需声明加载项函数（实际上这样产生了少量的转换开销）。
  
使用整数类型时，Excel 会验证输入是否在该类型的限制范围内，如果超出限制，则会失败并显示 **#NUM!** 。 注册采用使用 short int 实现的 **Boolean** 参数的函数时例外。在这种情况下，任何非零输入均转换为 1，并会直接传入零。 
  
## <a name="excel-specific-data-structures"></a>特定于 Excel 的数据结构

Excel 的所有版本：
  
- **FP** &ndash; 二维浮点数组结构，通过给定 Excel 版本支持的最大数字列数最多可支持 65,356 行。 
    
- **XLOPER** &ndash; 可表示所有工作表数据类型（包括错误）、整数、范围引用、XLM 宏工作表流控制类型和内部二进制存储数据类型的多类型数据结构。 
    
   > [!NOTE]
   > 字符串表示为最多包含 255 个字符的长度计数型字节字符串。 
  
自 Excel 2007 起：
  
- **FP12** &ndash; 自 Excel 2007 起支持所有行和列的二维浮点数组结构。 
    
- **XLOPER12** &ndash; 可表示所有工作表数据类型（包括错误）、整数、范围引用、XLM 宏工作表流控制类型和内部二进制存储数据类型的多类型数据结构。 
    
   > [!NOTE]
   > 字符串表示为最多包含 32,767 个字符的长度计数型 Unicode 字符串。 
  
## <a name="registration-data-type-codes"></a>注册数据类型代码

XLL 函数使用 C API 函数 **xlfRegister** 注册，该函数会将为返回类型和参数类型编码的字母字符串用作其第三个参数。 此字符串还包含用于告知 Excel 此函数是否具有以下特征的信息：可变、线程安全（自 Excel 2007 起）、等效于宏工作表、是否通过就地修改参数返回结果。
  
[xlfRegister（窗体 1）](xlfregister-form-1.md)主题复制了下表，并进行了详细介绍。 此处复制该表的目的在于为其他部分提供上下文。 例如，可以将采用长度计数型 Unicode 字符串（自 Excel 2007 起）的函数描述为采用 C% 类型的参数。 
  
|数据类型|按值传递|按引用传递（指针）|注释|
|:-----|:-----|:-----|:-----|
|Boolean  <br/> |A  <br/> |L  <br/> |short（0=false 或 1=true）  <br/> |
|double  <br/> |B  <br/> |E  <br/> ||
|char \*  <br/> ||C、F  <br/> |以 null 结尾的 ASCII 字节字符串  <br/> |
|unsigned char \*  <br/> ||D、G  <br/> |长度计数型 ASCII 字节字符串  <br/> |
|unsigned short \*（自 Excel 2007 起）  <br/> ||C%、F%  <br/> |以 null 结尾的 Unicode 宽字符字符串  <br/> |
|unsigned short \*（自 Excel 2007 起）  <br/> ||D%、G%  <br/> |长度计数型 Unicode 宽字符字符串  <br/> |
|unsigned short [int]  <br/> |H  <br/> ||WORD  <br/> |
|[signed] short [int]  <br/> |I  <br/> |M  <br/> |16 位  <br/> |
|[signed long] int  <br/> |J  <br/> |N  <br/> |32 位  <br/> |
|Array  <br/> ||O  <br/> | 按引用传递为三个参数：  <br/>1. short int \*行  <br/>2. short int \*列  <br/>3. double \*数组  <br/> |
|Array  <br/> （自 Excel 2007 起）  <br/> ||O%  <br/> | 按引用传递为三个参数：  <br/>1. int \*行  <br/>2. int \*列  <br/>3. double \*数组  <br/> |
|FP  <br/> ||K  <br/> |浮点数组结构  <br/> |
|FP12  <br/> （自 Excel 2007 起）  <br/> ||K%  <br/> |大型网格浮点数组结构  <br/> |
|XLOPER  <br/> ||P  <br/> |变量类型工作表值和数组  <br/> |
|||R  <br/> |值、数组和范围引用  <br/> |
|XLOPER12  <br/> （自 Excel 2007 起）  <br/> ||Q  <br/> |变量类型工作表值和数组  <br/> |
|||U  <br/> |值、数组和范围引用  <br/> |
   
下列类型均是 Microsoft Office Excel 2007 新增的类型，较旧版本中不支持这些类型：**C%**、**F%**、**D%**、**G%**、**K%**、**O%**、**Q** 和 **U**。 下列字符串类型用于就地修改的参数：**F**、**F%**、**G** 和 **G%**。 如果 **XLOPER** 或 **XLOPER12** 参数分别注册为 **P** 或 **Q** 类型，当 Excel 准备这些类型时，会将单个单元格引用转换为简单值，并将多单元格引用转换为数组。 
  
**P** 和 **Q** 类型始终作为下列类型之一引入函数：**xltypeNum**、**xltypeStr**、**xltypeBool**、**xltypeErr**、**xltypeMulti**、**xltypeMissing** 或 **xltypeNil**，但不会作为 **xltypeRef** 或 **xltypeSRef** 引入，因为始终会取消引用这些类型。 
  
类型 **O** 实际上是堆栈上的三个参数，是为了与 Fortran DLL 兼容而引入的，其中参数通过引用传递。 该类型不能用于返回值，除非将参数声明为就地修改返回值，并将结果置于引用值中。 **O%** 类型在 Excel 2007 中扩展 **O** 类型，使它可以访问范围大于 Office Excel 2003 网格的数组。 
  
## <a name="see-also"></a>另请参阅

- [xlfRegister（窗体 1）](xlfregister-form-1.md)
- [Excel 编程概念](excel-programming-concepts.md)
- [Excel XLL SDK API 函数引用](excel-xll-sdk-api-function-reference.md)

