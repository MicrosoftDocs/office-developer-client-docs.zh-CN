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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a191c07d2a06a1cb6123c235e8fac69d90426758
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311037"
---
# <a name="fdance"></a>fDance

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于更改活动工作表上的选定单元格的用户定义命令的示例, 直到用户按**ESC**。 当加载了 generic xll 时, 它将创建一个用户定义的菜单 (通用), 通过该菜单可访问此命令。
  
```cs
int WINAPI fDance(void);
```

## <a name="parameters"></a>参数

函数不采用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数总是返回1。
  
## <a name="remarks"></a>注解

这是一个漫长的操作示例。 它偶尔调用函数[xlAbort](xlabort.md) 。 这将生成处理器 (帮助协作多任务), 并检查用户是否已按**ESC**取消操作。 如果是这样, 它向用户提供了取消中止的机会。 
  
### <a name="example"></a>示例

有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

