---
title: xlGetHwnd
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlGetHwnd
keywords:
- xlgethwnd 函数 [excel 2007]
localization_priority: Normal
ms.assetid: be33b097-812b-4f5c-81be-4d9673e95b0b
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: ab4ac1bc040ef2ea9bca182624111e03722c5200
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425454"
---
# <a name="xlgethwnd"></a>xlGetHwnd

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
返回顶级 Microsoft Excel 窗口的窗口句柄。
  
```cs
Excel4(xlGetHwnd, LPXLOPER pxRes, 0); /* returns low part only */
Excel12(xlGetHwnd, LPXLOPER12 pxRes, 0); /* returns full handle */
```

## <a name="parameters"></a>参数

此函数没有参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

在 " **w** " 字段中包含窗口句柄 (**xltypeInt**)。 
  
## <a name="remarks"></a>说明

此函数对于编写 Windows API 代码很有用。
  
使用[Excel4](excel4-excel12.md)或[Excel4v](excel4v-excel12v.md)调用此函数时, 返回的 XLOPER 整数变量是带符号的16位短整型。这只能包含32位 Windows 句柄的低16位。 若要查找高部分, 您的代码必须循环访问所有打开的窗口, 查找低部分的匹配项。 从 Excel 2007 开始, **XLOPER12**的整数变量是一个有符号的32位 int, 因此包含整个句柄, 从而消除了对所有打开的窗口进行迭代的需求。 
  
### <a name="example"></a>示例

请参阅中`SAMPLES\GENERIC\GENERIC.C`的[fShowDialog 函数](fshowdialog.md)的代码。
  
## <a name="see-also"></a>另请参阅

- [xlGetInst](xlgetinst.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

