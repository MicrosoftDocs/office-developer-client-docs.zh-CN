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
ms.openlocfilehash: 34fe8f4a606956b90a0d005b0bc523cea460153f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310680"
---
# <a name="initframework"></a><span data-ttu-id="44ecd-104">InitFramework</span><span class="sxs-lookup"><span data-stu-id="44ecd-104">InitFramework</span></span>

 <span data-ttu-id="44ecd-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="44ecd-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="44ecd-106">framework library 函数, 它初始化框架库, 它只是初始化临时**XLOPER**/ **XLOPER12**内存数据结构, 释放已分配的任何内存。</span><span class="sxs-lookup"><span data-stu-id="44ecd-106">Framework library function that initializes the Framework library, which simply initializes the temporary **XLOPER**/ **XLOPER12** memory data structures, freeing any memory that has already been allocated.</span></span> 
  
```cs
short WINAPI InitFramework(void);
```

## <a name="parameters"></a><span data-ttu-id="44ecd-107">参数</span><span class="sxs-lookup"><span data-stu-id="44ecd-107">Parameters</span></span>

<span data-ttu-id="44ecd-108">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="44ecd-108">This function takes no arguments.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="44ecd-109">返回值</span><span class="sxs-lookup"><span data-stu-id="44ecd-109">Return value</span></span>

<span data-ttu-id="44ecd-110">此函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="44ecd-110">This function does not return a value.</span></span>
  
## <a name="example"></a><span data-ttu-id="44ecd-111">示例</span><span class="sxs-lookup"><span data-stu-id="44ecd-111">Example</span></span>

<span data-ttu-id="44ecd-112">此示例使用**InitFramework**函数来释放所有临时内存。</span><span class="sxs-lookup"><span data-stu-id="44ecd-112">This example uses the **InitFramework** function to free all temporary memory.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI InitFrameworkExample(void)
{
    InitFramework();
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="44ecd-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44ecd-113">See also</span></span>



[<span data-ttu-id="44ecd-114">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="44ecd-114">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

