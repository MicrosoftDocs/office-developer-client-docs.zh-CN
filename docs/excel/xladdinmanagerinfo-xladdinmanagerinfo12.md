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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 66d2ac05b9603d6bb587a3898bde2545c1bb844a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407793"
---
# <a name="xladdinmanagerinfoxladdinmanagerinfo12"></a>xlAddInManagerInfo/xlAddInManagerInfo12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
当Microsoft Excel会话中首次调用加载项管理器时，由 Excel 调用。 此函数用于向Add-In管理员提供有关您的外接程序的信息。
  
Excel 2007 及更高版本调用 **xlAddInManagerInfo12，** 如果由 XLL 导出，将优先调用 **xlAddInManagerInfo。** **xlAddInManagerInfo12** 函数的运行方式应该与 **xlAddInManagerInfo** 相同，以避免 XLL 行为中特定于版本的差异。 Excel **xlAddInManagerInfo12** 返回 **XLOPER12** 数据类型，而 **xlAddInManagerInfo** 应返回 **XLOPER**。
  
**xlAddInManagerInfo12** 函数不是由 Excel 2007 Excel之前的版本调用的，这些版本不支持 **XLOPER12**。
  
Excel不需要 XLL 来实现和导出其中任一函数。
  
```cs
LPXLOPER WINAPI xlAddInManagerInfo(LPXLOPER pxAction);
LPXLOPER12 WINAPI xlAddInManagerInfo12(LPXLOPER12 pxAction);
```

## <a name="parameters"></a>参数

 _pxAction：_ 指向数值 **XLOPER/XLOPER12** (**xltypeInt** 或 **xltypeNum**) 。
  
用户Excel的信息。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果  _pxAction_ 是数字 1，或可以强制转换为数字 1，则此函数的实现应返回一个字符串，其中包含有关外接程序的一些信息，通常是其名称和版本号。 否则，它应返回 #VALUE！。 
  
如果不返回字符串，则Excel尝试将返回的值转换为字符串。
  
## <a name="remarks"></a>备注

如果返回的字符串指向动态分配的缓冲区，则必须确保最终释放此缓冲区。 如果字符串是由 Excel分配的，则通过设置 **xlbitXLFree 来这样做**。 如果字符串是由 DLL 分配的，则通过设置 **xlbitDLLFree** 来实现这一点，如果要返回 **XLOPER** () 或 **xlAutoFree12** (则还必须在 [xlAutoFree](xlautofree-xlautofree12.md)) 中实现。 
  
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

