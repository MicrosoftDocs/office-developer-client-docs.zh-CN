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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: ae6d8b2f0b95641678947e9bd75daa2237b080b1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773758"
---
# <a name="fshowdialog"></a>fShowDialog

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
示例用户定义的命令，加载和显示示例本机 Windows 的对话框。 当加载 GENERIC.xll 时，它会创建用户定义的菜单中，一般，通过其访问此命令。
  
```cs
int WINAPI fShowDialog(void);
```

## <a name="parameters"></a>参数

函数没有参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数返回整数零指示成功完成
  
## <a name="remarks"></a>备注

显示本机 Windows 对话框中的步骤如下所示：
  
1. 获取使用**GetHwnd**的 Microsoft Excel 主窗口句。
    
2. 挂接使用**HookExcelWindow**Excel 主窗口。
    
3. 显示使用**DialogBox**对话框。
    
4. 打开 Excel 主窗口中使用**UnhookExcelWindow**闩锁。
    
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[泛型 DLL 中的函数](functions-in-the-generic-dll.md)

