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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 0b991cf5cdae90522abc9512193ee556e4c6e6e1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773755"
---
# <a name="funcsum"></a>FuncSum

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
示例用户定义的工作表函数，它采用 1 到 29 个参数并将计算其和。 每个参数可以是一个号码、 区域或数组。 加载 GENERIC.xll 时，以便它可以调用从工作表中注册此函数。 
  
```cs
LPXLOPER12 WINAPI FuncSum(LPXLOPER12 px1, LPXLOPER12 px2, LPXLOPER12 px3,LPXLOPER12 px4, LPXLOPER12 px5, LPXLOPER12 px6, LPXLOPER12 px7,LPXLOPER12 px8, LPXLOPER12 px9, LPXLOPER12 px10, LPXLOPER12 px11,LPXLOPER12 px12, LPXLOPER12 px13, LPXLOPER12 px14, LPXLOPER12 px15,LPXLOPER12 px16, LPXLOPER12 px17, LPXLOPER12 px18, LPXLOPER12 px19,LPXLOPER12 px20, LPXLOPER12 px21, LPXLOPER12 px22, LPXLOPER12 px23,LPXLOPER12 px24, LPXLOPER12 px25, LPXLOPER12 px26, LPXLOPER12 px27,LPXLOPER12 px28, LPXLOPER12 px29);
```

## <a name="parameters"></a>参数

 _px1 px29_(**LPXLOPER12**)
  
指向**XLOPER12**参数。 该函数接受任何一种输入类型，但编码仅要操作的号码，字面数组数字和包含仅号码或空白单元格的范围。 如果提供少于 29 个参数，其余参数作为**xltypeMissing**提供。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

（**LPXLOPER12 xltypeNum**或**xltypeErr**）
  
总和的参数或 # #VALUE ！ 如果有非数值型或单元格区域或数组中的元素中提供的参数列表中。
  
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

