---
title: InitFramework
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- InitFramework
keywords:
- initframework 函数 [excel 2007]
localization_priority: Normal
ms.assetid: c472a14a-92a6-46f6-924c-db8d6199d6fb
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 2d7e3286d794d6f21da9ef83ca44d18ec242c063
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773748"
---
# <a name="initframework"></a><span data-ttu-id="d301d-104">InitFramework</span><span class="sxs-lookup"><span data-stu-id="d301d-104">InitFramework</span></span>

 <span data-ttu-id="d301d-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d301d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d301d-106">初始化 Framework 库中，只需初始化临时**XLOPER**的框架库函数/ **XLOPER12**内存数据结构，释放任何已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="d301d-106">Framework library function that initializes the Framework library, which simply initializes the temporary **XLOPER**/ **XLOPER12** memory data structures, freeing any memory that has already been allocated.</span></span> 
  
```cs
short WINAPI InitFramework(void);
```

## <a name="parameters"></a><span data-ttu-id="d301d-107">参数</span><span class="sxs-lookup"><span data-stu-id="d301d-107">Parameters</span></span>

<span data-ttu-id="d301d-108">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="d301d-108">This function takes no arguments.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="d301d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d301d-109">Return value</span></span>

<span data-ttu-id="d301d-110">此函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="d301d-110">This function does not return a value.</span></span>
  
## <a name="example"></a><span data-ttu-id="d301d-111">示例</span><span class="sxs-lookup"><span data-stu-id="d301d-111">Example</span></span>

<span data-ttu-id="d301d-112">本示例使用**InitFramework**函数释放所有临时内存。</span><span class="sxs-lookup"><span data-stu-id="d301d-112">This example uses the **InitFramework** function to free all temporary memory.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI InitFrameworkExample(void)
{
    InitFramework();
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="d301d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d301d-113">See also</span></span>



[<span data-ttu-id="d301d-114">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="d301d-114">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

