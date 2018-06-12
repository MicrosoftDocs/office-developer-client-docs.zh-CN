---
title: Excel4v/Excel12v
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Excel12v
- Excel4v
keywords:
- excel12v 函数 [excel 2007，] Excel4v 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: e3e96b98-c5a7-4625-95b6-a1e2d09c6d3d
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 7ffa0bc3ae6222af1ecd7f65de66d026ea178c87
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773751"
---
# <a name="excel4vexcel12v"></a>Excel4v/Excel12v

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
内部 Microsoft Excel 工作表函数、 宏工作表函数或命令或仅 XLL 特殊函数或命令，从调用 DLL，XLL 或代码资源中。
  
所有的最新版本的 Excel 支持**Excel4v**。 从 Excel 2007 开始，支持**Excel12v** 。 
  
仅当 Excel 已传递给 DLL 或 XLL 的控件时，可调用这些函数。 他们也称为 Excel 过后控件间接通过调用 Visual Basic for Applications (VBA)。 他们不能在其他任何时间调用。 例如，他们不能为 DllMain 函数或其他时间操作系统时呼叫 dll 文件，或从由 DLL 中创建的线程在呼叫过程中调用。 
  
[Excel4 和 Excel12](excel4-excel12.md)函数接受及其参数为堆栈上, 长度可变列表，而**Excel4v**和**Excel12v**函数接受其参数作为数组。 在所有其他方面， **Excel4** **Excel4v**，相同的行为和**Excel12**行为与**Excel12v**相同。
  
```cs
int _cdecl Excel4v(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER rgx[]);
int _cdecl Excel12v(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 rgx[]);
```

## <a name="parameters"></a>参数

 _iFunction_(**int**)
  
一个数字，指示命令、 函数或您要呼叫的特殊函数。 有效_iFunction_值的列表，请参阅下的备注部分。 
  
 _pxRes_（**LPXLOPER**或**LPXLOPER12**）
  
一个指向 （对于**Excel4v**) **XLOPER**或**XLOPER12** （对于**Excel12v**) 将保存计算函数的结果。
  
 _iCount_(**int**)
  
将传递给函数的后续参数的数目。 Excel 2003 最版本中可以是介于 0 到 30 任何号码。 从 Excel 2007 开始，这可以是任何介于 0 到 255。
  
 _rgx_（**LPXLOPER []** 或**LPXLOPER12 []**）
  
一个数组，包含对函数的参数。 该数组中的所有参数都必须为**XLOPER**或**XLOPER12**值的指针。 
  
## <a name="return-value"></a>返回值

这些函数返回**Excel4**和**Excel12**相同的值。
  
## <a name="remarks"></a>备注

其中的参数传递给运算符数目为变量，这些函数很有用。 例如， **Excel4v**和**Excel12v**很有用时使用其中的总参数数目取决于所要所注册的函数的参数数目[xlfRegister](xlfregister-form-1.md)注册函数。 **Excel4v**和**Excel12v**也是有用时**Excel4**或**Excel12**编写一个包装函数。 在这些情况下，您需要转换变量参数列表中，通常会提供给变量的大小以回调到 Excel 使用**Excel4v**或**Excel12v**的单个数组参数为**Excel4**或**Excel12**，如。
  
### <a name="example"></a>示例

代码示例，请参阅 Excel 2010 XLL SDK 安装 SDK 的以下位置中的**Excel**和**Excel12f**函数的代码： 
  
Samples\Framewrk\Framewrk.c
  
## <a name="see-also"></a>另请参阅



[Excel4/Excel12](excel4-excel12.md)

