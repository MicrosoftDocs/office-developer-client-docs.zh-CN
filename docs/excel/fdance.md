---
title: fDance
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- fDance
keywords:
- fdance 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 8c2f2d83-b7aa-456e-b473-a54897bc35ae
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a191c07d2a06a1cb6123c235e8fac69d90426758
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409046"
---
# <a name="fdance"></a>fDance

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
示例用户定义命令，该命令将活动工作表上的选定单元格四处更改，直到用户按 **ESC。** 加载 GENERIC.xll 时，它将创建一个用户定义的菜单 Generic，通过该菜单可以访问此命令。
  
```cs
int WINAPI fDance(void);
```

## <a name="parameters"></a>参数

该函数不采用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数始终返回 1。
  
## <a name="remarks"></a>备注

这是一个冗长操作的示例。 它偶尔调用[函数 xlAbort。](xlabort.md) 这样，处理器 (协作多任务) ，并检查用户是否已按 **ESC** 取消操作。 如果是这样，它将为用户提供取消中止的机会。 
  
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

