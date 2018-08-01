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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9484f7bbc1f5e0fc5b0def17f2ce79ef226dcd17
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773851"
---
# <a name="xlgetinst"></a>xlGetInst

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
返回当前正在呼叫 DLL 的 Microsoft Excel 实例的实例句柄。
  
```cs
Excel4(xlGetInst, LPXLOPER pxRes, 0); /* returns low part only */
Excel12(xlGetInst, LPXLOPER12 pxRes, 0); /* returns full handle */
```

## <a name="parameters"></a>参数

此函数具有任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

在**val.w**字段将实例句柄 (**xltypeInt**)。 
  
## <a name="remarks"></a>说明

用于区分多个运行实例 Excel 的 DLL 调用此函数。
  
返回的 XLOPER integer 变量时要调用此函数使用[Excel4](excel4-excel12.md)或[Excel4v](excel4v-excel12v.md)，为签名的 16 位短 int。这是只可以包含低 16 位的 32 位 Windows 句柄。 从 Excel 2007 开始， **XLOPER12**整数变量是带符号的 32 位 int 和因此包含整个窗口的句，而不必循环访问所有打开的窗口。 
  
> [!IMPORTANT]
> 如果与 64 位版本的 Microsoft Excel 使用**xlGetInst**函数，则将失败函数。 这是因为**xltypeInt**值类型不宽到足以容纳在这种情况下返回 Excel 的 64 位长句柄。 为此，Excel 2010 引入了新的函数名为[xlGetInstPtr](xlgetinstptr.md)，与 Excel 的 32 位和 64 位版本正确运行。 
  
## <a name="example"></a>示例

下面的示例将实例调用于调用它的 Excel 的当前副本的 Excel 的最后一个副本进行比较。 如果它们是相同的则将返回 1;如果没有，则返回 0;如果函数失败，则返回-1。
  
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

