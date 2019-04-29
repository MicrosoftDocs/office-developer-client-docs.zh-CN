---
title: xlGetInstPtr
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a166f39c-f10b-4e56-8b5d-e6a54ee08c8f
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: fd4b4ad5bf52f29384ef7e0ba738c350189f471e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405280"
---
# <a name="xlgetinstptr"></a>xlGetInstPtr

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
返回当前正在调用 DLL 的 Microsoft Excel 实例的实例句柄。
  
```cs
Excel4(xlGetInstPtr, LPXLOPER pxRes, 0);Excel12(xlGetInstPtr, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a>参数

此函数没有参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

实例句柄 (**xltypeBigData**) 将位于**bigdata**字段中。 
  
## <a name="remarks"></a>说明

此函数可用于区分调用 DLL 的 Excel 的多个运行实例。
  
此函数将返回包含32位和64位版本的 Excel 的正确值。 它在 excel 2010 中引入, 作为[xlGetInst](xlgetinst.md)函数的扩展, 它只能在32位版本的 Excel 中正常运行。 
  
在使用 API 回调函数的[Excel4 和 Excel12](excel4-excel12.md)种类的情况调用此函数时, 该函数将正常运行, 因为**XLOPER**和**XLOPER12**都具有支持**xltypeBigData**值的相同结构类型. 
  
## <a name="example"></a>示例

下面的示例将调用它的 excel 的最后一个副本的实例与调用它的 excel 的当前副本进行比较。 如果它们相同, 则返回 1; 否则返回1。如果不是, 则返回 0;如果函数失败, 则返回-1。 此示例适用于32位和64位版本的 Excel。
  
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

