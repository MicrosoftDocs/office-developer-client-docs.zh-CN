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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9408a7938927214802935e54ec8e53b1469e5016
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408570"
---
# <a name="quitframework"></a><span data-ttu-id="5b335-104">QuitFramework</span><span class="sxs-lookup"><span data-stu-id="5b335-104">QuitFramework</span></span>

 <span data-ttu-id="5b335-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b335-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="5b335-106">取消初始化框架库的框架库函数，只需重新初始化临时 **XLOPER** /  **XLOPER12** 内存数据结构，从而释放已分配的任何内存。</span><span class="sxs-lookup"><span data-stu-id="5b335-106">Framework library function that uninitializes the Framework library, which simply re-initializes the temporary **XLOPER**/ **XLOPER12** memory data structures, freeing any memory that has already been allocated.</span></span> 
  
```cs
short WINAPI QuitFramework(void);
```

## <a name="parameters"></a><span data-ttu-id="5b335-107">参数</span><span class="sxs-lookup"><span data-stu-id="5b335-107">Parameters</span></span>

<span data-ttu-id="5b335-108">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="5b335-108">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5b335-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="5b335-109">Property value/Return value</span></span>

<span data-ttu-id="5b335-110">此函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="5b335-110">This function does not return a value.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b335-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b335-111">See also</span></span>



[<span data-ttu-id="5b335-112">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="5b335-112">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

