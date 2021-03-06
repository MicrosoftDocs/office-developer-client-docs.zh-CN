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
- tempbool 函数 [excel 2007]，TempBool12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 0cf1fa58-416f-4692-a2e3-422473c19492
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: c8c917f0004fe091413ea670f1cc562f1d701fa0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433715"
---
# <a name="tempbooltempbool12"></a>TempBool/TempBool12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
创建包含布尔 TRUE 或 FALSE 的临时 /  **XLOPER XLOPER12** **的框架** 库 **函数**。
  
```cs
LPXLOPER TempBool(int b);
LPXLOPER12 TempBool12(int b);
```

## <a name="parameters"></a>参数

 _b_ (**int)**
  
使用 0 可返回 **FALSE;** 使用任何其他值返回 **TRUE**。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回一 **个 xltypeBool** **Boolean** 类型的值，其中包含传入的逻辑值。 
  
## <a name="example"></a>示例

下面的示例使用 **TempBool12** 函数清除状态栏。 调用[Excel/Excel12f 函数时将](excel-excel12f.md)释放临时内存。 
  
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

