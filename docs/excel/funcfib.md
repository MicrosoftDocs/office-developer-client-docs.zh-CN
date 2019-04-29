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
  
用于计算第 n 个斐波纳契数的用户定义的工作表函数示例。 当加载了 GENERIC xll 时, 它将注册此函数, 以便可以从工作表中调用它。
  
```cs
LPXLOPER12 WINAPI FuncFib (LPXLOPER12 pxN);
```

## <a name="parameters"></a>参数

 _pxN_(**LPXLOPER12**)
  
n 的值为 n, 其中必须有第 n 个斐波纳契数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

(如果成功, 则为**xltypeNum LPXLOPER12** , 否则为**xltypeErr** ) 
  
第 n 个斐波纳契号码。
  
## <a name="remarks"></a>说明

函数使用在函数块中定义的静态变量作为返回值**XLOPER12**。 这不是线程安全的, 因此此函数以及使用此策略以返回**XLOPER**s 或**XLOPER12**s 的任何工作表函数都不应注册为 Excel 2007 中的线程安全。
  
### <a name="example"></a>示例

有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

