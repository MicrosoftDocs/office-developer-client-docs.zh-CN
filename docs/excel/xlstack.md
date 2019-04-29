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
  
检查堆栈中剩余的空间量。
  
```cs
Excel12(xlStack, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回堆栈中剩余的字节数 (**xltypeInt**)。
  
## <a name="remarks"></a>说明

最新版本的可用堆栈空间量溢出**XLOPER**的16位带符号整数。 这意味着, 当使用**XLOPER**s 和**Excel4**或**Excel4v**调用时, **xlStack**可以返回介于-32767 和32768之间的值。 若要在这种情况下获取正确的值, 必须将返回的值转换为无符号的短整型值。
  
从 Excel 2007 开始, 应使用**XLOPER12**s 和**Excel12**或**Excel12v**调用此函数, 在这种情况下, 返回的值是可用的堆栈空间量或 64 KB (以较低者为准)。
  
Excel 在堆栈上的空间量有限, 应注意不要使此空间溢出。 永远不要将非常大的数据结构放在堆栈上, 并将任意多个局部变量作为可能的静态变量。 避免以递归方式调用函数, 因为这将迅速填满堆栈。
  
如果您怀疑您正在 overrunning 堆栈, 请经常调用此函数以查看剩余的堆栈空间量。
  
## <a name="example"></a>示例

第一个示例显示一条警告消息, 其中包含剩余的堆栈空间量, 包含`\SAMPLES\EXAMPLE\EXAMPLE.C`在中。 第二个示例执行相同的操作, 使用**XLOPER**s 且不包含在 SDK 示例代码中。
  
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

