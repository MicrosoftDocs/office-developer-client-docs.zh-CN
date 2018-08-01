---
title: QuitFramework
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- QuitFramework
keywords:
- quitframework 函数
localization_priority: Normal
ms.assetid: d17a3efe-c278-4ef1-b8f9-b958ae012361
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5c4b122b200d9de0cf098d2bc9e2fbd887ad9ff3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773805"
---
# <a name="quitframework"></a><span data-ttu-id="28830-104">QuitFramework</span><span class="sxs-lookup"><span data-stu-id="28830-104">QuitFramework</span></span>

 <span data-ttu-id="28830-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="28830-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="28830-106">取消初始化 Framework 库中，只需重新初始化临时**XLOPER**的框架库函数/ **XLOPER12**内存数据结构，释放任何已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="28830-106">Framework library function that uninitializes the Framework library, which simply re-initializes the temporary **XLOPER**/ **XLOPER12** memory data structures, freeing any memory that has already been allocated.</span></span> 
  
```cs
short WINAPI QuitFramework(void);
```

## <a name="parameters"></a><span data-ttu-id="28830-107">参数</span><span class="sxs-lookup"><span data-stu-id="28830-107">Parameters</span></span>

<span data-ttu-id="28830-108">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="28830-108">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="28830-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="28830-109">Property value/Return value</span></span>

<span data-ttu-id="28830-110">此函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="28830-110">This function does not return a value.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="28830-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28830-111">See also</span></span>



[<span data-ttu-id="28830-112">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="28830-112">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

