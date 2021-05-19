---
title: FuncFib
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- FuncFib
keywords:
- funcfib 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 6a719f04-b2d1-4f87-a227-be561cbd3e49
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: fb8f0c12c27fb2c95007eb5006c1d8b90970f3ad
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423669"
---
# <a name="funcfib"></a>FuncFib

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
计算第 N 个 Fi一号的用户定义的工作表函数示例。 当加载 GENERIC.xll 时，它会注册此函数，以便可以从工作表中调用它。
  
```cs
LPXLOPER12 WINAPI FuncFib (LPXLOPER12 pxN);
```

## <a name="parameters"></a>参数

 _pxN_ (**LPXLOPER12**) 
  
N 的值，其第 N 个 Fi一线数字是必需的。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

 (**为 xltypeNum LPXLOPER12，** 否则为 **xltypeErr**)  
  
第 N 个 Fi一号。
  
## <a name="remarks"></a>备注

函数使用函数块中定义的静态变量作为返回值 **XLOPER12**。 这不是线程安全函数，因此，此函数以及使用此策略返回 **XLOPER 或 XLOPER12** 的任何工作表函数不应从 Excel 2007 开始注册为线程安全。 
  
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

