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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 08bde61573874c137b18856fd24d23b324a35328
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311002"
---
# <a name="debugprintf"></a><span data-ttu-id="4ecad-104">debugPrintf</span><span class="sxs-lookup"><span data-stu-id="4ecad-104">debugPrintf</span></span>

<span data-ttu-id="4ecad-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4ecad-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="4ecad-106">通过 Windows SDK 函数**OutputDebugStringA**将以 null 结尾的字节字符串写入活动调试器的框架库函数。</span><span class="sxs-lookup"><span data-stu-id="4ecad-106">Framework library function that writes a null-terminated byte-string to the active debugger via the Windows SDK function **OutputDebugStringA**.</span></span> <span data-ttu-id="4ecad-107">如果应用程序没有调试器, 系统调试器将显示字符串。</span><span class="sxs-lookup"><span data-stu-id="4ecad-107">If the application has no debugger, the system debugger displays the string.</span></span> <span data-ttu-id="4ecad-108">如果应用程序没有调试器且系统调试器未处于活动状态, 则**debugPrintf**不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="4ecad-108">If the application has no debugger and the system debugger is not active, **debugPrintf** does nothing.</span></span> 
  
<span data-ttu-id="4ecad-109">此函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="4ecad-109">This function does not return a value.</span></span>
  
```cs
void WINAPI debugPrintf(LPSTR lpFormat, arguments);
```

## <a name="parameters"></a><span data-ttu-id="4ecad-110">参数</span><span class="sxs-lookup"><span data-stu-id="4ecad-110">Parameters</span></span>

 <span data-ttu-id="4ecad-111">_lpFormat (LPSTR)_</span><span class="sxs-lookup"><span data-stu-id="4ecad-111">_lpFormat (LPSTR)_</span></span>
  
<span data-ttu-id="4ecad-112">格式字符串, 遵循与**sprintf**函数一起使用的语法和规则。</span><span class="sxs-lookup"><span data-stu-id="4ecad-112">The format string, which follows the syntax and rules for that used with the **sprintf** function.</span></span> 
  
 <span data-ttu-id="4ecad-113">_自_</span><span class="sxs-lookup"><span data-stu-id="4ecad-113">_arguments_</span></span>
  
<span data-ttu-id="4ecad-114">与格式字符串匹配的零个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="4ecad-114">Zero or more arguments to match the format string.</span></span>
  
## <a name="example"></a><span data-ttu-id="4ecad-115">示例</span><span class="sxs-lookup"><span data-stu-id="4ecad-115">Example</span></span>

<span data-ttu-id="4ecad-116">此函数打印字符串以显示该控件已传递给它。</span><span class="sxs-lookup"><span data-stu-id="4ecad-116">This function prints a string to show that control was passed to it.</span></span> <span data-ttu-id="4ecad-117">必须在编译之前定义 _debug 标志, 否则此函数将不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="4ecad-117">The _DEBUG flag must be defined before compiling or else this function does nothing.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="4ecad-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ecad-118">See also</span></span>



[<span data-ttu-id="4ecad-119">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="4ecad-119">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

