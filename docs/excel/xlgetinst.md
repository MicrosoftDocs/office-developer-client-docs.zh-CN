---
title: xlGetInst
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlGetInst
keywords:
- xlgetinst 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 631a8f4e-ea7c-4743-9ee1-b2233fd7d98d
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e113ddbf55e2b4651d578549802c44e2c6413a18
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428128"
---
# <a name="xlgetinst"></a>xlGetInst

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
返回当前调用 DLL Microsoft Excel实例的实例句柄。
  
```cs
Excel4(xlGetInst, LPXLOPER pxRes, 0); /* returns low part only */
Excel12(xlGetInst, LPXLOPER12 pxRes, 0); /* returns full handle */
```

## <a name="parameters"></a>参数

此函数没有参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

**xltypeInt (将**) **val.w** 字段中。 
  
## <a name="remarks"></a>备注

此函数可用于区分调用 DLL 的 Excel实例。
  
使用 Excel4 或[Excel4v](excel4-excel12.md)调用此函数时，返回的 XLOPER 整数变量是一个有符号的 16 位短整型整数。 [](excel4v-excel12v.md)这只能包含 32 位句柄的低 16 Windows位。 从 Excel 2007 开始 **，XLOPER12** 的整数变量是一个已签名的 32 位 int，因此包含整个句柄，无需重新访问所有打开的窗口。 
  
> [!IMPORTANT]
> 如果 **xlGetInst** 函数与 64 位版本的 Microsoft Excel一起使用，该函数将失败。 这是因为 **xltypeInt** 值类型不够宽，无法容纳由 Excel返回的 64 位长句柄。 为此，Excel 2010 引入了名为[xlGetInstPtr](xlgetinstptr.md)的新函数，该函数在 32 位和 64 位版本的 Excel 中均正常运行。 
  
## <a name="example"></a>示例

下面的示例将最后一个调用该副本的 Excel 实例与调用它的Excel副本进行比较。 如果二者相同，则返回 1;如果没有，则返回 0;如果函数失败，则返回 -1。
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlGetInstExample(void)
{
    XLOPER12 xRes;
    static HANDLE hOld = 0;
    short iRet;
    if (Excel12(xlGetInst, &xRes, 0) != xlretSuccess)
        iRet = -1;
    else
    {
    HANDLE hNew;
    hNew = (HANDLE)xRes.val.w;
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



[xlGetHwnd](xlgethwnd.md)
  
[xlGetInstPtr](xlgetinstptr.md)


[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

