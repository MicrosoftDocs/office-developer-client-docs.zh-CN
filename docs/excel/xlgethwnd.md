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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a22365d6c945aaa5995e2c519c757a1a7515655a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773864"
---
# <a name="xlgethwnd"></a>xlGetHwnd

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
返回顶级 Microsoft Excel 窗口的窗口句柄。
  
```cs
Excel4(xlGetHwnd, LPXLOPER pxRes, 0); /* returns low part only */
Excel12(xlGetHwnd, LPXLOPER12 pxRes, 0); /* returns full handle */
```

## <a name="parameters"></a>参数

此函数具有任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

包含**val.w**字段中的窗口句柄 (**xltypeInt**)。 
  
## <a name="remarks"></a>说明

此函数可用于编写 Windows API 代码。
  
返回的 XLOPER integer 变量时调用此函数使用[Excel4](excel4-excel12.md)或[Excel4v](excel4v-excel12v.md)，为签名的 16 位短 int。这是只可以包含低 16 位的 32 位 Windows 句柄。 若要查找的高的部件，您的代码必须循环查找与低的部件的匹配的所有打开的窗口。 从 Excel 2007 开始， **XLOPER12**整数变量是带符号的 32 位 int 和因此包含整个窗口的句，而不必循环访问所有打开的窗口。 
  
### <a name="example"></a>示例

请参阅[fShowDialog 函数](fshowdialog.md)中的代码`SAMPLES\GENERIC\GENERIC.C`。
  
## <a name="see-also"></a>另请参阅

- [xlGetInst](xlgetinst.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

