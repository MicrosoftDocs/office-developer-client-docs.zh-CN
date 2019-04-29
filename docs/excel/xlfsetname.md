---
title: xlfSetName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfSetName
keywords:
- xlfsetname 函数 [excel 2007]
localization_priority: Normal
ms.assetid: ea7fd713-7c1b-4648-a609-3334f595c61a
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e6327ccf2cd18e42c3ef9abe538e6f669e498352
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404258"
---
# <a name="xlfsetname"></a>xlfSetName

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用于创建和删除与 DLL 相关联的已定义名称。
  
```cs
Excel12(xlfSetName, LPXLOPER12 pxRes, 2, LPXLOPER12 pxNameText, LPXLOPER12 pxNameDefinition);
```

## <a name="parameters"></a>参数

_pxNameText_(**xltypeStr**)
  
区域名称, 应符合 Microsoft Excel 对有效名称的常用限制。
  
_pxNameDefinition_(**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeMulti**、 **xltypeSRef**、 **xltypeRef**或**xltypeInt**)
  
(可选)。 _pxNameText_定义为的值、值、单元格或单元格区域的集合。 如果省略, 则删除该名称。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

_pxRes_(**xltypeBool**或**xltypeErr**)
  
如果操作成功, 则为 TRUE; 如果无法创建或删除此名称, 则为 FALSE。 返回 #VALUE! 如果一个或多个参数无效。
  
## <a name="remarks"></a>说明

使用**xlfRegister**和有效的_pxFunctionText_参数注册函数或命令时, Excel 将创建与 DLL 资源相关联的名称。 卸载 DLL 时, 应使用[xlfSetName 函数](xlfsetname.md)删除此类名称。 但是, 由于 Excel 中的已知问题, 此删除操作将失败。 有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
### <a name="example"></a>示例

请参阅中`\SAMPLES\GENERIC\GENERIC.C`的**xlAutoClose**函数的代码。
  
## <a name="see-also"></a>另请参阅

- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

