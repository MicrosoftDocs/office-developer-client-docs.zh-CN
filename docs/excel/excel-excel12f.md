---
title: Excel/Excel12f
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Excel12f
keywords:
- excel 函数 [excel 2007], Excel12f 函数 [excel 2007]
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
  
框架库函数。 **Excel**是[Excel4](excel4-excel12.md)函数的包装。 **Excel12f**是[Excel12](excel4-excel12.md)函数的包装。 每个检查到查看的参数是否均为零, 这表示临时**XLOPER**或**XLOPER12**的创建失败。 如果发生错误, 每个都将打印一条调试消息。 完成后, 每个都将释放可能已为临时**XLOPER**s 和**XLOPER12**s 创建的所有临时内存。
  
 仅可从 Excel 2007 C API 库开始的 DLL 调用**Excel12f** 。 此外, 它仅在从 Excel 2007 开始运行时才有效, 否则会与**xlretFailed**失败。 
  
```cs
int Excel(int iFunction, LPXLOPER pxRes, int iCount, 
LPXLOPER argument1, ...);
int Excel12f(int iFunction, LPXLOPER12 pxRes, int iCount, 
LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a>参数

 _iFunction_(**int**)
  
表示要调用的命令或函数的数字。 有关详细信息, 请参阅[Excel4/Excel12](excel4-excel12.md)。
  
 _pxRes_
  
指向计算函数的结果的指针。 在结果中指向的任何内存都将由 Excel 分配, 在 xlFree 不再需要时, 应在对[](xlfree.md)的调用中释放, 或者在将**xlbitXLFree**返回到 Excel 时将其设置为。 
  
 _iCount_(**int**)
  
将传递给函数的参数的数目。 从 Excel 2007 开始, 限制为255个参数。 在早期版本中, 限制为30个。
  
 _argument1 .。。_
  
函数的可选参数。 在**Excel**的情况下, 所有参数都必须是指向**XLOPER**s 的指针, 否则, 在**Excel12f**的情况下, 也必须是**XLOPER12**。
  
## <a name="return-value"></a>返回值

这两个函数都返回与**Excel4**、 **Excel4v**、 **Excel12**和**Excel12v**相同的错误和成功代码。 有关这些代码的完整说明, 请参阅[Excel4/Excel12](excel4-excel12.md) 。 此外, 如果检测到指向参数的 NULL 指针, 则这些框架函数将返回**xlretFailed** , 而不调用 C API。 
  
## <a name="example"></a>示例

此示例将一个不正确的参数传递给**Excel12f**函数, 该函数将向调试器发送一条消息。 
  
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

