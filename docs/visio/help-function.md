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
description: 在"搜索"框中打开一个包含指定关键字的 HTML 帮助文件。
ms.openlocfilehash: 639d10bf489d1ad09aef1522d3cbc743bbe66f6f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431335"
---
# <a name="help-function"></a><span data-ttu-id="7e711-103">HELP 函数</span><span class="sxs-lookup"><span data-stu-id="7e711-103">HELP Function</span></span>

<span data-ttu-id="7e711-104">在"搜索"框中打开一个包含指定  *关键字*  的 HTML **帮助** 文件。</span><span class="sxs-lookup"><span data-stu-id="7e711-104">Opens an HTML Help file with the specifed  *keyword*  in the **Search** box.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="7e711-105">语法</span><span class="sxs-lookup"><span data-stu-id="7e711-105">Syntax</span></span>

<span data-ttu-id="7e711-106">HELP (" \*\* *filename.chm！keyword* \*\* ") </span><span class="sxs-lookup"><span data-stu-id="7e711-106">HELP(" \*\* *filename.chm!keyword* \*\* ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7e711-107">参数</span><span class="sxs-lookup"><span data-stu-id="7e711-107">Parameters</span></span>

|<span data-ttu-id="7e711-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="7e711-108">**Name**</span></span>|<span data-ttu-id="7e711-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7e711-109">**Required/Optional**</span></span>|<span data-ttu-id="7e711-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7e711-110">**Data Type**</span></span>|<span data-ttu-id="7e711-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="7e711-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7e711-112">_filename.chm！keyword_</span><span class="sxs-lookup"><span data-stu-id="7e711-112">_filename.chm!keyword_</span></span> <br/> |<span data-ttu-id="7e711-113">必需</span><span class="sxs-lookup"><span data-stu-id="7e711-113">Required</span></span>  <br/> |<span data-ttu-id="7e711-114">**String**</span><span class="sxs-lookup"><span data-stu-id="7e711-114">**String**</span></span> <br/> | <span data-ttu-id="7e711-115">要搜索的帮助文件的文件名和关键字。</span><span class="sxs-lookup"><span data-stu-id="7e711-115">The filename of the Help file and the keyword to search for.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7e711-116">备注</span><span class="sxs-lookup"><span data-stu-id="7e711-116">Remarks</span></span>

<span data-ttu-id="7e711-117">如果  *未指定*  关键字，HELP 函数将打开帮助文件的内容页。</span><span class="sxs-lookup"><span data-stu-id="7e711-117">If no  *keyword*  is specified, the HELP function opens the contents page of the Help file.</span></span> 
  
## <a name="example"></a><span data-ttu-id="7e711-118">示例</span><span class="sxs-lookup"><span data-stu-id="7e711-118">Example</span></span>

<span data-ttu-id="7e711-119">HELP ("visio.chm！shapesheet") </span><span class="sxs-lookup"><span data-stu-id="7e711-119">HELP("visio.chm!shapesheet")</span></span> 
  
<span data-ttu-id="7e711-120">打开文件 Visio 帮助文件，并显示关键字为“shapesheet”的主题列表。</span><span class="sxs-lookup"><span data-stu-id="7e711-120">Opens the Visio Help file and displays a list of the topic(s) whose keyword is "shapesheet."</span></span> 
  

