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
- excel12v 函数 [excel 2007], Excel4v 函数 [excel 2007]
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
  
从 DLL、xll 或 code 资源中调用内部 Microsoft Excel 工作表函数、宏工作表函数或命令, 或仅 XLL 特殊函数或命令。
  
Excel 的所有最新版本都支持**Excel4v**。 从 Excel 2007 开始, 支持**Excel12v** 。 
  
只有当 Excel 已将控制传递给 DLL 或 XLL 时, 才能调用这些函数。 当 Excel 通过对 Visual Basic for Applications (VBA) 的调用间接传递控制时, 也可以调用它们。 任何时候都不能调用它们。 例如, 在调用 DllMain 函数期间或其他操作系统调用 dll 的线程或由 DLL 创建的线程中, 不能调用这些函数。 
  
[Excel4 和 Excel12](excel4-excel12.md)函数接受其参数作为堆栈上的可变长度列表, 而**Excel4v**和**Excel12v**函数接受其参数作为数组。 在所有其他方面, **Excel4**的行为与**Excel4v**相同, **Excel12**的行为与**Excel12v**相同。
  
```cs
int _cdecl Excel4v(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER rgx[]);
int _cdecl Excel12v(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 rgx[]);
```

## <a name="parameters"></a>参数

 _iFunction_(**int**)
  
一个数字, 指示要调用的命令、函数或特殊函数。 有关有效_iFunction_值的列表, 请参阅以下备注部分。 
  
 _pxRes_(**LPXLOPER**或**LPXLOPER12**)
  
指向**XLOPER** (在**Excel4v**中) 或**XLOPER12** (在**Excel12v**中) 的指针, 它将包含计算函数的结果。
  
 _iCount_(**int**)
  
将传递给函数的后续参数的数目。 在 Excel 的 Excel 版本中, 最多为2003。这可以是0到30之间的任意数字。 从 Excel 2007 开始, 可以是0到255之间的任意数字。
  
 _rgx_(**LPXLOPER []** 或**LPXLOPER12 []**)
  
包含函数的参数的数组。 数组中的所有参数都必须是指向**XLOPER**或**XLOPER12**值的指针。 
  
## <a name="return-value"></a>返回值

这些函数返回的值与**Excel4**和**Excel12**的值相同。
  
## <a name="remarks"></a>说明

这些函数在传递给运算符的参数数目为可变时非常有用。 例如, 在使用[xlfRegister](xlfregister-form-1.md)注册函数时, **Excel4v**和**Excel12v**是很有用的, 其中 total 参数的数目取决于所注册的函数所执行的参数数量。 当您为**Excel4**或**Excel12**编写包装函数时, **Excel4v**和**Excel12v**也很有用。 在这些情况下, 您需要将变量参数列表 (通常为**Excel4**或**Excel12**提供) 转换为使用**Excel4v**或**Excel12v**回调到 Excel 中的单个数组参数的变量大小。
  
### <a name="example"></a>示例

有关代码示例, 请参阅 excel 2010 XLL SDK 中的**excel**和**Excel12f**函数代码, 该 sdk 的安装位置如下所示: 
  
Samples\Framewrk\Framewrk。c
  
## <a name="see-also"></a>另请参阅



[Excel4/Excel12](excel4-excel12.md)

