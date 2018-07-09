---
title: Excel XLL SDK API 函数参考
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- api 函数参考 [excel 2007，] 函数 [Excel 2007]、 引用 [Excel 2007]，Excel 2007 XLL 软件开发工具包，参考
localization_priority: Normal
api_type:
- COM
ms.assetid: 2f6df879-7546-4ac0-a4e3-6b009aee9463
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 2bb0a57ebcae618c8e921135b2bd4c50e8adf751
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773743"
---
# <a name="excel-xll-sdk-api-function-reference"></a><span data-ttu-id="42abd-104">Excel XLL SDK API 函数参考</span><span class="sxs-lookup"><span data-stu-id="42abd-104">Excel XLL SDK API Function Reference</span></span>

<span data-ttu-id="42abd-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="42abd-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="42abd-106">Microsoft Excel 2013 XLL SDK 包含用于加快 xll，以及两个示例项目，示例和泛型编写 Framework 库的源文件。</span><span class="sxs-lookup"><span data-stu-id="42abd-106">The Microsoft Excel 2013 XLL SDK contains source files for a Framework library that is designed to speed up the writing of XLLs, and two sample projects, Example and Generic.</span></span> 
  
<span data-ttu-id="42abd-107">本节提供有关以下函数引用：</span><span class="sxs-lookup"><span data-stu-id="42abd-107">This section provides a function reference for the following:</span></span>
  
- <span data-ttu-id="42abd-108">Excel XLL 可以调用的回调。</span><span class="sxs-lookup"><span data-stu-id="42abd-108">Excel callbacks that the XLL can call.</span></span>
    
- <span data-ttu-id="42abd-109">查找 Microsoft Excel 的 XLL 回调。</span><span class="sxs-lookup"><span data-stu-id="42abd-109">XLL callbacks that Microsoft Excel looks for.</span></span>
    
- <span data-ttu-id="42abd-110">示例和框架项目中的主要功能。</span><span class="sxs-lookup"><span data-stu-id="42abd-110">Key functions in the sample and framework projects.</span></span>
    
## <a name="sample-projects"></a><span data-ttu-id="42abd-111">示例项目</span><span class="sxs-lookup"><span data-stu-id="42abd-111">Sample projects</span></span>

<span data-ttu-id="42abd-112">Excel 2013 XLL SDK 提供源文件和 Microsoft Visual Studio 项目文件的以下示例项目：</span><span class="sxs-lookup"><span data-stu-id="42abd-112">The Excel 2013 XLL SDK provides source files and Microsoft Visual Studio project files for the following sample projects:</span></span>
  
- <span data-ttu-id="42abd-113">**框架**项目 (`SAMPLES\FRAMEWRK\`) 包含可生成到库，FRAMEWRK.lib，然后可链接到其他 XLL 项目的项目。</span><span class="sxs-lookup"><span data-stu-id="42abd-113">The **Framework** project (`SAMPLES\FRAMEWRK\`) contains a project that can be built to a library, FRAMEWRK.lib, which can then be linked into other XLL projects.</span></span> <span data-ttu-id="42abd-114">库包含许多函数和进行编写 Xll 更轻松的工具。</span><span class="sxs-lookup"><span data-stu-id="42abd-114">The library contains many functions and tools that make writing XLLs easier.</span></span> <span data-ttu-id="42abd-115">此库用于在这两个一起使用的其他项目的头文件 FRAMEWRK.h。</span><span class="sxs-lookup"><span data-stu-id="42abd-115">This library is used in both of the other projects in conjunction with the header file FRAMEWRK.h.</span></span>
    
- <span data-ttu-id="42abd-116">**示例**项目 (`SAMPLES\EXAMPLE\`) 包含可以对 XLL，EXAMPLE.xll 生成的项目。</span><span class="sxs-lookup"><span data-stu-id="42abd-116">The **Example** project (`SAMPLES\EXAMPLE\`) contains a project that can be built to an XLL, EXAMPLE.xll.</span></span> <span data-ttu-id="42abd-117">XLL 包含 Framework 库中，使用和如**xlAutoOpen**的 XLL 加载项界面功能的示例实现的多个示例。</span><span class="sxs-lookup"><span data-stu-id="42abd-117">The XLL contains many examples of the use of the Framework library, and example implementations of the XLL add-in interface functions such as **xlAutoOpen**.</span></span>
    
- <span data-ttu-id="42abd-118">**通用**项目 (`SAMPLES\GENERIC\`) 包含可以对 XLL，GENERIC.xll 生成的项目。</span><span class="sxs-lookup"><span data-stu-id="42abd-118">The **Generic** project (`SAMPLES\GENERIC\`) contains a project that can be built to an XLL, GENERIC.xll.</span></span> <span data-ttu-id="42abd-119">XLL 演示几个示例函数和命令和是编写您自己的 Xll 的良好起始点。</span><span class="sxs-lookup"><span data-stu-id="42abd-119">The XLL demonstrates several example functions and commands and is a good starting point for writing your own XLLs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="42abd-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="42abd-120">In this section</span></span>

- [<span data-ttu-id="42abd-121">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="42abd-121">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)
  
- [<span data-ttu-id="42abd-122">C API Callback Functions Excel4, Excel12</span><span class="sxs-lookup"><span data-stu-id="42abd-122">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md)
  
- [<span data-ttu-id="42abd-123">关键及有用的 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="42abd-123">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)
  
- [<span data-ttu-id="42abd-124">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="42abd-124">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
- [<span data-ttu-id="42abd-125">Framework 库中的函数</span><span class="sxs-lookup"><span data-stu-id="42abd-125">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)
  
- [<span data-ttu-id="42abd-126">泛型 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="42abd-126">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)
  
- [<span data-ttu-id="42abd-127">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="42abd-127">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)
  
## <a name="see-also"></a><span data-ttu-id="42abd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42abd-128">See also</span></span>

- [<span data-ttu-id="42abd-129">�� Excel ��ʹ�� C API ���б��</span><span class="sxs-lookup"><span data-stu-id="42abd-129">Programming with the C API in Excel</span></span>](programming-with-the-c-api-in-excel.md)
  
- [<span data-ttu-id="42abd-130">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="42abd-130">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

