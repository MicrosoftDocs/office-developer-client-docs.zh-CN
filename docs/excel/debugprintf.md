---
title: debugPrintf
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- debugPrintf
keywords:
- debugprintf 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 9ad541f6-0b35-4f50-926a-8940e3f8033a
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 25669cfc705e797b80be0fab590d809e8f1e3b5c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773638"
---
# <a name="debugprintf"></a><span data-ttu-id="37fb4-104">debugPrintf</span><span class="sxs-lookup"><span data-stu-id="37fb4-104">debugPrintf</span></span>

<span data-ttu-id="37fb4-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="37fb4-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="37fb4-106">Null 结尾字节字符串写入 Windows SDK 函数**OutputDebugStringA**通过活动的调试器 framework 库函数。</span><span class="sxs-lookup"><span data-stu-id="37fb4-106">Framework library function that writes a null-terminated byte-string to the active debugger via the Windows SDK function **OutputDebugStringA**.</span></span> <span data-ttu-id="37fb4-107">如果应用程序不有任何调试器，系统将调试器将显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="37fb4-107">If the application has no debugger, the system debugger displays the string.</span></span> <span data-ttu-id="37fb4-108">如果应用程序都有任何调试器和系统调试未处于活动状态，则**debugPrintf**无实际作用。</span><span class="sxs-lookup"><span data-stu-id="37fb4-108">If the application has no debugger and the system debugger is not active, **debugPrintf** does nothing.</span></span> 
  
<span data-ttu-id="37fb4-109">此函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="37fb4-109">This function does not return a value.</span></span>
  
```cs
void WINAPI debugPrintf(LPSTR lpFormat, arguments);
```

## <a name="parameters"></a><span data-ttu-id="37fb4-110">参数</span><span class="sxs-lookup"><span data-stu-id="37fb4-110">Parameters</span></span>

 <span data-ttu-id="37fb4-111">_lpFormat (LPSTR)_</span><span class="sxs-lookup"><span data-stu-id="37fb4-111">_lpFormat (LPSTR)_</span></span>
  
<span data-ttu-id="37fb4-112">下面的语法和规则的与**sprintf**函数一起使用的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="37fb4-112">The format string, which follows the syntax and rules for that used with the **sprintf** function.</span></span> 
  
 <span data-ttu-id="37fb4-113">_参数_</span><span class="sxs-lookup"><span data-stu-id="37fb4-113">_arguments_</span></span>
  
<span data-ttu-id="37fb4-114">要与格式字符串匹配的零个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="37fb4-114">Zero or more arguments to match the format string.</span></span>
  
## <a name="example"></a><span data-ttu-id="37fb4-115">示例</span><span class="sxs-lookup"><span data-stu-id="37fb4-115">Example</span></span>

<span data-ttu-id="37fb4-116">此函数打印显示控件已传递给它的字符串。</span><span class="sxs-lookup"><span data-stu-id="37fb4-116">This function prints a string to show that control was passed to it.</span></span> <span data-ttu-id="37fb4-117">在编译之前，必须定义 _DEBUG 标志，否则此函数不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="37fb4-117">The _DEBUG flag must be defined before compiling or else this function does nothing.</span></span>
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI debugPrintfExample(void)
{
#ifdef _DEBUG
   debugPrintf("Made it!\r");
#endif
   return 1;
}

```

## <a name="see-also"></a><span data-ttu-id="37fb4-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37fb4-118">See also</span></span>



[<span data-ttu-id="37fb4-119">Framework 库中的函数</span><span class="sxs-lookup"><span data-stu-id="37fb4-119">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

