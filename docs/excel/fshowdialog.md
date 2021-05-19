---
title: fShowDialog
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- fShowDialog
keywords:
- fshowdialog 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 6cc01075-7221-488e-870f-433da62930e6
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 6122e4b99c69cd1bd878c9267ff85f59d0f61998
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433589"
---
# <a name="fshowdialog"></a>fShowDialog

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用户定义的示例命令，用于加载并显示示例本机Windows对话框。 加载 GENERIC.xll 时，它将创建一个用户定义的菜单 Generic，通过该菜单可以访问此命令。
  
```cs
int WINAPI fShowDialog(void);
```

## <a name="parameters"></a>参数

该函数不采用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数返回整数 0 以指示成功完成
  
## <a name="remarks"></a>备注

显示本机应用程序Windows的步骤如下所示：
  
1. 使用 **GetHwnd** Microsoft Excel主Windows句柄。
    
2. 使用 **hookExcelWindow** Excel挂钩主窗口。
    
3. 使用 **DialogBox 显示对话框**。
    
4. 使用 **UnhookExcelWindow** 取消Excel主窗口。
    
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

