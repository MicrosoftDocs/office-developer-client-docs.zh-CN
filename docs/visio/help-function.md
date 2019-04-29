---
title: HELP 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251436
localization_priority: Normal
ms.assetid: 5b358c38-6ed1-3fbe-c1d1-1a56ebbaa870
description: 打开 HTML 帮助文件, 其中包含指定的关键字在搜索框中。
ms.openlocfilehash: 639d10bf489d1ad09aef1522d3cbc743bbe66f6f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431335"
---
# <a name="help-function"></a><span data-ttu-id="e5f40-103">HELP 函数</span><span class="sxs-lookup"><span data-stu-id="e5f40-103">HELP Function</span></span>

<span data-ttu-id="e5f40-104">打开 HTML 帮助文件, 其中包含指定的*关键字*在**搜索**框中。</span><span class="sxs-lookup"><span data-stu-id="e5f40-104">Opens an HTML Help file with the specifed  *keyword*  in the **Search** box.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e5f40-105">语法</span><span class="sxs-lookup"><span data-stu-id="e5f40-105">Syntax</span></span>

<span data-ttu-id="e5f40-106">HELP ("\* \* *filename .chm! 关键字*\* \*")</span><span class="sxs-lookup"><span data-stu-id="e5f40-106">HELP(" \*\* *filename.chm!keyword* \*\* ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e5f40-107">参数</span><span class="sxs-lookup"><span data-stu-id="e5f40-107">Parameters</span></span>

|<span data-ttu-id="e5f40-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="e5f40-108">**Name**</span></span>|<span data-ttu-id="e5f40-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e5f40-109">**Required/Optional**</span></span>|<span data-ttu-id="e5f40-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e5f40-110">**Data Type**</span></span>|<span data-ttu-id="e5f40-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e5f40-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e5f40-112">_文件名 .chm! 关键字_</span><span class="sxs-lookup"><span data-stu-id="e5f40-112">_filename.chm!keyword_</span></span> <br/> |<span data-ttu-id="e5f40-113">必需</span><span class="sxs-lookup"><span data-stu-id="e5f40-113">Required</span></span>  <br/> |<span data-ttu-id="e5f40-114">**String**</span><span class="sxs-lookup"><span data-stu-id="e5f40-114">**String**</span></span> <br/> | <span data-ttu-id="e5f40-115">要搜索的帮助文件的文件名和关键字。</span><span class="sxs-lookup"><span data-stu-id="e5f40-115">The filename of the Help file and the keyword to search for.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e5f40-116">说明</span><span class="sxs-lookup"><span data-stu-id="e5f40-116">Remarks</span></span>

<span data-ttu-id="e5f40-117">如果未指定*关键字*, 则帮助函数将打开帮助文件的内容页。</span><span class="sxs-lookup"><span data-stu-id="e5f40-117">If no  *keyword*  is specified, the HELP function opens the contents page of the Help file.</span></span> 
  
## <a name="example"></a><span data-ttu-id="e5f40-118">示例</span><span class="sxs-lookup"><span data-stu-id="e5f40-118">Example</span></span>

<span data-ttu-id="e5f40-119">帮助 ("visio .chm! shapesheet")</span><span class="sxs-lookup"><span data-stu-id="e5f40-119">HELP("visio.chm!shapesheet")</span></span> 
  
<span data-ttu-id="e5f40-120">打开文件 Visio 帮助文件，并显示关键字为“shapesheet”的主题列表。</span><span class="sxs-lookup"><span data-stu-id="e5f40-120">Opens the Visio Help file and displays a list of the topic(s) whose keyword is "shapesheet."</span></span> 
  

