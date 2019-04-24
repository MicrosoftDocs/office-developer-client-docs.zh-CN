---
title: fExit
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- fExit
keywords:
- fexit 函数 [excel 2007]
localization_priority: Normal
ms.assetid: d85685fa-df70-45bb-b629-a9d43b5cb926
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 97f0a1ec797176fb51c87c58f94e46a323ae5b32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310855"
---
# <a name="fexit"></a>fExit

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于卸载通用 xll 的用户定义命令示例。 当加载了 generic xll 时, 它将创建一个用户定义的菜单 (通用), 通过该菜单可访问此命令。 
  
```cs
int WINAPI fExit(void);
```

## <a name="parameters"></a>参数

函数不采用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数总是返回1。
  
## <a name="remarks"></a>注解

这是用户启动的用于退出 GENERIC 的例程。您应避免只是在`UNREGISTER("GENERIC.XLL")`此函数中调用。 这将强制注销此 DLL 中的所有函数, 即使它们在其他位置注册也是如此。 相反, 一次注销一个函数。 
  
### <a name="example"></a>示例

有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

