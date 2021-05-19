---
title: xlCoerce
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlCoerce
keywords:
- xlcoerce 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 9d47c16c-a7e7-4998-b594-9cf001827b7b
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d84839535d5eb913ca8a62d631238e3330683d0e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424831"
---
# <a name="xlcoerce"></a>xlCoerce

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
将一种类型的 /  **XLOPER XLOPER12** 转换为另一种类型，或在工作表上查找单元格值。 
  
```cs
Excel12(xlCoerce, LPXLOPER12 pxRes, 2, LPXLOPER12 pxSource, LPXLOPER12 pxDestType);
```

## <a name="parameters"></a>参数

 _pxSource_
  
需要转换 **的** /  **源 XLOPER XLOPER12。** 
  
 _pxDestType_ (**xltypeInt**) 
  
 (可选) 。 您愿意接受的结果类型的位掩码。 您应该使用位 OR **运算符** ( |) 指定多个可能的类型。 如果省略该参数，则对单个单元格的引用将转换为值类型 xltypeStr、xltypeNum、xltypeBool、xltypeErr、xltypeNil (如果引用的单元格为空) ，则对单元格块的引用将转换为 **xltypeMulti**。     这使得 **xlCoerce** 成为查找单元格值的最方便方式。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回 xltypeStr、xltypeNum、xltypeBool、xltypeErr、xltypeNil或 **xltypeMulti**) 的强制值。 (   
  
## <a name="remarks"></a>备注

 **xlCoerce** 无法转换为 **xltypeBigData** 或 **xltypeFlow 或从 xltypeFlow 转换**。 将 **xltypeMissing** 或 **xltypeNil** 类型作为  _pxDestType_ 传递等效于省略该参数。 在某些情况下，转换可能会失败。 例如，某些字符串不能转换为数字，而其他字符串可以转换为数字。 
  
如果数组或多单元格引用转换为单个值类型，则结果是左上单元格或数组元素的值。
  
## <a name="example"></a>示例

可以在 中找到以下代码  `\SAMPLES\EXAMPLE\EXAMPLE.C` 。 
  
> [!NOTE]
> **xlcAlert** 函数隐式尝试将其参数转换为字符串，以便实际上可以删除此处所示的强制步骤，**并且可以将 xInt** 直接传递到 **xlcAlert**。 由于 **xlcAlert** 是命令宏，因此此代码仅在从宏工作表调用时才能正常运行。 
  
```cs
short WINAPI xlCoerceExample(short iVal)
{
   XLOPER12 xStr, xInt, xDestType;
   xInt.xltype = xltypeInt;
   xInt.val.w = iVal;
   xDestType.xltype = xltypeInt;
   xDestType.val.w = xltypeStr;
   Excel12f(xlCoerce, &xStr, 2, (LPXLOPER12)&xInt, (LPXLOPER12)&xDestType);
   Excel12f(xlcAlert, 0, 1, (LPXLOPER12)&xStr);
   Excel12f(xlFree, 0, 1, (LPXLOPER12)&xStr);
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[xlSet](xlset.md)


[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

