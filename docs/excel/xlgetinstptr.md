---
title: xlGetInstPtr
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a166f39c-f10b-4e56-8b5d-e6a54ee08c8f
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7cc07093e5db335d01fe85527746594d34d4d938
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773863"
---
# <a name="xlgetinstptr"></a>xlGetInstPtr

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
返回当前正在呼叫 DLL 的 Microsoft Excel 实例的实例句柄。
  
```cs
Excel4(xlGetInstPtr, LPXLOPER pxRes, 0);Excel12(xlGetInstPtr, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a>参数

此函数具有任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

在**val.bigdata.h.hdata**字段将实例句柄 (**xltypeBigData**)。 
  
## <a name="remarks"></a>说明

用于区分多个运行实例 Excel 的 DLL 调用此函数。
  
此函数返回与 32 位和 64 位版本的 Excel 的正确值。 它引入了 Excel 2010 中作为扩展到[xlGetInst](xlgetinst.md)函数，仅与 32 位版本的 Excel 一起正常运行。 
  
因为**XLOPER**和**XLOPER12**具有相同的结构支持**xltypeBigData**值使用的 API 回调函数中， [Excel4 和 Excel12](excel4-excel12.md)类别调用时此函数的运行正常类型。 
  
## <a name="example"></a>示例

下面的示例将实例调用于调用它的 Excel 的当前副本的 Excel 的最后一个副本进行比较。 如果它们是相同的则将返回 1;如果没有，则返回 0;如果函数失败，则返回-1。 此示例使用 32 位和 64 位版本的 Excel 工作正常。
  
`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlGetInstPtrExample(void)
{
    XLOPER12 xRes;
    static HANDLE hOld = 0;
    short iRet;
    if (Excel12(xlGetInstPtr, &xRes, 0) != xlretSuccess)
    iRet = -1;
    else
    {
    HANDLE hNew;
    hNew =  xRes.val.bigdata.h.hdata;
    if (hNew != hOld)
    iRet = 0;
    else
    iRet = 1;
    hOld = hNew;
    }
    return iRet;
}
```

## <a name="see-also"></a>另请参阅

- [xlGetHwnd](xlgethwnd.md)
- [xlGetInst](xlgetinst.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

