---
title: C API 回调函数 Excel4、Excel12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- functions [excel 2007]， c api callback
localization_priority: Normal
ms.assetid: 0f3ae86d-329a-4177-a65b-6288c248297e
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5fe5eb7486f12d75ce7e42ad57141480ec735c54
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434429"
---
# <a name="c-api-callback-functions-excel4-excel12"></a><span data-ttu-id="87bdf-104">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="87bdf-104">C API Callback Functions Excel4, Excel12</span></span>

<span data-ttu-id="87bdf-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="87bdf-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="87bdf-106">**提供了 Excel4** 和 **Excel12** 函数以使 DLL 能够调用内部 Microsoft Excel 工作表函数、宏工作表函数或命令，或仅 XLL 的特殊函数或命令。</span><span class="sxs-lookup"><span data-stu-id="87bdf-106">The **Excel4** and **Excel12** functions are provided to enable DLLs to call an internal Microsoft Excel worksheet function, macro sheet function or command, or XLL-only special function or command.</span></span> <span data-ttu-id="87bdf-107">所有最新版本的 Excel都支持 **Excel4** 函数。</span><span class="sxs-lookup"><span data-stu-id="87bdf-107">All recent versions of Excel support the **Excel4** function.</span></span> <span data-ttu-id="87bdf-108">从 2007 Excel **开始，支持 Excel12** 函数。</span><span class="sxs-lookup"><span data-stu-id="87bdf-108">Starting in Excel 2007 the **Excel12** function is supported.</span></span> <span data-ttu-id="87bdf-109">这两种函数以两种形式提供：</span><span class="sxs-lookup"><span data-stu-id="87bdf-109">Both functions are provided in two forms:</span></span> 
  
- <span data-ttu-id="87bdf-110">**Excel4/Excel12 (长度参数列表**) </span><span class="sxs-lookup"><span data-stu-id="87bdf-110">A variable-length argument list form (**Excel4/Excel12**)</span></span>
    
- <span data-ttu-id="87bdf-111">**Excel4v/Excel12v (参数数组)**</span><span class="sxs-lookup"><span data-stu-id="87bdf-111">An array-of-arguments form (**Excel4v/Excel12v**)</span></span>
    
<span data-ttu-id="87bdf-112">除了将参数传递给这些回调的方式之外，这两种形式在功能上是等效的。</span><span class="sxs-lookup"><span data-stu-id="87bdf-112">Except for the way in which arguments are passed to these callbacks, the two forms are functionally equivalent.</span></span> <span data-ttu-id="87bdf-113">[Excel4/Excel12](excel4-excel12.md)中完全描述了这两种表单的基本概念。</span><span class="sxs-lookup"><span data-stu-id="87bdf-113">The basic concepts for both forms are fully described in [Excel4/Excel12](excel4-excel12.md).</span></span> <span data-ttu-id="87bdf-114">[Excel4v/Excel12v](excel4v-excel12v.md) 涵盖了有关此表单的其他问题。</span><span class="sxs-lookup"><span data-stu-id="87bdf-114">[Excel4v/Excel12v](excel4v-excel12v.md) covers other issues about this form.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="87bdf-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="87bdf-115">In this section</span></span>

[<span data-ttu-id="87bdf-116">Excel4/Excel12</span><span class="sxs-lookup"><span data-stu-id="87bdf-116">Excel4/Excel12</span></span>](excel4-excel12.md)
  
[<span data-ttu-id="87bdf-117">Excel4v/Excel12v</span><span class="sxs-lookup"><span data-stu-id="87bdf-117">Excel4v/Excel12v</span></span>](excel4v-excel12v.md)
  

