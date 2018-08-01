---
title: OPENFILE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251471
localization_priority: Normal
ms.assetid: ff59ab04-a589-cf9e-db3b-20658a7dffdc
description: 如果其尚未打开，并激活文档窗口，请打开 Microsoft Visio 文档。
ms.openlocfilehash: 7d4778fc4641465e88303b8515365172fd8be0ff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780811"
---
# <a name="openfile-function"></a><span data-ttu-id="4c7bc-103">OPENFILE 函数</span><span class="sxs-lookup"><span data-stu-id="4c7bc-103">OPENFILE Function</span></span>

<span data-ttu-id="4c7bc-104">如果其尚未打开，并激活文档窗口，请打开 Microsoft Visio 文档。</span><span class="sxs-lookup"><span data-stu-id="4c7bc-104">Opens a Microsoft Visio document, if it's not already open, and activates the document window.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4c7bc-105">语法</span><span class="sxs-lookup"><span data-stu-id="4c7bc-105">Syntax</span></span>

 <span data-ttu-id="4c7bc-106">**OPENFILE**( _"文件名"_)</span><span class="sxs-lookup"><span data-stu-id="4c7bc-106">**OPENFILE**( _"filename"_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="4c7bc-107">参数</span><span class="sxs-lookup"><span data-stu-id="4c7bc-107">Parameters</span></span>

|<span data-ttu-id="4c7bc-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="4c7bc-108">**Name**</span></span>|<span data-ttu-id="4c7bc-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="4c7bc-109">**Required/Optional**</span></span>|<span data-ttu-id="4c7bc-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4c7bc-110">**Data Type**</span></span>|<span data-ttu-id="4c7bc-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="4c7bc-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4c7bc-112">_文件名_</span><span class="sxs-lookup"><span data-stu-id="4c7bc-112">_filename_</span></span> <br/> |<span data-ttu-id="4c7bc-113">必需</span><span class="sxs-lookup"><span data-stu-id="4c7bc-113">Required</span></span>  <br/> |<span data-ttu-id="4c7bc-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="4c7bc-114">**String**</span></span> <br/> |<span data-ttu-id="4c7bc-115">要打开该文件，包括文件路径的名称。</span><span class="sxs-lookup"><span data-stu-id="4c7bc-115">The name of the file, including file path, you want to open.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4c7bc-116">注解</span><span class="sxs-lookup"><span data-stu-id="4c7bc-116">Remarks</span></span>

<span data-ttu-id="4c7bc-p101">多个 OPENFILE 函数调用将按照计算次序排队执行。如果当前的 Visio 文档正处于可视（就地）编辑状态，则用请求的文件名启动新的 Visio 实例。</span><span class="sxs-lookup"><span data-stu-id="4c7bc-p101">Multiple OPENFILE function calls are queued and executed in order of evaluation. If the current Visio document is activated for visual (in-place) editing, a new Visio instance is launched with the requested file name.</span></span> 
  
<span data-ttu-id="4c7bc-119">此函数总是返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="4c7bc-119">This function always returns FALSE.</span></span> 
  
<span data-ttu-id="4c7bc-p102">在 Visio 应用程序的早期版本中，此函数以 _OPENFILE 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。</span><span class="sxs-lookup"><span data-stu-id="4c7bc-p102">In earlier versions of the Visio application, this function appears as _OPENFILE. Visio versions 4.0 and later accept either style.</span></span> 
  
## <a name="example"></a><span data-ttu-id="4c7bc-122">示例</span><span class="sxs-lookup"><span data-stu-id="4c7bc-122">Example</span></span>

 `OPENFILE("C:/MyFile.vsdx")`
  
<span data-ttu-id="4c7bc-123">在新窗口中，打开指定的文件"MyFile.vsdx"，或如果文件已打开，则激活窗口。</span><span class="sxs-lookup"><span data-stu-id="4c7bc-123">Opens the specified file "MyFile.vsdx" in a new window, or activates the window if the file is already open.</span></span> 
  

