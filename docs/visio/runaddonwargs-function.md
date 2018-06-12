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
description: 运行字符串，并将命令行参数传递给字符串形式的程序。
ms.openlocfilehash: 7bc05a0cbf32550d1e39bee39bec83101882cf19
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781208"
---
# <a name="runaddonwargs-function"></a><span data-ttu-id="70fbb-103">RUNADDONWARGS 函数</span><span class="sxs-lookup"><span data-stu-id="70fbb-103">RUNADDONWARGS Function</span></span>

<span data-ttu-id="70fbb-104">运行_字符串_，并将命令行_参数_传递给字符串形式的程序。</span><span class="sxs-lookup"><span data-stu-id="70fbb-104">Runs  _string_ and passes the command line  _arguments_ to the program as a string.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="70fbb-105">语法</span><span class="sxs-lookup"><span data-stu-id="70fbb-105">Syntax</span></span>

<span data-ttu-id="70fbb-106">RUNADDONWARGS ("* **字符串** *"、"* **参数** *")</span><span class="sxs-lookup"><span data-stu-id="70fbb-106">RUNADDONWARGS(" ** *string* ** "," ** *arguments* ** ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="70fbb-107">参数</span><span class="sxs-lookup"><span data-stu-id="70fbb-107">Parameters</span></span>

|<span data-ttu-id="70fbb-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="70fbb-108">**Name**</span></span>|<span data-ttu-id="70fbb-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="70fbb-109">**Required/Optional**</span></span>|<span data-ttu-id="70fbb-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="70fbb-110">**Data Type**</span></span>|<span data-ttu-id="70fbb-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="70fbb-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="70fbb-112">_string_</span><span class="sxs-lookup"><span data-stu-id="70fbb-112">_string_</span></span> <br/> |<span data-ttu-id="70fbb-113">必需</span><span class="sxs-lookup"><span data-stu-id="70fbb-113">Required</span></span>  <br/> |<span data-ttu-id="70fbb-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="70fbb-114">**String**</span></span> <br/> | <span data-ttu-id="70fbb-115">加载项的名称。</span><span class="sxs-lookup"><span data-stu-id="70fbb-115">The name of an add-on.</span></span>  <br/> |
| <span data-ttu-id="70fbb-116">_参数_</span><span class="sxs-lookup"><span data-stu-id="70fbb-116">_arguments_</span></span> <br/> |<span data-ttu-id="70fbb-117">必需</span><span class="sxs-lookup"><span data-stu-id="70fbb-117">Required</span></span>  <br/> |<span data-ttu-id="70fbb-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="70fbb-118">**String**</span></span> <br/> |<span data-ttu-id="70fbb-119">要传递给程序的参数。</span><span class="sxs-lookup"><span data-stu-id="70fbb-119">Arguments to pass to your program.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="70fbb-120">注解</span><span class="sxs-lookup"><span data-stu-id="70fbb-120">Remarks</span></span>

<span data-ttu-id="70fbb-121">实际上，_参数_应为 50 个或更少字符。</span><span class="sxs-lookup"><span data-stu-id="70fbb-121">In practice,  _arguments_ should be 50 or fewer characters.</span></span> <span data-ttu-id="70fbb-122">使用 RUNADDONWARGS 函数将程序，如加载项，对单元格，例如，绑定到操作或事件单元格。</span><span class="sxs-lookup"><span data-stu-id="70fbb-122">Use the RUNADDONWARGS function to bind a program, such as an add-on, to a cell, for example, to an Action or Events cell.</span></span> 
  
<span data-ttu-id="70fbb-123">RUNADDONWARGS 函数只能运行加载项的应用程序的**Addons**集合的成员。</span><span class="sxs-lookup"><span data-stu-id="70fbb-123">The RUNADDONWARGS function can only run add-ons that are members of the application's **Addons** collection.</span></span> <span data-ttu-id="70fbb-124">必须包含在集合中，加载项必须是 EXE 文件或 VSL 文件：</span><span class="sxs-lookup"><span data-stu-id="70fbb-124">To be present in that collection, an add-on must be an EXE file or VSL file that is:</span></span> 
  
- <span data-ttu-id="70fbb-125">安装应用程序的**启动**或**Addons**路径中。</span><span class="sxs-lookup"><span data-stu-id="70fbb-125">Installed in the application's **Startup** or **Addons** path.</span></span> 
    
- <span data-ttu-id="70fbb-126">使用**Addons**集合的**Add**方法以编程方式添加。</span><span class="sxs-lookup"><span data-stu-id="70fbb-126">Added programmatically by using the **Add** method of the **Addons** collection.</span></span> 
    
<span data-ttu-id="70fbb-127">有关在 Visio 中运行代码的详细信息，请参阅[关于安全设置和运行 Visio 中的代码](about-security-settings-and-running-code-in-visio-shapesheet.md)在 ShapeSheet 参考。</span><span class="sxs-lookup"><span data-stu-id="70fbb-127">For more information about running code in Visio, see [About Security Settings and Running Code in Visio](about-security-settings-and-running-code-in-visio-shapesheet.md) in this ShapeSheet Reference.</span></span> 
  
<span data-ttu-id="70fbb-p103">在 Visio 的早期版本中，此函数以 _RUNADDONWARGS 的形式出现。Visio 应用程序 4.0 版和更高版本接受这两种样式中的任意一种。</span><span class="sxs-lookup"><span data-stu-id="70fbb-p103">In earlier versions of Visio, this function appears as _RUNADDONWARGS. Visio application versions 4.0 and later accept either style.</span></span>
  
## <a name="example"></a><span data-ttu-id="70fbb-130">示例</span><span class="sxs-lookup"><span data-stu-id="70fbb-130">Example</span></span>

<span data-ttu-id="70fbb-131">RUNADDONWARGS ("GRAPHMKR。Exe 文件"，"/ GraphMaker = 堆栈")</span><span class="sxs-lookup"><span data-stu-id="70fbb-131">RUNADDONWARGS("GRAPHMKR.EXE","/GraphMaker=Stack")</span></span> 
  
<span data-ttu-id="70fbb-132">启动加载项 Graphmkr.exe 并向它传递参数 /GraphMaker=Stack。</span><span class="sxs-lookup"><span data-stu-id="70fbb-132">Launches the add-on Graphmkr.exe and passes it the argument /GraphMaker=Stack.</span></span> 
  

