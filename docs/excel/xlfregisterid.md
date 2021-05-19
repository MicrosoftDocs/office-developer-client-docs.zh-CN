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
  
可以从已由 Microsoft Excel 调用的 DLL 中调用。 如果函数已经注册，它将返回该函数的现有注册 ID，而不重新注册它。 如果函数尚未注册，它将注册它并返回生成的注册 ID。
  
```cs
Excel12(xlfRegisterId, LPXLOPER12 pxRes, 3,     LPXLOPER12 pxModuleText, LPXLOPER12 pxProcedure, LPXLOPER12 pxTypeText);
```

## <a name="parameters"></a>参数

_pxModuleText_ (**xltypeStr**) 
  
包含 函数的 DLL 的名称。
  
_pxProcedure_ (**xltypeStr** 或 **xltypeNum**) 
  
如果是字符串，则表示要调用的函数的名称。 如果是数字，则表示要调用的函数的序号导出号。 为清楚和可靠，请始终使用字符串形式。
  
_pxTypeText_ (**xltypeStr**) 
  
一个可选字符串，用于指定函数的所有参数的类型以及函数的返回值类型。 有关详细信息，请参阅“注解”部分。 对于定义 **xlAutoRegister** 的 XLL 独立 DLL (可以) 此参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回函数 **xltypeNum** (的注册 ID) ，该 id 可用于对 **xlfUnregister 的后续调用**。
  
## <a name="remarks"></a>备注

如果您不想维护注册 ID，但稍后需要一个注册 ID，则此函数非常有用。 当要分配的函数位于 DLL 中时，它还可用于分配给菜单、工具和按钮。
  
如果 DLL 或 XLL 函数已使用提供给 **xlfRegister** 的有效 _pxFunctionText_ 参数进行注册，则也可通过向函数 **xlfEvaluate** 传递 _pxFunctionText_ 来获取其注册 ID。
  
## <a name="see-also"></a>另请参阅

- [REGISTER](xlfregister-form-1.md)
- [UNREGISTER](xlfunregister-form-1.md)
- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

