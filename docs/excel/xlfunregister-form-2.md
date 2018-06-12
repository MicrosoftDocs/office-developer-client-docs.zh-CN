---
title: xlfUnregister (窗体 2)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfUnregister (Form 2)
keywords:
- xlfunregister [excel 2007]
localization_priority: Normal
ms.assetid: 39c6eba7-ba41-4e7b-9a28-2b662378ff5a
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: e0154e380b65b8c57e7e96a98ef131e26b49e203
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773865"
---
# <a name="xlfunregister-form-2"></a>xlfUnregister (窗体 2)

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
可从 DLL 或 XLL 命令的本身已调用由 Microsoft Excel 进行调用。 这是等效于从 Excel XLM 宏工作表调用**注销**。 
  
可在两个窗体中调用**xlfUnregister** : 
  
- 窗体 1： 取消注册的单个命令或函数。
    
- 窗体 2： 卸载并停用 XLL。
    
此函数调用窗体 2 中，强制 DLL 或代码资源被完全卸载。 即使当前正在使用由另一个宏，无论使用计数，它注销所有在 DLL 中的功能。 此函数调用**xlAutoClose**，然后取消注册 DLL 中的所有功能。
  
```cs
Excel12(xlfUnregister, LPXLOPER12 pxRes, 1, LPXLOPER12 pxModuleText);
```

## <a name="parameters"></a>参数

_pxModuleText_(**xltypeStr**)
  
DLL 的名称。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，则返回**TRUE** (**xltypeBool**)。 如果不成功，则返回**FALSE**。
  
## <a name="remarks"></a>备注

> [!NOTE] 
> 不要尝试取消注册的所有与一个简单的函数调用的 DLL 的资源的[xlAutoClose](xlautoclose.md)实现调用此函数的形式。 这将导致**xlAutoClose**和堆栈溢出递归呼叫。 
  
### <a name="remember-to-delete-names"></a>请记住删除名称

如果您指定**xlfRegister**， _pxFunctionText_参数注册的 DLL 函数和命令时，必须明确名称通过调用删除**xlfSetName**每个省略第二个参数，以便函数不再显示在函数向导。 有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
## <a name="see-also"></a>另请参阅

- [xlfRegister (窗体 1)](xlfregister-form-1.md)
- [xlfRegisterId](xlfregisterid.md)
- [xlfUnregister (窗体 1)](xlfunregister-form-1.md)
- [关键及有用的 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

