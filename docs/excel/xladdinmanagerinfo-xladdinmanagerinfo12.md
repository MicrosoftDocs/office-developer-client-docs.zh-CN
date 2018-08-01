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
ms.openlocfilehash: e42cca809c4426ddf9a98b3b275d08490d31c8db
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773819"
---
# <a name="xladdinmanagerinfoxladdinmanagerinfo12"></a>xlAddInManagerInfo/xlAddInManagerInfo12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
由 Microsoft Excel 加载项管理器调用 Excel 会话中第一次时调用。 此函数用于外接程序经理提供有关加载项的信息。
  
如果导出 XLL，Excel 2007 和更高版本调用**xlAddInManagerInfo12**优先于**xlAddInManagerInfo** 。 **XlAddInManagerInfo12**函数应从事方式相同**xlAddInManagerInfo**以避免 XLL 的行为的特定于版本的差异。 Excel 希望**xlAddInManagerInfo12**返回**XLOPER12**数据类型，而**xlAddInManagerInfo**应返回**XLOPER**。
  
因为这些不支持**XLOPER12**早于 Excel 2007 版本的 Excel 不调用**xlAddInManagerInfo12**函数。
  
Excel 不需要 XLL 实施和导出其中任一函数。
  
```cs
LPXLOPER WINAPI xlAddInManagerInfo(LPXLOPER pxAction);
LPXLOPER12 WINAPI xlAddInManagerInfo12(LPXLOPER12 pxAction);
```

## <a name="parameters"></a>参数

 _pxAction:_ 指向 （**xltypeInt**或**xltypeNum**） 数字**XLOPER/XLOPER12**的指针。
  
Excel 要求的信息。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果_pxAction_ ，或可以强制为，数字 1，此函数的实现应返回包含一些有关外接程序、 通常其名称和可能的版本号的字符串。 否则，它应返回 #VALUE ！。 
  
如果不返回一个字符串，Excel 会尝试将返回的值转换为字符串。
  
## <a name="remarks"></a>说明

如果返回的字符串指向动态分配缓冲区，您必须确保最终释放的此缓冲区。 如果该字符串由 Excel 分配，您需要执行此操作通过设置**xlbitXLFree**。 如果字符串已分配 DLL，设置**xlbitDLLFree**，通过实现此目的，您还必须实现[xlAutoFree](xlautofree-xlautofree12.md) （如果您返回**XLOPER**） 或**xlAutoFree12**中 （如果您返回**XLOPER12**）。
  
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

