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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 08bde61573874c137b18856fd24d23b324a35328
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424796"
---
# <a name="debugprintf"></a><span data-ttu-id="11a73-104">debugPrintf</span><span class="sxs-lookup"><span data-stu-id="11a73-104">debugPrintf</span></span>

<span data-ttu-id="11a73-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="11a73-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="11a73-106">通过 Windows SDK 函数 **OutputDebugStringA** 将以 null 结尾的字节字符串写入活动调试程序的框架库函数。</span><span class="sxs-lookup"><span data-stu-id="11a73-106">Framework library function that writes a null-terminated byte-string to the active debugger via the Windows SDK function **OutputDebugStringA**.</span></span> <span data-ttu-id="11a73-107">如果应用程序没有调试器，则系统调试程序将显示字符串。</span><span class="sxs-lookup"><span data-stu-id="11a73-107">If the application has no debugger, the system debugger displays the string.</span></span> <span data-ttu-id="11a73-108">如果应用程序没有调试器并且系统调试程序不活动， **则 debugPrintf 不** 执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="11a73-108">If the application has no debugger and the system debugger is not active, **debugPrintf** does nothing.</span></span> 
  
<span data-ttu-id="11a73-109">此函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="11a73-109">This function does not return a value.</span></span>
  
```cs
void WINAPI debugPrintf(LPSTR lpFormat, arguments);
```

## <a name="parameters"></a><span data-ttu-id="11a73-110">参数</span><span class="sxs-lookup"><span data-stu-id="11a73-110">Parameters</span></span>

 <span data-ttu-id="11a73-111">_lpFormat (LPSTR)_</span><span class="sxs-lookup"><span data-stu-id="11a73-111">_lpFormat (LPSTR)_</span></span>
  
<span data-ttu-id="11a73-112">格式字符串，遵循用于 **sprintf** 函数的语法和规则。</span><span class="sxs-lookup"><span data-stu-id="11a73-112">The format string, which follows the syntax and rules for that used with the **sprintf** function.</span></span> 
  
 <span data-ttu-id="11a73-113">_arguments_</span><span class="sxs-lookup"><span data-stu-id="11a73-113">_arguments_</span></span>
  
<span data-ttu-id="11a73-114">匹配格式字符串的零个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="11a73-114">Zero or more arguments to match the format string.</span></span>
  
## <a name="example"></a><span data-ttu-id="11a73-115">示例</span><span class="sxs-lookup"><span data-stu-id="11a73-115">Example</span></span>

<span data-ttu-id="11a73-116">此函数打印一个字符串，以显示控件已传递给它。</span><span class="sxs-lookup"><span data-stu-id="11a73-116">This function prints a string to show that control was passed to it.</span></span> <span data-ttu-id="11a73-117">编译_DEBUG必须定义该标志，否则此函数不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="11a73-117">The _DEBUG flag must be defined before compiling or else this function does nothing.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="11a73-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11a73-118">See also</span></span>



[<span data-ttu-id="11a73-119">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="11a73-119">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

