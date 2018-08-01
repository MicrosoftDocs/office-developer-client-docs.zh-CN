---
title: 使用 Excel 数据类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
keywords:
- 注册数据类型 [excel 2007]，Excel 数据类型、 [Excel 2007] 的字符串、 数字 [Excel 2007]、 数据结构 [Excel 2007]，数据类型 [Excel 2007]
localization_priority: Normal
ms.assetid: 8740a8fb-ad67-4232-a49b-d78967a786c2
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: b32a9beb2f77c12e6b6f2c445672c717a2546386
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773648"
---
# <a name="data-types-used-by-excel"></a>使用 Excel 数据类型

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 交换几种 ANSI C/c + + 类型和还某些特定于 Excel 的数据结构。 这些此处提及的其他部分中，提供上下文和[xlfRegister (窗体 1)](xlfregister-form-1.md)主题中详细讨论了它们。 
  
## <a name="ansi-cc-types"></a>ANSI C/c + + 类型

### <a name="numbers"></a>����

所有版本的 Excel 中：
  
- 8 字节双精度值
    
- [签名] short [int]&ndash;用于**布尔**值和还整数 
    
- 无符号的 short [int]
    
- [签名长] int
    
### <a name="strings"></a>字符串

所有版本的 Excel 中：
  
- [签名] char \* &ndash; null 结尾的字节的最多 255 个字符的字符串
    
- 未签署的 char \* &ndash;最多 255 个字符的长度计数字节字符串
    
启动 Excel 2007 中：
  
- 未签署的短\*&ndash;达 32,767 个字符，可以是 null 结尾或长度计数的 Unicode 字符串
    
在 Excel 中的所有工作表号码存储为双精度型值，以使它不需要 （和实际上引入了小型转换开销） 声明作为交换整数类型，通过 Excel 外接程序函数。
  
如果您使用的整数类型，Excel 验证的输入中的类型，限制是，且它们失败并出现 **#NUM ！** 如果这些外部。 您要注册才能使用短 int。 实现一个**布尔**参数的函数时除外在这种情况下，任何非零输入将转换为 1，并直接通过传递零。 
  
## <a name="excel-specific-data-structures"></a>特定于 Excel 的数据结构

所有版本的 Excel 中：
  
- **FP**&ndash;由在给定的 Excel 版本中受支持的最大数字列支持多达包含 65356 行的二维浮点数组结构。 
    
- **XLOPER**&ndash; （包括错误） 的所有工作表数据类型、 整数、 区域引用、 XLM 宏工作表流控件类型和内部二进制存储数据类型可以表示多类型数据结构。 
    
   > [!NOTE]
   > 字符串长度计数字节的最多 255 个字符长度的字符串表示。 
  
启动 Excel 2007 中：
  
- **FP12**&ndash;支持所有的行和列开始在 Excel 2007 中的二维浮点数组结构。 
    
- **XLOPER12**&ndash; （包括错误） 的所有工作表数据类型、 整数、 区域引用、 XLM 宏工作表流控件类型和内部二进制存储数据类型可以表示多类型数据结构。 
    
   > [!NOTE]
   > 字符串表示作为计算长度在内的长达 32,767 个字符的 Unicode 字符串。 
  
## <a name="registration-data-type-codes"></a>注册数据类型代码

使用 C API 函数**xlfRegister**，它采用作为其第三个参数返回和参数的类型编码的字母字符串注册 XLL 函数。 此字符串还包含告诉 Excel 可变函数是否是线程安全 （在 Excel 2007 中从开始）、 是等效的宏工作表的信息并是否返回其结果通过修改就地参数。
  
下表是复制并[xlfRegister (窗体 1)](xlfregister-form-1.md)主题中的更详细地讨论。 被复制此处以便为本节的其余部分提供上下文。 例如，采用的长度计数的 Unicode 字符串 （在 Excel 2007 中从开始） 函数无法描述为采用 C %参数的类型。 
  
|数据类型|按值传递|Ref （指针） 通过传递|注释|
|:-----|:-----|:-----|:-----|
|Boolean  <br/> |A  <br/> |L  <br/> |短 (0 = false 或 1 = true)  <br/> |
|double  <br/> |B  <br/> |E  <br/> ||
|char\*  <br/> ||C F  <br/> |Null 结尾的 ASCII 字节字符串  <br/> |
|无符号的字符\*  <br/> ||D、 G  <br/> |长度-计数 ASCII 字节字符串  <br/> |
|未签署的短\*（在 Excel 2007 中从开始）  <br/> ||C %，F %  <br/> |Null 结尾的 Unicode 宽字符字符串  <br/> |
|未签署的短\*（在 Excel 2007 中从开始）  <br/> ||D %，G %  <br/> |长度计数 Unicode 宽字符字符串  <br/> |
|无符号的 short [int]  <br/> |H  <br/> ||WORD  <br/> |
|[签名] short [int]  <br/> |I  <br/> |M  <br/> |16 位  <br/> |
|[签名长] int  <br/> |J  <br/> |N  <br/> |32 位  <br/> |
|数组  <br/> ||O  <br/> | 通过引用作为三个参数传递：  <br/>1.短 int\*行  <br/>2.短 int\*列  <br/>3.double\*数组  <br/> |
|数组  <br/> （在 Excel 2007 中从开始）  <br/> ||O %  <br/> | 通过引用作为三个参数传递：  <br/>1.int\*行  <br/>2.int\*列  <br/>3.double\*数组  <br/> |
|FP  <br/> ||K  <br/> |浮点数组结构  <br/> |
|FP12  <br/> （在 Excel 2007 中从开始）  <br/> ||K %  <br/> |大网格浮点数组结构  <br/> |
|XLOPER  <br/> ||P  <br/> |变量类型工作表值和阵列  <br/> |
|||R  <br/> |值、 数组和区域引用  <br/> |
|XLOPER12  <br/> （在 Excel 2007 中从开始）  <br/> ||Q  <br/> |变量类型工作表值和阵列  <br/> |
|||U  <br/> |值、 数组和区域引用  <br/> |
   
类型**C %**、 **F %**、 **D %**、 **G %**、 **K %**、 **O %**、 **Q**、 和**U**了 Microsoft Office Excel 2007 中的所有新和不支持早期版本中。 **F**、 **F %**、 **G**、 和**G %** 的字符串类型用于修改就地的参数。 时**XLOPER**或**XLOPER12**参数分别注册为**P**或**Q**的类型，Excel 就会转换简单值的单个单元格引用和数组的多单元格引用时它准备它们。 
  
**P**和**Q**类型始终进入您函数为以下类型之一： **xltypeNum**、 **xltypeStr**、 **xltypeBool**、 **xltypeErr**、 **xltypeMulti**、 **xltypeMissing**或**xltypeNil**，但不**xltypeRef**或**xltypeSRef**因为这些始终取消引用。 
  
类型**O**，实际上是在堆栈上的三个参数，引入了与 Fortran Dll 的引用传递的参数的兼容性。 它不能用于通过声明作为修改就地返回值参数并将结果放中引用的值返回除值。 键入 **%o%** 扩展 Excel 2007 中的**O**类型，以便它可以访问覆盖区域大于 Office Excel 2003 网格的数组。 
  
## <a name="see-also"></a>另请参阅

- [xlfRegister（窗体 1）](xlfregister-form-1.md)
- [Excel Programming Concepts](excel-programming-concepts.md)
- [Excel XLL SDK API Function Reference](excel-xll-sdk-api-function-reference.md)

