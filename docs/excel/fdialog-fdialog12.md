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
- fdialog 函数 [excel 2007]，fDialog12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: a9a47408-07d1-4a00-9596-abc48b12392f
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 58d0df500c38534ec1315d2dab1517c1f5272ad5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431524"
---
# <a name="fdialogfdialog12"></a>fDialog/fDialog12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
示例用户定义命令，演示如何使用 C API 中的对话框Microsoft Excel在 DLL (创建) UDD) 用户定义的对话框。 加载 GENERIC.xll 时，它将创建一个用户定义的菜单 Generic，通过该菜单可以访问此命令。
  
```cs
int WINAPI fDialog(void);
```

## <a name="parameters"></a>参数

该函数不采用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数始终返回 1。
  
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

