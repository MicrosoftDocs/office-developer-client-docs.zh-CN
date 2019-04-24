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
ms.openlocfilehash: e113ddbf55e2b4651d578549802c44e2c6413a18
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303848"
---
# <a name="xlgetinst"></a>xlGetInst

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
返回当前正在调用 DLL 的 Microsoft Excel 实例的实例句柄。
  
```cs
Excel4(xlGetInst, LPXLOPER pxRes, 0); /* returns low part only */
Excel12(xlGetInst, LPXLOPER12 pxRes, 0); /* returns full handle */
```

## <a name="parameters"></a>参数

此函数没有参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

实例句柄 (**xltypeInt**) 将位于 " **w** " 字段中。 
  
## <a name="remarks"></a>注解

此函数可用于区分调用 DLL 的 Excel 的多个运行实例。
  
使用[Excel4](excel4-excel12.md)或[Excel4v](excel4v-excel12v.md)调用此函数时, 返回的 XLOPER 整数变量是带符号的16位短整型。这只能包含32位 Windows 句柄的低16位。 从 Excel 2007 开始, **XLOPER12**的整数变量是一个有符号的32位 int, 因此包含整个句柄, 从而消除了对所有打开的窗口进行迭代的需求。 
  
> [!IMPORTANT]
> 如果将**xlGetInst**函数与64位版本的 Microsoft Excel 一起使用, 则函数将失败。 这是因为**xltypeInt**值类型的宽度不足以容纳 Excel 在这种情况下返回的64位长句柄。 为了实现此目的, excel 2010 引入了一个名为[xlGetInstPtr](xlgetinstptr.md)的新函数, 该函数可以使用32位和64位版本的 Excel 来正常运行。 
  
## <a name="example"></a>示例

下面的示例将调用它的 excel 的最后一个副本的实例与调用它的 excel 的当前副本进行比较。 如果它们相同, 则返回 1; 否则返回1。如果不是, 则返回 0;如果函数失败, 则返回-1。
  
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

