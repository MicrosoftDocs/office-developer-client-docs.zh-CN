---
title: fDialog/fDialog12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- fDialog
- fDialog12
keywords:
- fdialog 函数 [excel 2007], fDialog12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: a9a47408-07d1-4a00-9596-abc48b12392f
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 58d0df500c38534ec1315d2dab1517c1f5272ad5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304065"
---
# <a name="fdialogfdialog12"></a>fDialog/fDialog12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
演示如何使用 C API 中的对话框功能在 DLL 中创建 Microsoft Excel UDD (用户定义的对话框) 的用户定义命令示例。 当加载了 generic xll 时, 它将创建一个用户定义的菜单 (通用), 通过该菜单可访问此命令。
  
```cs
int WINAPI fDialog(void);
```

## <a name="parameters"></a>参数

函数不采用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数总是返回1。
  
### <a name="example"></a>示例

有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

