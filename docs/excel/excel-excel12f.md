---
title: Excel/Excel12f
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Excel12f
keywords:
- excel 函数 [excel 2007，] Excel12f 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 4e6a9ccc-988d-42a9-8874-01f2ee29b835
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 56034984852713496465c3d1f79a9989fc47df1c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773678"
---
# <a name="excelexcel12f"></a>Excel/Excel12f

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Framework 库函数。 **Excel**是[Excel4](excel4-excel12.md)函数的包装。 **Excel12f**是[Excel12](excel4-excel12.md)函数的包装。 每个检查所有参数为零，这将指示创建临时**XLOPER**或**XLOPER12**失败。 如果出现错误，每打印调试消息。 完成后，每个释放可能已创建的临时**XLOPER**s 和**XLOPER12**s 的所有临时内存。
  
 只能从 DLL 启动与 Excel 2007 C API 库调用**Excel12f** 。 此外，它仅适用于运行 Excel 2007 中，从开始时，操作失败**xlretFailed** ，否则。 
  
```cs
int Excel(int iFunction, LPXLOPER pxRes, int iCount, 
LPXLOPER argument1, ...);
int Excel12f(int iFunction, LPXLOPER12 pxRes, int iCount, 
LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a>参数

 _iFunction_(**int**)
  
要呼叫的一个数字，指示命令或函数。 有关详细信息，请参阅[Excel4/Excel12](excel4-excel12.md)。
  
 _pxRes_
  
一个指针到计算函数的结果。 在结果中指向任何内存将由 Excel 分配和应释放调用[xlFree](xlfree.md)后不再需要它，或通过设置**xlbitXLFree** ，如果它返回到 Excel 中。 
  
 _iCount_(**int**)
  
将传递给函数的参数数目。 从 Excel 2007 开始，限制为 255 的参数。 在早期版本，限制为 30。
  
 _argument1..._
  
函数的可选参数。 所有参数都必须为**XLOPER**s 对于**Excel**或对于**Excel12f** **XLOPER12**s 的指针。
  
## <a name="return-value"></a>返回值

这两个函数将返回相同的错误和成功代码为**Excel4**、 **Excel4v**、 **Excel12**和**Excel12v**。 有关这些代码的完整说明，请参阅[Excel4/Excel12](excel4-excel12.md) 。 此外，这些框架函数返回检测到**xlretFailed**而无需调用 C API 如果参数为 NULL 指针。 
  
## <a name="example"></a>示例

本示例将错误的参数传递给**Excel12f**函数，它向调试器发送邮件。 
  
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

