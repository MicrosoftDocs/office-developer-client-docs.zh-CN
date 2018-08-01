---
title: TempErr/TempErr12
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempErr
- TempErr12
keywords:
- temperr 函数 [excel 2007，] TempErr12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: cf8c26b2-ca2b-4dda-a02d-0ccbeac19106
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 22c0ff1b8259fc0e5ee70edb06bb3db53781ff8c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773812"
---
# <a name="temperrtemperr12"></a>TempErr/TempErr12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
创建临时**XLOPER**的框架库函数/ **XLOPER12**包含 Microsoft Excel 工作表错误。 
  
```cs
LPXLOPER TempErr(WORD err);
LPXLOPER12 TempErr12(BOOL err);
```

## <a name="parameters"></a>参数

 _err_
  
所需的错误代码或其文字等价数值下, 表中所示。
  
|**Error**|**XLCALL 中定义的错误代码。H**|**十进制等效项**|
|:-----|:-----|:-----|
|#NULL  <br/> |**xlerrNull** <br/> |0  <br/> |
|#DIV/0!  <br/> |**xlerrDiv0** <br/> |7  <br/> |
|#VALUE!  <br/> |**xlerrValue** <br/> |15  <br/> |
|#REF!  <br/> |**xlerrRef** <br/> |23  <br/> |
|#NAME?  <br/> |**xlerrName** <br/> |29  <br/> |
|#NUM!  <br/> |**xlerrNum** <br/> |36  <br/> |
|#N/A  <br/> |**xlerrNA** <br/> |42  <br/> |
   
## <a name="return-value"></a>返回值

返回一个**xltypeBool**包含的错误代码中传递。 
  
## <a name="example"></a>示例

本示例使用**TempErr12**函数返回 #VALUE ！ 到 Excel 时出错。 
  
> [!NOTE]
> Framework 库函数**TempErr12**从内部缓冲区，通常被释放调用框架函数**Excel12f**时分配内存。 如果没有**Excel12f**调用重复调用此示例函数，则将发生内存泄漏。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
LPXLOPER WINAPI TempErrExample(void)
{
    return TempErr12(xlerrValue);
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

