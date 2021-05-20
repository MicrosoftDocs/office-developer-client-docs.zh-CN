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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 97f0a1ec797176fb51c87c58f94e46a323ae5b32
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429913"
---
# <a name="fexit"></a>fExit

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
卸载 GENERIC.xll 的用户定义命令示例。 加载 GENERIC.xll 时，它将创建一个用户定义的菜单 Generic，通过该菜单可以访问此命令。 
  
```cs
int WINAPI fExit(void);
```

## <a name="parameters"></a>参数

该函数不采用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数始终返回 1。
  
## <a name="remarks"></a>备注

这是用户启动的用于退出 GENERIC.xll 的例程 应避免在此函数  `UNREGISTER("GENERIC.XLL")` 中调用。 这将强制取消注册此 DLL 中所有函数，即使它们已在其他地方注册。 相反，应一次注销一个函数。 
  
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

