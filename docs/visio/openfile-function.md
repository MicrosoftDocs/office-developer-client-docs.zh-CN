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
description: 打开一Visio打开一个 Microsoft 文档（如果该文档尚未打开）并激活文档窗口。
ms.openlocfilehash: 5a89a658e560d144007ec19796de82b9949bea82
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419574"
---
# <a name="openfile-function"></a><span data-ttu-id="ad1cd-103">OPENFILE 函数</span><span class="sxs-lookup"><span data-stu-id="ad1cd-103">OPENFILE Function</span></span>

<span data-ttu-id="ad1cd-104">打开一Visio打开一个 Microsoft 文档（如果该文档尚未打开）并激活文档窗口。</span><span class="sxs-lookup"><span data-stu-id="ad1cd-104">Opens a Microsoft Visio document, if it's not already open, and activates the document window.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="ad1cd-105">语法</span><span class="sxs-lookup"><span data-stu-id="ad1cd-105">Syntax</span></span>

 <span data-ttu-id="ad1cd-106">**OPENFILE** _("filename")_</span><span class="sxs-lookup"><span data-stu-id="ad1cd-106">**OPENFILE**( _"filename"_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="ad1cd-107">参数</span><span class="sxs-lookup"><span data-stu-id="ad1cd-107">Parameters</span></span>

|<span data-ttu-id="ad1cd-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="ad1cd-108">**Name**</span></span>|<span data-ttu-id="ad1cd-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ad1cd-109">**Required/Optional**</span></span>|<span data-ttu-id="ad1cd-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ad1cd-110">**Data Type**</span></span>|<span data-ttu-id="ad1cd-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="ad1cd-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ad1cd-112">_filename_</span><span class="sxs-lookup"><span data-stu-id="ad1cd-112">_filename_</span></span> <br/> |<span data-ttu-id="ad1cd-113">必需</span><span class="sxs-lookup"><span data-stu-id="ad1cd-113">Required</span></span>  <br/> |<span data-ttu-id="ad1cd-114">**String**</span><span class="sxs-lookup"><span data-stu-id="ad1cd-114">**String**</span></span> <br/> |<span data-ttu-id="ad1cd-115">要打开的文件的名称，包括文件路径。</span><span class="sxs-lookup"><span data-stu-id="ad1cd-115">The name of the file, including file path, you want to open.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ad1cd-116">备注</span><span class="sxs-lookup"><span data-stu-id="ad1cd-116">Remarks</span></span>

<span data-ttu-id="ad1cd-p101">多个 OPENFILE 函数调用将按照计算次序排队执行。如果当前的 Visio 文档正处于可视（就地）编辑状态，则用请求的文件名启动新的 Visio 实例。</span><span class="sxs-lookup"><span data-stu-id="ad1cd-p101">Multiple OPENFILE function calls are queued and executed in order of evaluation. If the current Visio document is activated for visual (in-place) editing, a new Visio instance is launched with the requested file name.</span></span> 
  
<span data-ttu-id="ad1cd-119">此函数总是返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="ad1cd-119">This function always returns FALSE.</span></span> 
  
<span data-ttu-id="ad1cd-p102">在 Visio 应用程序的早期版本中，此函数以 _OPENFILE 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。</span><span class="sxs-lookup"><span data-stu-id="ad1cd-p102">In earlier versions of the Visio application, this function appears as _OPENFILE. Visio versions 4.0 and later accept either style.</span></span> 
  
## <a name="example"></a><span data-ttu-id="ad1cd-122">示例</span><span class="sxs-lookup"><span data-stu-id="ad1cd-122">Example</span></span>

 `OPENFILE("C:/MyFile.vsdx")`
  
<span data-ttu-id="ad1cd-123">在新窗口中打开指定的文件"MyFile.vsdx"，如果该文件已经打开，则激活该窗口。</span><span class="sxs-lookup"><span data-stu-id="ad1cd-123">Opens the specified file "MyFile.vsdx" in a new window, or activates the window if the file is already open.</span></span> 
  

