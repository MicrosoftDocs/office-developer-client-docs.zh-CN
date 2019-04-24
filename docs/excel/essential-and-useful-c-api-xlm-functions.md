---
title: 基本和有用的 C API XLM 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 函数 [excel 2007], c api xlm
localization_priority: Normal
ms.assetid: dc80cb3d-0d7e-4cb9-9870-3acc84eeca82
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d6acd5bb171fb2494f2adb23584f4e7f088e1b83
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311121"
---
# <a name="essential-and-useful-c-api-xlm-functions"></a><span data-ttu-id="6f810-104">基本和有用的 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="6f810-104">Essential and Useful C API XLM Functions</span></span>

 <span data-ttu-id="6f810-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6f810-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="6f810-106">本节中介绍的函数是 Microsoft Excel 回调函数, 对于 DLL 和 XLL 开发人员尤其有用。</span><span class="sxs-lookup"><span data-stu-id="6f810-106">The functions described in this section are Microsoft Excel callback functions that are particularly useful to DLL and XLL developers.</span></span> <span data-ttu-id="6f810-107">在这些情况下, **xlfRegister**函数对于要注册其函数和命令的 xll 和 dll 是必需的, 以便可以直接从 Excel 中调用它们。</span><span class="sxs-lookup"><span data-stu-id="6f810-107">Of these, the **xlfRegister** function is essential for XLLs and DLLs that want to register their functions and commands so that they can be called directly from Excel.</span></span> <span data-ttu-id="6f810-108">函数**xlfUnregister**和**xlfSetName**结合使用, 以注销 DLL 和 XLL 函数和命令。</span><span class="sxs-lookup"><span data-stu-id="6f810-108">The functions **xlfUnregister** and **xlfSetName** are used in combination to unregister DLL and XLL functions and commands.</span></span> 
  
<span data-ttu-id="6f810-109">Excel 通过 C API 公开了许多函数, 这些函数在开发 xll 时非常有用。</span><span class="sxs-lookup"><span data-stu-id="6f810-109">Many more functions are exposed by Excel via the C API that are useful when you are developing XLLs.</span></span> <span data-ttu-id="6f810-110">它们对应于 XLM 宏工作表中提供的 Excel 工作表函数和函数和命令。</span><span class="sxs-lookup"><span data-stu-id="6f810-110">They correspond to the Excel worksheet functions and functions and commands that are available from XLM macro sheets.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="6f810-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="6f810-111">In this section</span></span>

[<span data-ttu-id="6f810-112">xlfCaller</span><span class="sxs-lookup"><span data-stu-id="6f810-112">xlfCaller</span></span>](xlfcaller.md)
  
[<span data-ttu-id="6f810-113">xlfEvaluate</span><span class="sxs-lookup"><span data-stu-id="6f810-113">xlfEvaluate</span></span>](xlfevaluate.md)
  
[<span data-ttu-id="6f810-114">xlfGetDef</span><span class="sxs-lookup"><span data-stu-id="6f810-114">xlfGetDef</span></span>](xlfgetdef.md)
  
[<span data-ttu-id="6f810-115">xlfGetName</span><span class="sxs-lookup"><span data-stu-id="6f810-115">xlfGetName</span></span>](xlfgetname.md)
  
[<span data-ttu-id="6f810-116">xlfRegister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="6f810-116">xlfRegister (Form 1)</span></span>](xlfregister-form-1.md)
  
[<span data-ttu-id="6f810-117">xlfRegister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="6f810-117">xlfRegister (Form 2)</span></span>](xlfregister-form-2.md)
  
[<span data-ttu-id="6f810-118">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="6f810-118">xlfRegisterId</span></span>](xlfregisterid.md)
  
[<span data-ttu-id="6f810-119">xlfUnregister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="6f810-119">xlfUnregister (Form 1)</span></span>](xlfunregister-form-1.md)
  
[<span data-ttu-id="6f810-120">xlfUnregister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="6f810-120">xlfUnregister (Form 2)</span></span>](xlfunregister-form-2.md)
  
[<span data-ttu-id="6f810-121">xlfSetName</span><span class="sxs-lookup"><span data-stu-id="6f810-121">xlfSetName</span></span>](xlfsetname.md)
  

