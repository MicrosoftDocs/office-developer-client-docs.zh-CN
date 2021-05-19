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
  
返回顶级窗口的窗口句柄Microsoft Excel窗口。
  
```cs
Excel4(xlGetHwnd, LPXLOPER pxRes, 0); /* returns low part only */
Excel12(xlGetHwnd, LPXLOPER12 pxRes, 0); /* returns full handle */
```

## <a name="parameters"></a>参数

此函数没有参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

包含 **val.w** (**xltypeInt)** 窗口句柄。 
  
## <a name="remarks"></a>备注

此函数可用于编写Windows API 代码。
  
使用 Excel4 或[Excel4v](excel4-excel12.md)调用此函数时，返回的 XLOPER 整数变量是一个有符号的 16 位短整型整数。 [](excel4v-excel12v.md)这只能包含 32 位句柄的低 16 Windows位。 若要查找高部分，代码必须浏览所有打开的窗口，查找与低部分匹配的项。 从 Excel 2007 开始 **，XLOPER12** 的整数变量是一个已签名的 32 位 int，因此包含整个句柄，无需重新访问所有打开的窗口。 
  
### <a name="example"></a>示例

请参阅 中的 [fShowDialog 函数](fshowdialog.md) 代码  `SAMPLES\GENERIC\GENERIC.C` 。
  
## <a name="see-also"></a>另请参阅

- [xlGetInst](xlgetinst.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

