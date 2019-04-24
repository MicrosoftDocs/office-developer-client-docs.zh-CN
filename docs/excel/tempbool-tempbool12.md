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
- tempbool 函数 [excel 2007], TempBool12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 0cf1fa58-416f-4692-a2e3-422473c19492
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: c8c917f0004fe091413ea670f1cc562f1d701fa0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310351"
---
# <a name="tempbooltempbool12"></a>TempBool/TempBool12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Framework library 函数, 用于创建包含**布尔****值 TRUE**或**FALSE**的临时**XLOPER**/ **XLOPER12** 。
  
```cs
LPXLOPER TempBool(int b);
LPXLOPER12 TempBool12(int b);
```

## <a name="parameters"></a>参数

 _b_ (**int**)
  
使用0将返回**FALSE**;使用任何其他值返回**TRUE**。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回一个**xltypeBool** **Boolean 类型**的值, 该值包含传入的逻辑值。 
  
## <a name="example"></a>示例

下面的示例使用**TempBool12**函数清除状态栏。 调用[Excel/Excel12f](excel-excel12f.md)函数时, 将释放临时内存。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short int WINAPI TempBoolExample(void)
{
    Excel12f(xlcMessage, 0, 1, TempBool12(0));
    return 1;
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

