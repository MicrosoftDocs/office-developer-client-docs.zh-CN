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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e4e184d4e456ffe26292fe31b1b41463834216f9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773858"
---
# <a name="xlsheetid"></a>xlSheetId

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
若要构建外部引用查找命名工作表的工作表 ID。
  
```cs
Excel12(xlSheetId, LPXLOPER12 pxRes, 1, LPXLOPER12 pxSheetName);
```

## <a name="parameters"></a>参数

_pxSheetName_(**xltypeStr**)
  
（可选）。 要了解有关簿和工作表的名称。 如果省略，则**xlSheetId**函数将返回活动 （前端） 工作表的工作表 ID。 
  
## <a name="return-value"></a>返回值

返回中的工作表 ID _pxRes-\>val.mref.idSheet_。 
  
> [!NOTE]
> _PxRes-\>val.mref.lpmref_数组指针设置为 NULL 此呼叫后，以便不需要调用**xlFree**释放内存中通常包含此类型，尽管完全可以安全地这样做。 
  
## <a name="remarks"></a>说明

包含指定的工作表的工作簿必须打开要使用此函数。 没有方法来构造向未打开工作簿从 DLL 的引用。 有关使用**xlSheetId**构造引用的详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md) **xltypeRef**构造的示例。 
  
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

