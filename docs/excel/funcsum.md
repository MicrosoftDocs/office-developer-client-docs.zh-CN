---
title: FuncSum
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- FuncSum
keywords:
- funcsum 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 934192ef-8a89-4dbb-bd37-01e92ba24256
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 14db5812165812161cf7031f75338a981251dfd2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406939"
---
# <a name="funcsum"></a>FuncSum

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用户定义的工作表函数示例，该函数采用 1 到 29 个参数并计算其和。 每个参数可以是单个数字、区域或数组。 当加载 GENERIC.xll 时，它会注册此函数，以便可以从工作表中调用它。 
  
```cs
LPXLOPER12 WINAPI FuncSum(LPXLOPER12 px1, LPXLOPER12 px2, LPXLOPER12 px3,LPXLOPER12 px4, LPXLOPER12 px5, LPXLOPER12 px6, LPXLOPER12 px7,LPXLOPER12 px8, LPXLOPER12 px9, LPXLOPER12 px10, LPXLOPER12 px11,LPXLOPER12 px12, LPXLOPER12 px13, LPXLOPER12 px14, LPXLOPER12 px15,LPXLOPER12 px16, LPXLOPER12 px17, LPXLOPER12 px18, LPXLOPER12 px19,LPXLOPER12 px20, LPXLOPER12 px21, LPXLOPER12 px22, LPXLOPER12 px23,LPXLOPER12 px24, LPXLOPER12 px25, LPXLOPER12 px26, LPXLOPER12 px27,LPXLOPER12 px28, LPXLOPER12 px29);
```

## <a name="parameters"></a>参数

 _px1-px29_ (**LPXLOPER12**) 
  
指向 **XLOPER12 参数的** 指针。 函数接受任何类型的输入类型，但编码时仅对数字、数字文本数组和仅包含数字或空白单元格的范围进行操作。 如果提供的参数少于 29 个，则其余参数作为 **xltypeMissing 提供**。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

 (**LPXLOPER12 xltypeNum** 或 **xltypeErr**) 
  
参数或参数#VALUE！ 如果提供的参数列表或数组中区域或元素的单元格中存在非数值。
  
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

