---
title: xlfRegisterId
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfRegisterId
keywords:
- xlfregisterid 函数 [excel 2007]
localization_priority: Normal
ms.assetid: d34cf20c-a5cd-45fb-9dcb-d49eac2d99dd
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 05119226d0b6190a2c4b30846c03a59b5c3cd1d8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420057"
---
# <a name="xlfregisterid"></a>xlfRegisterId

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
可以从已由 Microsoft Excel 调用它本身的 DLL 调用。 如果某个函数已注册, 它将返回该函数的现有 register ID, 而不 reregistering 它。 如果尚未注册某个函数, 它将注册它并返回生成的寄存器 ID。
  
```cs
Excel12(xlfRegisterId, LPXLOPER12 pxRes, 3,     LPXLOPER12 pxModuleText, LPXLOPER12 pxProcedure, LPXLOPER12 pxTypeText);
```

## <a name="parameters"></a>参数

_pxModuleText_(**xltypeStr**)
  
包含函数的 DLL 的名称。
  
_pxProcedure_(**xltypeStr**或**xltypeNum**)
  
如果为字符串, 则为要调用的函数的名称。 如果为数字, 则为要调用的函数的序号导出编号。 为清楚起见, 请始终使用字符串窗体。
  
_pxTypeText_(**xltypeStr**)
  
一个可选字符串, 指定函数的所有参数的类型和函数的返回值的类型。 有关详细信息，请参阅“注解”部分。 可省略定义**xlAutoRegister**的独立 DLL (XLL) 的此参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回函数的 register ID (**xltypeNum**), 该 ID 可在后续调用**xlfUnregister**时使用。
  
## <a name="remarks"></a>说明

如果您不想要维护收银机 ID, 但稍后需要对其进行注销, 则此函数很有用。 当要分配的函数位于 DLL 中时, 也可以将其分配给菜单、工具和按钮。
  
在已向**xlfRegister**提供有效的_pxFunctionText_参数的情况下注册 DLL 或 XLL 函数时, 也可以通过将_pxFunctionText_传递给函数**xlfEvaluate**来获取其 register ID。
  
## <a name="see-also"></a>另请参阅

- [注册表](xlfregister-form-1.md)
- [注销](xlfunregister-form-1.md)
- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

