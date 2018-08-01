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
- fdialog 函数 [excel 2007，] fDialog12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: a9a47408-07d1-4a00-9596-abc48b12392f
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 554b76d2d316110286e83158acfff33aa68e19c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773744"
---
# <a name="fdialogfdialog12"></a>fDialog/fDialog12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
示例用户定义演示如何使用 C API 中的对话框框功能创建 Microsoft Excel UDD （用户定义的对话框中） DLL 中的命令。 当加载 GENERIC.xll 时，它会创建用户定义的菜单中，一般，通过其访问此命令。
  
```cs
int WINAPI fDialog(void);
```

## <a name="parameters"></a>参数

函数没有参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数始终返回 1。
  
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

