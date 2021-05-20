---
title: xlSheetId
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlSheetId
keywords:
- xlsheetid 函数 [excel 2007]
localization_priority: Normal
ms.assetid: cb32059c-b899-49cf-8028-ff828998ab75
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a2ca1bb478c5c985ad7032e30ed0cfe3aef31406
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428429"
---
# <a name="xlsheetid"></a>xlSheetId

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
查找已命名工作表的工作表 ID 以构建外部引用。
  
```cs
Excel12(xlSheetId, LPXLOPER12 pxRes, 1, LPXLOPER12 pxSheetName);
```

## <a name="parameters"></a>参数

_pxSheetName_ (**xltypeStr**) 
  
 (可选) 。 要查找的书籍和工作表的名称。 如果省略 **，xlSheetId** 函数将返回活动工作表的工作表 (表) ID。 
  
## <a name="return-value"></a>返回值

返回 _pxRes- \> val.mref.idSheet 中的工作表 ID。_ 
  
> [!NOTE]
> 在此调用后  _，pxRes- \> val.mref.lpmref_ 数组指针设置为 NULL，因此无需调用 **xlFree** 来释放此类型通常包含的内存，尽管这样做完全安全。 
  
## <a name="remarks"></a>备注

必须打开包含指定工作表的工作簿，以使用此函数。 无法从 DLL 构造对未打开工作簿的引用。 有关使用 **xlSheetId** 构造引用的详细信息，请参阅 memory [Management in Excel](memory-management-in-excel.md) for examples of **xltypeRef** construction。 
  
## <a name="example"></a>示例

 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlSheetIdExample(void)
{       
   XLOPER12 xSheetName, xRes;
   xSheetName.xltype = xltypeStr;
   xSheetName.val.str = L"\022[BOOK1.XLSX]Sheet1";
   Excel12(xlSheetId, &xRes, 1, (LPXLOPER12)&xSheetName);
   Excel12f(xlcAlert, 0, 1, TempNum12(xRes.val.mref.idSheet));
   Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes);
   return 1;
}
```

## <a name="see-also"></a>另请参阅

- [xlSheetNm](xlsheetnm.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

