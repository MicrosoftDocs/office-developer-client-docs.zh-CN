---
title: 必需和有用的 C API XLM 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- functions [excel 2007]， c api xlm
localization_priority: Normal
ms.assetid: dc80cb3d-0d7e-4cb9-9870-3acc84eeca82
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d6acd5bb171fb2494f2adb23584f4e7f088e1b83
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434513"
---
# <a name="essential-and-useful-c-api-xlm-functions"></a><span data-ttu-id="a464b-104">必需和有用的 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="a464b-104">Essential and Useful C API XLM Functions</span></span>

 <span data-ttu-id="a464b-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a464b-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a464b-106">本节中介绍的函数是Microsoft Excel对 DLL 和 XLL 开发人员特别有用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="a464b-106">The functions described in this section are Microsoft Excel callback functions that are particularly useful to DLL and XLL developers.</span></span> <span data-ttu-id="a464b-107">其中 **，xlfRegister** 函数对于想要注册其函数和命令以便可以直接从 Excel 调用的 XLL 和 DLL 至关重要。</span><span class="sxs-lookup"><span data-stu-id="a464b-107">Of these, the **xlfRegister** function is essential for XLLs and DLLs that want to register their functions and commands so that they can be called directly from Excel.</span></span> <span data-ttu-id="a464b-108">函数 **xlfUnregister** 和 **xlfSetName** 用于取消注册 DLL 和 XLL 函数和命令。</span><span class="sxs-lookup"><span data-stu-id="a464b-108">The functions **xlfUnregister** and **xlfSetName** are used in combination to unregister DLL and XLL functions and commands.</span></span> 
  
<span data-ttu-id="a464b-109">更多的函数通过 C API Excel公开，这些函数在开发 XLL 时很有用。</span><span class="sxs-lookup"><span data-stu-id="a464b-109">Many more functions are exposed by Excel via the C API that are useful when you are developing XLLs.</span></span> <span data-ttu-id="a464b-110">它们对应于 XLM Excel中可用的工作表函数和命令。</span><span class="sxs-lookup"><span data-stu-id="a464b-110">They correspond to the Excel worksheet functions and functions and commands that are available from XLM macro sheets.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a464b-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="a464b-111">In this section</span></span>

[<span data-ttu-id="a464b-112">xlfCaller</span><span class="sxs-lookup"><span data-stu-id="a464b-112">xlfCaller</span></span>](xlfcaller.md)
  
[<span data-ttu-id="a464b-113">xlfEvaluate</span><span class="sxs-lookup"><span data-stu-id="a464b-113">xlfEvaluate</span></span>](xlfevaluate.md)
  
[<span data-ttu-id="a464b-114">xlfGetDef</span><span class="sxs-lookup"><span data-stu-id="a464b-114">xlfGetDef</span></span>](xlfgetdef.md)
  
[<span data-ttu-id="a464b-115">xlfGetName</span><span class="sxs-lookup"><span data-stu-id="a464b-115">xlfGetName</span></span>](xlfgetname.md)
  
[<span data-ttu-id="a464b-116">xlfRegister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="a464b-116">xlfRegister (Form 1)</span></span>](xlfregister-form-1.md)
  
[<span data-ttu-id="a464b-117">xlfRegister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="a464b-117">xlfRegister (Form 2)</span></span>](xlfregister-form-2.md)
  
[<span data-ttu-id="a464b-118">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="a464b-118">xlfRegisterId</span></span>](xlfregisterid.md)
  
[<span data-ttu-id="a464b-119">xlfUnregister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="a464b-119">xlfUnregister (Form 1)</span></span>](xlfunregister-form-1.md)
  
[<span data-ttu-id="a464b-120">xlfUnregister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="a464b-120">xlfUnregister (Form 2)</span></span>](xlfunregister-form-2.md)
  
[<span data-ttu-id="a464b-121">xlfSetName</span><span class="sxs-lookup"><span data-stu-id="a464b-121">xlfSetName</span></span>](xlfsetname.md)
  

