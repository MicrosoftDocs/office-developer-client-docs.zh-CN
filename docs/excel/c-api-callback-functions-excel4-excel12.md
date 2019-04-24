---
title: C API 回调函数 Excel4、Excel12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 函数 [excel 2007], c api 回调
localization_priority: Normal
ms.assetid: 0f3ae86d-329a-4177-a65b-6288c248297e
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5fe5eb7486f12d75ce7e42ad57141480ec735c54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304177"
---
# <a name="c-api-callback-functions-excel4-excel12"></a><span data-ttu-id="926c6-104">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="926c6-104">C API Callback Functions Excel4, Excel12</span></span>

<span data-ttu-id="926c6-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="926c6-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="926c6-106">提供**Excel4**和**Excel12**函数以使 dll 能够调用内部 Microsoft Excel 工作表函数、宏工作表函数或命令, 或仅 XLL 特殊函数或命令。</span><span class="sxs-lookup"><span data-stu-id="926c6-106">The **Excel4** and **Excel12** functions are provided to enable DLLs to call an internal Microsoft Excel worksheet function, macro sheet function or command, or XLL-only special function or command.</span></span> <span data-ttu-id="926c6-107">Excel 的所有最新版本都支持**Excel4**函数。</span><span class="sxs-lookup"><span data-stu-id="926c6-107">All recent versions of Excel support the **Excel4** function.</span></span> <span data-ttu-id="926c6-108">在 Excel 2007 中启动支持**Excel12**函数。</span><span class="sxs-lookup"><span data-stu-id="926c6-108">Starting in Excel 2007 the **Excel12** function is supported.</span></span> <span data-ttu-id="926c6-109">这两个函数都以两种形式提供:</span><span class="sxs-lookup"><span data-stu-id="926c6-109">Both functions are provided in two forms:</span></span> 
  
- <span data-ttu-id="926c6-110">可变长度参数列表表单 (**Excel4/Excel12**)</span><span class="sxs-lookup"><span data-stu-id="926c6-110">A variable-length argument list form (**Excel4/Excel12**)</span></span>
    
- <span data-ttu-id="926c6-111">参数数组形式 (**Excel4v/Excel12v**)</span><span class="sxs-lookup"><span data-stu-id="926c6-111">An array-of-arguments form (**Excel4v/Excel12v**)</span></span>
    
<span data-ttu-id="926c6-112">除了将参数传递给这些回调的方式外, 这两个窗体在功能上是等效的。</span><span class="sxs-lookup"><span data-stu-id="926c6-112">Except for the way in which arguments are passed to these callbacks, the two forms are functionally equivalent.</span></span> <span data-ttu-id="926c6-113">[Excel4/Excel12](excel4-excel12.md)中完全介绍了这两种形式的基本概念。</span><span class="sxs-lookup"><span data-stu-id="926c6-113">The basic concepts for both forms are fully described in [Excel4/Excel12](excel4-excel12.md).</span></span> <span data-ttu-id="926c6-114">[Excel4v/Excel12v](excel4v-excel12v.md)涵盖有关此窗体的其他问题。</span><span class="sxs-lookup"><span data-stu-id="926c6-114">[Excel4v/Excel12v](excel4v-excel12v.md) covers other issues about this form.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="926c6-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="926c6-115">In this section</span></span>

[<span data-ttu-id="926c6-116">Excel4/Excel12</span><span class="sxs-lookup"><span data-stu-id="926c6-116">Excel4/Excel12</span></span>](excel4-excel12.md)
  
[<span data-ttu-id="926c6-117">Excel4v/Excel12v</span><span class="sxs-lookup"><span data-stu-id="926c6-117">Excel4v/Excel12v</span></span>](excel4v-excel12v.md)
  

