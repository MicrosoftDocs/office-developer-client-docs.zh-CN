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
- excel12v 函数 [excel 2007]，Excel4v 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: e3e96b98-c5a7-4625-95b6-a1e2d09c6d3d
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 11ab86a95dde2ad52840822b28ce4d74dd05d148
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414989"
---
# <a name="excel4vexcel12v"></a>Excel4v/Excel12v

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
从 DLL、Microsoft Excel或代码资源中调用内部工作表函数、宏工作表函数或命令或仅 XLL 的特殊函数或命令。
  
所有最新版本的 Excel都支持 **Excel4v。** 从 2007 Excel开始，**支持 Excel12v。** 
  
只有在将控件传递给 DLL Excel XLL 时，才能调用这些函数。 当通过调用 VBA Excel间接传递控制权时，也可以Visual Basic for Applications (这些) 。 无法在其他时间调用它们。 例如，在调用 DllMain 函数期间或操作系统调用 DLL 时的其他时间，或者从 DLL 创建的线程调用它们时，无法调用它们。 
  
[Excel4 和 Excel12](excel4-excel12.md)函数接受其参数作为堆栈上的可变长度列表，而 **Excel4v** 和 **Excel12v** 函数接受其参数作为数组。 在所有其他方面 **，Excel4** 的行为与 **Excel4v** 相同， **而 Excel12** 的行为与 **Excel12v 相同**。
  
```cs
int _cdecl Excel4v(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER rgx[]);
int _cdecl Excel12v(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 rgx[]);
```

## <a name="parameters"></a>参数

 _iFunction_ (**int)**
  
指示要调用的命令、函数或特殊函数的编号。 有关有效  _iFunction_ 值的列表，请参阅以下"备注"部分。 
  
 _pxRes_ (**LPXLOPER** 或 **LPXLOPER12**) 
  
一个指向 **XLOPER** (（对于 **Excel4v**) ）或 **XLOPER12** (（对于 **Excel12v**) 将保存计算函数的结果）。
  
 _iCount_ (**int)**
  
将传递给函数的后续参数的数量。 在 Excel 2003 版本中，它可以是 0 到 30 的任何数字。 从 Excel 2007 开始，可以是从 0 到 255 的任何数字。
  
 _rgx_ (**LPXLOPER []** 或 **LPXLOPER12 [])**
  
包含函数参数的数组。 数组中所有参数都必须是指向 **XLOPER** 或 **XLOPER12** 值的指针。 
  
## <a name="return-value"></a>返回值

这些函数返回与 **Excel4** 和 **Excel12** 相同的值。
  
## <a name="remarks"></a>备注

当传递给运算符的参数数目为变量时，这些函数非常有用。 例如，在使用 [xlfRegister](xlfregister-form-1.md)注册函数时 **，Excel4v** 和 **Excel12v** 非常有用，其中总参数数取决于注册的函数所采用参数的数量。 **编写 Excel4** 或 **Excel12** 的包装函数时 **，Excel4v** 和 **Excel12v 也很有用**。 在这些情况下，您需要将变量参数列表（通常提供给 **Excel4** 或 **Excel12）** 转换为变量大小的单个数组参数，以使用 **Excel4v** 或 **Excel12v** 调用回 Excel。
  
### <a name="example"></a>示例

有关代码示例，请参阅安装 SDK的以下位置的 Excel 2010 XLL SDK 中的 Excel 和 **Excel12f** 函数的代码： 
  
Samples\Framewrk\Framewrk.c
  
## <a name="see-also"></a>另请参阅



[Excel4/Excel12](excel4-excel12.md)

