---
title: Excel/Excel12f
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Excel12f
keywords:
- excel 函数 [excel 2007]，Excel12f 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 4e6a9ccc-988d-42a9-8874-01f2ee29b835
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f7ff6afac1737ee869e69fffd3dbed36a908b376
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431671"
---
# <a name="excelexcel12f"></a>Excel/Excel12f

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
框架库函数。 **Excel** [Excel4](excel4-excel12.md)函数的包装。 **Excel12f** 是 [Excel12](excel4-excel12.md) 函数的包装。 每个检查一次，发现没有任何参数为零，这表示创建临时 **XLOPER** 或 **XLOPER12** 失败。 如果发生错误，则每个代码都打印一条调试消息。 完成后，每个将释放可能为临时 XLOPER 和 **XLOPER12** s 创建的所有临时内存。 
  
 **Excel12f** 只能从从 Excel 2007 C API 库开始调用。 此外，它仅在从 2007 Excel运行时有效，否则使用 **xlretFailed** 失败。 
  
```cs
int Excel(int iFunction, LPXLOPER pxRes, int iCount, 
LPXLOPER argument1, ...);
int Excel12f(int iFunction, LPXLOPER12 pxRes, int iCount, 
LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a>参数

 _iFunction_ (**int)**
  
指示要调用的命令或函数的编号。 有关详细信息，请参阅[Excel4/Excel12。](excel4-excel12.md)
  
 _pxRes_
  
指向已计算函数结果的指针。 结果中指向的任何内存都将由 Excel 并且应在 [不再需要 xlFree](xlfree.md)时通过调用 xlFree 中释放，或者通过设置 **xlbitXLFree（** 如果返回到 Excel） 来释放。 
  
 _iCount_ (**int)**
  
将传递给函数的参数数。 从 2007 Excel起，限制为 255 个参数。 在早期版本中，限制为 30。
  
 _argument1， ..._
  
函数的可选参数。 所有参数必须为指向 **XLOPER** 的指针（如果为 **Excel）** 或 **XLOPER12** s（**对于 Excel12f）。**
  
## <a name="return-value"></a>返回值

这两个函数返回与 **Excel4、Excel4v、Excel12** 和 **Excel12v 相同的错误代码和成功代码**。   有关[这些代码的完整说明，请参阅 Excel4/Excel12。](excel4-excel12.md) 此外，如果检测到指向参数的 NULL 指针，这些 Framework 函数将返回 **xlretFailed，** 而不调用 C API。 
  
## <a name="example"></a>示例

此示例将错误参数传递给 **Excel12f** 函数，该函数向调试器发送消息。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI Excel12fExample(void)
{
    Excel12f(xlcDisplay, 0, 1, 0);
    return 1;
}
```

## <a name="see-also"></a>另请参阅



[Excel4/Excel12](excel4-excel12.md)


[框架库中的函数](functions-in-the-framework-library.md)

