---
title: RUNADDONWARGS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251493
localization_priority: Normal
ms.assetid: c154413f-c366-a66b-94e3-ed71ad23f325
description: 运行字符串并将命令行参数作为字符串传递给程序。
ms.openlocfilehash: bc05a4480438875c348373059f57bf04f82c9eca
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408703"
---
# <a name="runaddonwargs-function"></a><span data-ttu-id="7cd28-103">RUNADDONWARGS 函数</span><span class="sxs-lookup"><span data-stu-id="7cd28-103">RUNADDONWARGS Function</span></span>

<span data-ttu-id="7cd28-104">运行_字符串_并将命令行_参数_作为字符串传递给程序。</span><span class="sxs-lookup"><span data-stu-id="7cd28-104">Runs  _string_ and passes the command line  _arguments_ to the program as a string.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="7cd28-105">语法</span><span class="sxs-lookup"><span data-stu-id="7cd28-105">Syntax</span></span>

<span data-ttu-id="7cd28-106">RUNADDONWARGS ("\* \* *string* \* *", "* \* *arguments* \* \*")</span><span class="sxs-lookup"><span data-stu-id="7cd28-106">RUNADDONWARGS(" \*\* *string* \*\* "," \*\* *arguments* \*\* ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7cd28-107">参数</span><span class="sxs-lookup"><span data-stu-id="7cd28-107">Parameters</span></span>

|<span data-ttu-id="7cd28-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="7cd28-108">**Name**</span></span>|<span data-ttu-id="7cd28-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7cd28-109">**Required/Optional**</span></span>|<span data-ttu-id="7cd28-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7cd28-110">**Data Type**</span></span>|<span data-ttu-id="7cd28-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="7cd28-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7cd28-112">_string_</span><span class="sxs-lookup"><span data-stu-id="7cd28-112">_string_</span></span> <br/> |<span data-ttu-id="7cd28-113">必需</span><span class="sxs-lookup"><span data-stu-id="7cd28-113">Required</span></span>  <br/> |<span data-ttu-id="7cd28-114">**String**</span><span class="sxs-lookup"><span data-stu-id="7cd28-114">**String**</span></span> <br/> | <span data-ttu-id="7cd28-115">加载项的名称。</span><span class="sxs-lookup"><span data-stu-id="7cd28-115">The name of an add-on.</span></span>  <br/> |
| <span data-ttu-id="7cd28-116">_自_</span><span class="sxs-lookup"><span data-stu-id="7cd28-116">_arguments_</span></span> <br/> |<span data-ttu-id="7cd28-117">必需</span><span class="sxs-lookup"><span data-stu-id="7cd28-117">Required</span></span>  <br/> |<span data-ttu-id="7cd28-118">**String**</span><span class="sxs-lookup"><span data-stu-id="7cd28-118">**String**</span></span> <br/> |<span data-ttu-id="7cd28-119">要传递给程序的参数。</span><span class="sxs-lookup"><span data-stu-id="7cd28-119">Arguments to pass to your program.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7cd28-120">说明</span><span class="sxs-lookup"><span data-stu-id="7cd28-120">Remarks</span></span>

<span data-ttu-id="7cd28-121">在实践中,_参数_应为50个字符或更少。</span><span class="sxs-lookup"><span data-stu-id="7cd28-121">In practice,  _arguments_ should be 50 or fewer characters.</span></span> <span data-ttu-id="7cd28-122">使用 RUNADDONWARGS 函数将一个程序（如加载项）绑定到一个单元格（例如，Action 单元格或 Events 单元格）上。</span><span class="sxs-lookup"><span data-stu-id="7cd28-122">Use the RUNADDONWARGS function to bind a program, such as an add-on, to a cell, for example, to an Action or Events cell.</span></span> 
  
<span data-ttu-id="7cd28-123">RUNADDONWARGS 函数只能运行属于应用程序的 **Addons** 集合的成员的加载项。</span><span class="sxs-lookup"><span data-stu-id="7cd28-123">The RUNADDONWARGS function can only run add-ons that are members of the application's **Addons** collection.</span></span> <span data-ttu-id="7cd28-124">要加入该集合的加载项必须是 EXE 文件或 VSL 文件，且：</span><span class="sxs-lookup"><span data-stu-id="7cd28-124">To be present in that collection, an add-on must be an EXE file or VSL file that is:</span></span> 
  
- <span data-ttu-id="7cd28-125">安装在应用程序的 **“Startup”** 或 **“Addons”** 路径中。</span><span class="sxs-lookup"><span data-stu-id="7cd28-125">Installed in the application's **Startup** or **Addons** path.</span></span> 
    
- <span data-ttu-id="7cd28-126">使用 **Addons** 集合的 **Add** 方法，以编程方式添加。</span><span class="sxs-lookup"><span data-stu-id="7cd28-126">Added programmatically by using the **Add** method of the **Addons** collection.</span></span> 
    
<span data-ttu-id="7cd28-127">有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。</span><span class="sxs-lookup"><span data-stu-id="7cd28-127">For more information about running code in Visio, see [About Security Settings and Running Code in Visio](about-security-settings-and-running-code-in-visio-shapesheet.md) in this ShapeSheet Reference.</span></span> 
  
<span data-ttu-id="7cd28-p103">在 Visio 的早期版本中，此函数以 _RUNADDONWARGS 的形式出现。Visio 应用程序 4.0 版和更高版本接受这两种样式中的任意一种。</span><span class="sxs-lookup"><span data-stu-id="7cd28-p103">In earlier versions of Visio, this function appears as _RUNADDONWARGS. Visio application versions 4.0 and later accept either style.</span></span>
  
## <a name="example"></a><span data-ttu-id="7cd28-130">示例</span><span class="sxs-lookup"><span data-stu-id="7cd28-130">Example</span></span>

<span data-ttu-id="7cd28-131">RUNADDONWARGS ("GRAPHMKR"。EXE ","/GraphMaker = Stack ")</span><span class="sxs-lookup"><span data-stu-id="7cd28-131">RUNADDONWARGS("GRAPHMKR.EXE","/GraphMaker=Stack")</span></span> 
  
<span data-ttu-id="7cd28-132">启动加载项 Graphmkr.exe 并向它传递参数 /GraphMaker=Stack。</span><span class="sxs-lookup"><span data-stu-id="7cd28-132">Launches the add-on Graphmkr.exe and passes it the argument /GraphMaker=Stack.</span></span> 
  

