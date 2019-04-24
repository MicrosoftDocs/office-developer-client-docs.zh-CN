---
title: Excel XLL SDK API 函数引用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- api 函数引用 [excel 2007], 函数 [Excel 2007], 引用 [Excel 2007], Excel 2007 XLL 软件开发工具包, 引用
api_type:
- COM
ms.assetid: 2f6df879-7546-4ac0-a4e3-6b009aee9463
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: e116021a3dc24de7decbe0dad76cc762cd66d032
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304121"
---
# <a name="excel-xll-sdk-api-function-reference"></a><span data-ttu-id="b09e5-104">Excel XLL SDK API 函数引用</span><span class="sxs-lookup"><span data-stu-id="b09e5-104">Excel XLL SDK API Function Reference</span></span>

<span data-ttu-id="b09e5-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b09e5-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="b09e5-106">Microsoft Excel 2013 XLL SDK 包含适用于专为加速 XLL 编写而设计的框架库的源文件和两个示例项目：示例项目和常规项目。</span><span class="sxs-lookup"><span data-stu-id="b09e5-106">The Microsoft Excel 2013 XLL SDK contains source files for a Framework library that is designed to speed up the writing of XLLs, and two sample projects, Example and Generic.</span></span> 
  
<span data-ttu-id="b09e5-107">本节提供了以下函数引用：</span><span class="sxs-lookup"><span data-stu-id="b09e5-107">This section provides a function reference for the following:</span></span>
  
- <span data-ttu-id="b09e5-108">XLL 可调用的 Excel 回调。</span><span class="sxs-lookup"><span data-stu-id="b09e5-108">Excel callbacks that the XLL can call.</span></span>
    
- <span data-ttu-id="b09e5-109">Microsoft Excel 可查找的 XLL 回调。</span><span class="sxs-lookup"><span data-stu-id="b09e5-109">XLL callbacks that Microsoft Excel looks for.</span></span>
    
- <span data-ttu-id="b09e5-110">示例和框架项目中的关键函数。</span><span class="sxs-lookup"><span data-stu-id="b09e5-110">Key functions in the sample and framework projects.</span></span>
    
## <a name="sample-projects"></a><span data-ttu-id="b09e5-111">示例项目</span><span class="sxs-lookup"><span data-stu-id="b09e5-111">Sample projects</span></span>

<span data-ttu-id="b09e5-112">Excel 2013 XLL SDK 提供适用于以下示例项目的源文件和 Microsoft Visual Studio 项目文件：</span><span class="sxs-lookup"><span data-stu-id="b09e5-112">The Excel 2013 XLL SDK provides source files and Microsoft Visual Studio project files for the following sample projects:</span></span>
  
- <span data-ttu-id="b09e5-113">**框架**项目 (`SAMPLES\FRAMEWRK\`) 包含可生成到库的项目 FRAMEWRK.lib，该项目随后可链接至其他 XLL 项目。</span><span class="sxs-lookup"><span data-stu-id="b09e5-113">The **Framework** project (`SAMPLES\FRAMEWRK\`) contains a project that can be built to a library, FRAMEWRK.lib, which can then be linked into other XLL projects.</span></span> <span data-ttu-id="b09e5-114">库中包含多个可以简化 XLL 编写的函数和工具。</span><span class="sxs-lookup"><span data-stu-id="b09e5-114">The library contains many functions and tools that make writing XLLs easier.</span></span> <span data-ttu-id="b09e5-115">此库可以在两个其他项目中与头文件 FRAMEWRK.h 结合使用。</span><span class="sxs-lookup"><span data-stu-id="b09e5-115">This library is used in both of the other projects in conjunction with the header file FRAMEWRK.h.</span></span>
    
- <span data-ttu-id="b09e5-116">**示例**项目 (`SAMPLES\EXAMPLE\`) 包含可生成到 XLL 的项目 EXAMPLE.xll。</span><span class="sxs-lookup"><span data-stu-id="b09e5-116">The **Example** project (`SAMPLES\EXAMPLE\`) contains a project that can be built to an XLL, EXAMPLE.xll.</span></span> <span data-ttu-id="b09e5-117">XLL 包含多个使用框架库的示例以及 XLL 加载项接口函数（如 **xlAutoOpen**）的示例实施。</span><span class="sxs-lookup"><span data-stu-id="b09e5-117">The XLL contains many examples of the use of the Framework library, and example implementations of the XLL add-in interface functions such as **xlAutoOpen**.</span></span>
    
- <span data-ttu-id="b09e5-118">**常规**项目 (`SAMPLES\GENERIC\`) 包含可生成到 XLL 的项目 GENERIC.xll。</span><span class="sxs-lookup"><span data-stu-id="b09e5-118">The **Generic** project (`SAMPLES\GENERIC\`) contains a project that can be built to an XLL, GENERIC.xll.</span></span> <span data-ttu-id="b09e5-119">XLL 演示了多个实例函数和命令，是编写你自己的 XLL 的一个很好起点。</span><span class="sxs-lookup"><span data-stu-id="b09e5-119">The XLL demonstrates several example functions and commands and is a good starting point for writing your own XLLs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="b09e5-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="b09e5-120">In this section</span></span>

- [<span data-ttu-id="b09e5-121">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="b09e5-121">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)
  
- [<span data-ttu-id="b09e5-122">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="b09e5-122">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md)
  
- [<span data-ttu-id="b09e5-123">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="b09e5-123">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)
  
- [<span data-ttu-id="b09e5-124">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="b09e5-124">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
- [<span data-ttu-id="b09e5-125">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="b09e5-125">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)
  
- [<span data-ttu-id="b09e5-126">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="b09e5-126">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)
  
- [<span data-ttu-id="b09e5-127">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="b09e5-127">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)
  
## <a name="see-also"></a><span data-ttu-id="b09e5-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b09e5-128">See also</span></span>

- [<span data-ttu-id="b09e5-129">在 Excel 中使用 C API 进行编程</span><span class="sxs-lookup"><span data-stu-id="b09e5-129">Programming with the C API in Excel</span></span>](programming-with-the-c-api-in-excel.md)
  
- [<span data-ttu-id="b09e5-130">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="b09e5-130">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

