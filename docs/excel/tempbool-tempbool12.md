---
title: TempBool/TempBool12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempBool
- TempBool12
keywords:
- tempbool 函数 [excel 2007，] TempBool12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 0cf1fa58-416f-4692-a2e3-422473c19492
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 30874e7b918d8cd780bef60b4b02de1319f0f9ab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773815"
---
# <a name="tempbooltempbool12"></a>TempBool/TempBool12

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
创建临时**XLOPER**的框架库函数/ **XLOPER12**包含**布尔值** **TRUE**或**FALSE**。
  
```cs
LPXLOPER TempBool(int b);
LPXLOPER12 TempBool12(int b);
```

## <a name="parameters"></a>参数

 _b_ (**int**)
  
使用 0，则返回**FALSE**;使用任何其他值返回**TRUE**。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回**xltypeBool** **布尔**包含传入的逻辑值。 
  
## <a name="example"></a>示例

下面的示例使用**TempBool12**函数以清除状态栏。 调用[Excel/Excel12f](excel-excel12f.md)函数时释放临时内存。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short int WINAPI TempBoolExample(void)
{
    Excel12f(xlcMessage, 0, 1, TempBool12(0));
    return 1;
}
```

## <a name="see-also"></a>另请参阅



[Framework 库中的函数](functions-in-the-framework-library.md)

