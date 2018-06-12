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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 8d1c97ea57e968aaedffca6b37ded3d875e87413
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773747"
---
# <a name="funcfib"></a>FuncFib

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
示例计算第 n 个 Fibonacci 数的用户定义的工作表函数。 加载 GENERIC.xll 时，以便它可以调用从工作表中注册此函数。
  
```cs
LPXLOPER12 WINAPI FuncFib (LPXLOPER12 pxN);
```

## <a name="parameters"></a>参数

 _pxN_(**LPXLOPER12**)
  
N 需要第 n 个 Fibonacci 数的值。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

（**xltypeNum LPXLOPER12**如果成功或**xltypeErr**否则为） 
  
第 n 个 Fibonacci 数。
  
## <a name="remarks"></a>备注

该函数使用的函数块内定义为**XLOPER12**的返回值的静态变量。 这不是线程安全的，因此此函数中，并使用此策略对返回**XLOPER**s 或**XLOPER12**s 进行任何工作表函数不应注册为安全启动 Excel 2007 中的线程。
  
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[泛型 DLL 中的函数](functions-in-the-generic-dll.md)

