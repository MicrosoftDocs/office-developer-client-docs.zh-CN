---
title: Func1
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Func1
keywords:
- func1 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 801b14ef-0be8-4b97-919d-a9d413705d1c
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a3d3c6bbd529f43bd75b31b9348498928390a8f5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408913"
---
# <a name="func1"></a>Func1

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用户定义的工作表函数示例演示静态字符串值的返回。 当加载 GENERIC.xll 时，它会注册此函数，以便可以从工作表中调用它。
  
```cs
LPXLOPER12 WINAPI Func1(LPXLOPER12 px);
```

## <a name="parameters"></a>参数

 _px_ (**LPXLOPER**) 
  
此参数将被忽略，并且只能触发Microsoft Excel调用该函数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

 **LPXLOPER12：** 始终为字符串"Func1"
  
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

