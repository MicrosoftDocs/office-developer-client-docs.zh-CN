---
title: 欢迎使用 Excel 软件开发工具包
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- excel 2007 xll software development kit,add-ins [Excel 2007]
localization_priority: Normal
ms.assetid: abfc9d76-6f22-49b9-ba45-eb7a54b082e0
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4de88a12b5fb945c6243e52b77babe88b2d02417
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773823"
---
# <a name="welcome-to-the-excel-software-development-kit"></a><span data-ttu-id="dd98b-104">欢迎使用 Excel 软件开发工具包</span><span class="sxs-lookup"><span data-stu-id="dd98b-104">Welcome to the Excel Software Development Kit</span></span>

 <span data-ttu-id="dd98b-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dd98b-105">Applies to: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="dd98b-p101">欢迎使用 Excel 2013 XLL 软件开发工具包 (SDK) 文档。此参考包含帮助你开发 Microsoft Excel 2013 XLL 的概念概述、编程任务和示例。</span><span class="sxs-lookup"><span data-stu-id="dd98b-p101">Welcome to the Excel 2013 XLL Software Development Kit (SDK) documentation. This reference contains conceptual overviews, programming tasks, and samples to help you develop Microsoft Excel 2013 XLLs.</span></span>
  
<span data-ttu-id="dd98b-108">修订日期：2012 年 11 月</span><span class="sxs-lookup"><span data-stu-id="dd98b-108">Revised: November 2012</span></span>
  
<span data-ttu-id="dd98b-109">下载 [Excel 2013 XLL SDK](http://go.microsoft.com/fwlink/?LinkID=251082&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="dd98b-109">Download the [Excel 2013 XLL SDK](http://go.microsoft.com/fwlink/?LinkID=251082&amp;clcid=0x409).</span></span>
  
<span data-ttu-id="dd98b-110">Excel 2013 XLL SDK 包括以下方面：</span><span class="sxs-lookup"><span data-stu-id="dd98b-110">The Excel 2013 XLL SDK includes the following:</span></span>
  
- <span data-ttu-id="dd98b-111">**C 应用程序编程接口 (API)**—包括使 DLL 能够访问 Excel 2013 功能的标头和源文件，以及接口说明，DLL 应将其公开以使用 Excel 加载项管理器。</span><span class="sxs-lookup"><span data-stu-id="dd98b-111">**C application programming interface (API)**—Includes header and source files that enable DLLs to access Excel 2013 functionality, and a description of the interface that a DLL should expose to work with the Excel Add-in Manager.</span></span>
    
- <span data-ttu-id="dd98b-p102">**Microsoft Visual Studio 项目**—包括 C/C++ 源代码并介绍了如何使用 C API。这些示例项目提供了示例，它们是你开发自己的加载项的起点。</span><span class="sxs-lookup"><span data-stu-id="dd98b-p102">**Microsoft Visual Studio projects**—Includes C/C++ source code and shows how to use the C API. These sample projects provide examples and they serve as a starting point for your own add-in development.</span></span>
    
<span data-ttu-id="dd98b-114">SDK 文档包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="dd98b-114">The SDK documentation contains the following sections:</span></span>
  
- [<span data-ttu-id="dd98b-115">Getting Started with the Excel XLL SDK</span><span class="sxs-lookup"><span data-stu-id="dd98b-115">Getting Started with the Excel XLL SDK</span></span>](getting-started-with-the-excel-xll-sdk.md)
    
- [<span data-ttu-id="dd98b-116">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="dd98b-116">Developing Excel XLLs</span></span>](developing-excel-xlls.md)
    
- [<span data-ttu-id="dd98b-117">Developing Excel Cluster Connectors</span><span class="sxs-lookup"><span data-stu-id="dd98b-117">Developing Excel Cluster Connectors</span></span>](developing-excel-cluster-connectors.md)
    
- [<span data-ttu-id="dd98b-118">Excel XLL SDK API Function Reference</span><span class="sxs-lookup"><span data-stu-id="dd98b-118">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)
    
## <a name="functionality-not-covered"></a><span data-ttu-id="dd98b-119">未涵盖的功能</span><span class="sxs-lookup"><span data-stu-id="dd98b-119">Functionality Not Covered</span></span>

<span data-ttu-id="dd98b-120">不涵盖以下主题：</span><span class="sxs-lookup"><span data-stu-id="dd98b-120">The following subjects are not covered:</span></span>
  
- <span data-ttu-id="dd98b-121">在 Excel 宏 (XLM) 工作表中开发用户定义的函数和命令。</span><span class="sxs-lookup"><span data-stu-id="dd98b-121">Developing user-defined functions and commands in Excel macro (XLM) sheets.</span></span>
    
- <span data-ttu-id="dd98b-122">在 DLL 中创建用户定义的函数以控制 XLM 宏的执行流。</span><span class="sxs-lookup"><span data-stu-id="dd98b-122">Creating user-defined functions in DLLs that control the flow of execution of an XLM macro.</span></span>
    
    <span data-ttu-id="dd98b-123">此类函数通过返回一种特殊的流控制数据类型工作，本文档中不作介绍。</span><span class="sxs-lookup"><span data-stu-id="dd98b-123">Such functions work by returning a special flow control data type, which is also not described in this documentation.</span></span>
    
## <a name="related-links"></a><span data-ttu-id="dd98b-124">相关链接</span><span class="sxs-lookup"><span data-stu-id="dd98b-124">Related Links</span></span>

[<span data-ttu-id="dd98b-125">Excel 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="dd98b-125">Excel Developer Center</span></span>](http://msdn.microsoft.com/zh-CN/office/aa905411.aspx)
  
[<span data-ttu-id="dd98b-126">Microsoft Office 开发中心</span><span class="sxs-lookup"><span data-stu-id="dd98b-126">Microsoft Office Developer Center</span></span>](http://msdn.microsoft.com/zh-CN/office/default.aspx)
  
[<span data-ttu-id="dd98b-127">Excel 2010 SDK：Excel 2010 XLL 软件开发工具包</span><span class="sxs-lookup"><span data-stu-id="dd98b-127">Excel 2010 SDK: Excel 2010 XLL Software Development Kit</span></span>](http://go.microsoft.com/fwlink/?LinkID=186435&amp;clcid=0x409)
  

