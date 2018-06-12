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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: fcd073f7d2b97e84743d01c498435f186277e345
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773859"
---
# <a name="xlstack"></a>xlStack

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
检查堆栈中的剩余空间量。
  
```cs
Excel12(xlStack, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a>参数

此函数不采用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回的字节数 (**xltypeInt**) 保持堆栈。
  
## <a name="remarks"></a>备注

最新版本的可用堆栈空间量溢出**XLOPER**16 位有符号的整数。 这意味着该**xlStack**可-32767 之间 32768 调用使用**XLOPER**s 和**Excel4**或**Excel4v**时返回的值。 若要在这种情况下获取正确的值，必须转换为无符号短返回的值。
  
在 Excel 2007 中，您应调用此函数使用**XLOPER12**s 和**Excel12**或**Excel12v**，在其中 case 返回的值是可用的堆栈空间量或 64 KB，无论哪个都有启动。
  
Excel 在堆栈，限制的空间量，您应注意不要溢出此空间。 从不将非常大的数据结构置于堆栈，并尽可能静态使任意数量的本地变量。 避免调用函数以递归方式，因为它会迅速填满堆栈。
  
如果您怀疑您致使溢出堆栈，调用此函数经常可看到剩余堆栈空间。
  
## <a name="example"></a>示例

第一个示例显示包含堆栈空间剩余的一条警告消息，并包含在`\SAMPLES\EXAMPLE\EXAMPLE.C`。 第二个示例执行同样的任务，使用**XLOPER**s，并且未包含在 SDK 示例代码。
  
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

