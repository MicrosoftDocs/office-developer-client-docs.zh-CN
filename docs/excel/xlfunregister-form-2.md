---
title: xlfUnregister（窗体 2）
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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 8bf1151e1ba4c165e784b88dce80096a2eaa62de
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419903"
---
# <a name="xlfunregister-form-2"></a>xlfUnregister（窗体 2）

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
可以从 DLL 或 XLL 命令调用，该命令本身已由 Microsoft Excel。 这相当于从 XLM 宏表Excel **UNREGISTER。** 
  
**xlfUnregister** 可以两种形式调用： 
  
- 表单 1：取消注册单个命令或函数。
    
- 表单 2：卸载和停用 XLL。
    
在表单 2 中调用此函数会强制完全卸载 DLL 或代码资源。 它取消注册 DLL 中所有函数，即使它们当前正由另一个宏使用，无论使用计数如何。 此函数调用 **xlAutoClose**，然后取消注册 DLL 中所有函数。
  
```cs
Excel12(xlfUnregister, LPXLOPER12 pxRes, 1, LPXLOPER12 pxModuleText);
```

## <a name="parameters"></a>参数

_pxModuleText_ (**xltypeStr**) 
  
DLL 的名称。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，则返回 **xltypeBool** (TRUE) 。  如果失败，则返回 **FALSE**。
  
## <a name="remarks"></a>备注

> [!NOTE] 
> 不要从 [xlAutoClose](xlautoclose.md) 的实现中调用此形式的函数，以尝试通过一个简单的函数调用注销 DLL 的所有资源。 这将导致递归调用 **xlAutoClose** 和堆栈溢出。 
  
### <a name="remember-to-delete-names"></a>请记住删除名称

如果将  _pxFunctionText_ 参数指定为 **xlfRegister**，则注册 DLL 的函数和命令时，必须通过调用每个函数的 **xlfSetName** 来明确删除名称，同时省略第二个参数，以便函数不再显示在函数向导中。 有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
## <a name="see-also"></a>另请参阅

- [xlfRegister（窗体 1）](xlfregister-form-1.md)
- [xlfRegisterId](xlfregisterid.md)
- [xlfUnregister（窗体 1）](xlfunregister-form-1.md)
- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

