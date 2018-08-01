---
title: 基本的有用 C API XLM 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- '[excel 2007] 的函数、 c api xlm'
localization_priority: Normal
ms.assetid: dc80cb3d-0d7e-4cb9-9870-3acc84eeca82
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 410a6009bf6bbb8146dcc1354e7f5688c28d96c6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773662"
---
# <a name="essential-and-useful-c-api-xlm-functions"></a><span data-ttu-id="238a7-104">基本的有用 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="238a7-104">Essential and Useful C API XLM Functions</span></span>

 <span data-ttu-id="238a7-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="238a7-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="238a7-106">本节中所述的功能都是尤为有用 DLL 和 XLL 开发人员的 Microsoft Excel 回调函数。</span><span class="sxs-lookup"><span data-stu-id="238a7-106">The functions described in this section are Microsoft Excel callback functions that are particularly useful to DLL and XLL developers.</span></span> <span data-ttu-id="238a7-107">其中， **xlfRegister**函数对于 xll （英文） 和要向其函数和命令注册，以便他们可以直接从 Excel 呼叫的 Dll 至关重要。</span><span class="sxs-lookup"><span data-stu-id="238a7-107">Of these, the **xlfRegister** function is essential for XLLs and DLLs that want to register their functions and commands so that they can be called directly from Excel.</span></span> <span data-ttu-id="238a7-108">函数**xlfUnregister**和**xlfSetName**结合使用，取消注册 DLL 和 XLL 函数和命令。</span><span class="sxs-lookup"><span data-stu-id="238a7-108">The functions **xlfUnregister** and **xlfSetName** are used in combination to unregister DLL and XLL functions and commands.</span></span> 
  
<span data-ttu-id="238a7-109">Excel 开发 Xll 时很有用的 C API 通过公开更多功能。</span><span class="sxs-lookup"><span data-stu-id="238a7-109">Many more functions are exposed by Excel via the C API that are useful when you are developing XLLs.</span></span> <span data-ttu-id="238a7-110">它们对应的 Excel 工作表功能和功能以及提供 XLM 宏工作表的命令。</span><span class="sxs-lookup"><span data-stu-id="238a7-110">They correspond to the Excel worksheet functions and functions and commands that are available from XLM macro sheets.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="238a7-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="238a7-111">In this section</span></span>

[<span data-ttu-id="238a7-112">xlfCaller</span><span class="sxs-lookup"><span data-stu-id="238a7-112">xlfCaller</span></span>](xlfcaller.md)
  
[<span data-ttu-id="238a7-113">xlfEvaluate</span><span class="sxs-lookup"><span data-stu-id="238a7-113">xlfEvaluate</span></span>](xlfevaluate.md)
  
[<span data-ttu-id="238a7-114">xlfGetDef</span><span class="sxs-lookup"><span data-stu-id="238a7-114">xlfGetDef</span></span>](xlfgetdef.md)
  
[<span data-ttu-id="238a7-115">xlfGetName</span><span class="sxs-lookup"><span data-stu-id="238a7-115">xlfGetName</span></span>](xlfgetname.md)
  
[<span data-ttu-id="238a7-116">xlfRegister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="238a7-116">xlfRegister (Form 1)</span></span>](xlfregister-form-1.md)
  
[<span data-ttu-id="238a7-117">xlfRegister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="238a7-117">xlfRegister (Form 2)</span></span>](xlfregister-form-2.md)
  
[<span data-ttu-id="238a7-118">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="238a7-118">xlfRegisterId</span></span>](xlfregisterid.md)
  
[<span data-ttu-id="238a7-119">xlfUnregister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="238a7-119">xlfUnregister (Form 1)</span></span>](xlfunregister-form-1.md)
  
[<span data-ttu-id="238a7-120">xlfUnregister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="238a7-120">xlfUnregister (Form 2)</span></span>](xlfunregister-form-2.md)
  
[<span data-ttu-id="238a7-121">xlfSetName</span><span class="sxs-lookup"><span data-stu-id="238a7-121">xlfSetName</span></span>](xlfsetname.md)
  

