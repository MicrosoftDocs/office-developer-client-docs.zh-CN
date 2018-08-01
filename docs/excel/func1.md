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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 26439f1fb05aae2077844ce19935d9ff99e4f701
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773749"
---
# <a name="func1"></a>Func1

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
示例用户定义的工作表函数演示的静态的字符串值返回。 加载 GENERIC.xll 时，以便它可以调用从工作表中注册此函数。
  
```cs
LPXLOPER12 WINAPI Func1(LPXLOPER12 px);
```

## <a name="parameters"></a>参数

 _像素_(**LPXLOPER**)
  
此参数被忽略，并且可仅对触发器 Microsoft Excel 将调用的函数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

 **LPXLOPER12**： 始终字符串"Func1"
  
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

