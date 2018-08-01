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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: cd401393b7465442cef9342b942a27456871c68b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773855"
---
# <a name="xlfregisterid"></a>xlfRegisterId

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
可从本身已调用由 Microsoft Excel DLL 调用。 如果已注册一个函数，它将返回该函数的现有注册 ID，而不重新注册它。 如果尚未未注册一个函数，它将其注册并返回结果注册 id。
  
```cs
Excel12(xlfRegisterId, LPXLOPER12 pxRes, 3,     LPXLOPER12 pxModuleText, LPXLOPER12 pxProcedure, LPXLOPER12 pxTypeText);
```

## <a name="parameters"></a>参数

_pxModuleText_(**xltypeStr**)
  
包含该函数的 dll 名称。
  
_pxProcedure_（**xltypeStr**或**xltypeNum**）
  
如果要调用的函数的名称的字符串。 如果一个号码，序号导出要调用的函数的数量。 为清楚起见和可靠性，始终使用字符串形式。
  
_pxTypeText_(**xltypeStr**)
  
可选字符串指定给函数的所有参数的类型和函数的返回值的类型。 有关详细信息，请参阅"备注"部分。 可以省略该参数为独立 DLL (XLL) 定义**xlAutoRegister**。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回可用于对**xlfUnregister**后续调用的函数 (**xltypeNum**)，注册 ID。
  
## <a name="remarks"></a>说明

您不希望担心维护一个注册 ID，但您需要一个更高版本用于注销时，此函数很有用。 也是用于将分配给菜单、 工具和按钮时要分配的功能是在 DLL 中。
  
在具有已提供给**xlfRegister**有效_pxFunctionText_参数已注册 DLL 或 XLL 函数，也可以通过将_pxFunctionText_传递给函数**xlfEvaluate**获得其注册 ID。
  
## <a name="see-also"></a>另请参阅

- [注册](xlfregister-form-1.md)
- [注销](xlfunregister-form-1.md)
- [基本的有用 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

