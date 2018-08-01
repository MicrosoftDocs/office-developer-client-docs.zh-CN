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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 48ce927f6bcb328a90779948a660cf9d0b460205
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773841"
---
# <a name="xlfsetname"></a>xlfSetName

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于创建和删除已定义的名称 DLL 相关联。
  
```cs
Excel12(xlfSetName, LPXLOPER12 pxRes, 2, LPXLOPER12 pxNameText, LPXLOPER12 pxNameDefinition);
```

## <a name="parameters"></a>参数

_pxNameText_(**xltypeStr**)
  
有效的名称通常限制在 Microsoft Excel 中应符合范围的名称。
  
_pxNameDefinition_（**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeMulti**、 **xltypeSRef**、 **xltypeRef**或**xltypeInt**）
  
（可选）。 值、 值、 单元格或单元格区域的设置的_pxNameText_被定义为。 如果省略，则删除名称。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

_pxRes_（**xltypeBool**或**xltypeErr**）
  
如果操作成功，则返回 TRUE 或 FALSE，如果无法创建或删除名称。 返回 #VALUE ！ 如果一个或多个参数无效。
  
## <a name="remarks"></a>说明

使用有效_pxFunctionText_参数**xlfRegister**注册函数或命令，Excel 将新建关联的 DLL 资源的名称。 当正在卸载 DLL 时，应使用[xlfSetName 函数](xlfsetname.md)删除此类名称。 但是，由于在 Excel 中的已知问题，此删除操作失败。 有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
### <a name="example"></a>示例

请参阅**xlAutoClose**函数中的代码`\SAMPLES\GENERIC\GENERIC.C`。
  
## <a name="see-also"></a>另请参阅

- [基本的有用 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

