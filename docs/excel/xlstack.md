---
title: xlStack
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlStack
keywords:
- xlstack 函数 [excel 2007]
localization_priority: Normal
ms.assetid: f9f030e8-1ec9-4cbf-92e1-360526260916
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 55ceed93407b1d99e05bc20fb6ce0b22459de7df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429977"
---
# <a name="xlstack"></a>xlStack

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
检查堆栈上留下的空间量。
  
```cs
Excel12(xlStack, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回堆栈上 (**xltypeInt)** 字节数。
  
## <a name="remarks"></a>备注

最新版本的可用堆栈空间量会溢出 **XLOPER** 的 16 位有符号整数。 这意味着在使用 **XLOPER** s 和 Excel4 或 **Excel4v** 调用 **xlStack** 时，可能会返回 -32767 和 32768 **之间的值**。 若要在这种情况下获取正确的值，必须将返回的值强制转换到无符号短整。
  
从 Excel 2007 开始，您应使用 **XLOPER12** s 和 **Excel12** 或 **Excel12v** 调用此函数，在这种情况下，返回的值是可用的堆栈空间量或 64 KB（以较小者为准）。
  
Excel堆栈上的空间有限，你应该注意不要溢出此空间。 切勿在堆栈上放入非常大的数据结构，并且使尽可能多的本地变量静态。 避免以递归式调用函数，因为这会迅速填满堆栈。
  
如果您怀疑您溢出堆栈，请经常调用此函数以查看所剩的堆栈空间。
  
## <a name="example"></a>示例

第一个示例显示一条警报消息，其中包含左侧堆栈空间量，并包含在 中  `\SAMPLES\EXAMPLE\EXAMPLE.C` 。 第二个示例执行相同的工作，即使用 **XLOPER，** 并且不包含在 SDK 示例代码中。
  
```cs
short WINAPI xlStackExample(void)
{
   XLOPER12 xRes;
   Excel12(xlStack, &xRes, 0);
   Excel12(xlcAlert, 0, 1, (LPXLOPER12)&xRes);
   return 1;
} 
short int WINAPI xlStackExample_XLOPER(void)
{
    XLOPER xRes;
    Excel4(xlStack, (LPXLOPER)&xRes, 0);
    xRes.xltype = xltypeNum; // Change the type to double
    // Cast to an unsigned short to get rid of the overflow problem
    xRes.val.num = (double)(unsigned short) xRes.val.w;
    Excel4(xlcAlert, 0, 1, (LPXLOPER)& xRes);
    return 1;
}
```

## <a name="see-also"></a>另请参阅

- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

