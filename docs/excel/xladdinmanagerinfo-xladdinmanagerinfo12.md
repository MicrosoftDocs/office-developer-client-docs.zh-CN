---
title: xlAddInManagerInfo/xlAddInManagerInfo12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAddInManagerInfo
keywords:
- xladdinmanagerinfo 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 63a73cd2-6479-4233-ad68-93379f940717
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 66d2ac05b9603d6bb587a3898bde2545c1bb844a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303994"
---
# <a name="xladdinmanagerinfoxladdinmanagerinfo12"></a>xlAddInManagerInfo/xlAddInManagerInfo12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
在 excel 会话中首次调用外接程序管理器时, 由 Microsoft Excel 调用。 此函数用于向外接程序管理器提供有关外接程序的信息。
  
如果 XLL 导出了 Excel 2007 及更高版本, 则将首选项中的**xlAddInManagerInfo12**调用**xlAddInManagerInfo** 。 **xlAddInManagerInfo12**函数应以与**xlAddInManagerInfo**相同的方式工作, 以避免 XLL 行为中特定于版本的差异。 Excel 要求**xlAddInManagerInfo12**返回**XLOPER12**数据类型, 而**xlAddInManagerInfo**应返回一个**XLOPER**。
  
excel 2007 之前的 excel 版本不会调用**xlAddInManagerInfo12**函数, 因为它们不支持**XLOPER12**。
  
Excel 不需要 XLL 即可实现和导出这两个函数中的任何一个。
  
```cs
LPXLOPER WINAPI xlAddInManagerInfo(LPXLOPER pxAction);
LPXLOPER12 WINAPI xlAddInManagerInfo12(LPXLOPER12 pxAction);
```

## <a name="parameters"></a>参数

 _pxAction:_ 指向数字**XLOPER/XLOPER12** (**xltypeInt**或**xltypeNum**) 的指针。
  
Excel 所要求的信息。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果_pxAction_为或可以强制为数字 1, 则此函数的实现应返回一个字符串, 其中包含有关外接程序的一些信息, 通常是它的名称, 也可能是版本号。 否则, 它应返回 #VALUE!。 
  
如果不返回字符串, Excel 将尝试将返回的值转换为字符串。
  
## <a name="remarks"></a>注解

如果返回的字符串指向动态分配的缓冲区, 则必须确保最终释放此缓冲区。 如果该字符串是由 Excel 分配的, 则可以通过设置**xlbitXLFree**来执行此操作。 如果该字符串是由 DLL 分配的, 则可以通过设置**xlbitDLLFree**来执行此操作, 此外, 还必须在[xlAutoFree](xlautofree-xlautofree12.md)中实现 (如果要返回**XLOPER**) 或**xlAutoFree12** (如果要返回**XLOPER12**)。
  
## <a name="example"></a>示例

 `\SAMPLES\GENERIC\GENERIC.C`
  
```cs
LPXLOPER12 WINAPI xlAddInManagerInfo12(LPXLOPER12 xAction)
{
    static XLOPER12 xInfo, xIntAction;
/*
** This code coerces the passed-in value to an integer. This is how the
** code determines what is being requested. If it receives a 1, it returns a
** string representing the long name. If it receives anything else, it
** returns a #VALUE! error.
*/
    Excel12f(xlCoerce, &xIntAction, 2, xAction, TempInt12(xltypeInt));
    if(xIntAction.val.w == 1) 
    {
        xInfo.xltype = xltypeStr;
        xInfo.val.str = L"\026Example Standalone DLL";
    }
    else 
    {
        xInfo.xltype = xltypeErr;
        xInfo.val.err = xlerrValue;
    }
// Word of caution - returning static XLOPERs/XLOPER12s is not thread safe
// for UDFs declared as thread safe. Use alternate memory allocation mechanisms.
    return (LPXLOPER12)&xInfo;
} 

```

## <a name="see-also"></a>另请参阅



[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

