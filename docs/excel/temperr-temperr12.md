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
- temperr 函数 [excel 2007], TempErr12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: cf8c26b2-ca2b-4dda-a02d-0ccbeac19106
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 68a0addc36ecf1b4491ab1e4f5b10f359bbc59c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410607"
---
# <a name="temperrtemperr12"></a>TempErr/TempErr12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
Framework library 函数, 用于创建一个包含 Microsoft Excel 工作表错误的临时**XLOPER**/ **XLOPER12** 。 
  
```cs
LPXLOPER TempErr(WORD err);
LPXLOPER12 TempErr12(BOOL err);
```

## <a name="parameters"></a>参数

 _err_
  
所需的错误代码或其常数值等效项, 如下表所示。
  
|**错误**|**xlcall.h 中定义的错误代码。水平**|**十进制等效项**|
|:-----|:-----|:-----|
|#NULL  <br/> |**xlerrNull** <br/> |0  <br/> |
|#DIV/0!  <br/> |**xlerrDiv0** <br/> |步  <br/> |
|#VALUE!  <br/> |**xlerrValue** <br/> |15   <br/> |
|#REF!  <br/> |**xlerrRef** <br/> |上午  <br/> |
|#NAME?  <br/> |**xlerrName** <br/> |29  <br/> |
|#NUM!  <br/> |**xlerrNum** <br/> |36  <br/> |
|#N/A  <br/> |**xlerrNA** <br/> |42  <br/> |
   
## <a name="return-value"></a>返回值

返回一个**xltypeBool** , 其中包含传入的错误代码。 
  
## <a name="example"></a>示例

此示例使用**TempErr12**函数返回 #VALUE! 对 Excel 的错误。 
  
> [!NOTE]
> 框架库函数**TempErr12**从内部缓冲区分配内存, 该缓冲区通常在调用 Framework 函数**Excel12f**时释放。 如果在未调用**Excel12f**的情况下重复调用此示例函数, 则会发生内存泄漏。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
LPXLOPER WINAPI TempErrExample(void)
{
    return TempErr12(xlerrValue);
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

