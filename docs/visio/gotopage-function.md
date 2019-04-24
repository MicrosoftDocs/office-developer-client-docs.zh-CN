---
title: GOTOPAGE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251432
localization_priority: Normal
ms.assetid: b131badf-1656-132e-0aae-eeedb917ba7a
description: 在当前活动窗口中显示名称为 "pagename" 的页面。
ms.openlocfilehash: c96585406b6104aeedbe46c35024a4f13bb0953e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302966"
---
# <a name="gotopage-function"></a><span data-ttu-id="50ea8-103">GOTOPAGE 函数</span><span class="sxs-lookup"><span data-stu-id="50ea8-103">GOTOPAGE Function</span></span>

<span data-ttu-id="50ea8-104">在当前活动窗口中显示名称为 " *pagename* " 的页面。</span><span class="sxs-lookup"><span data-stu-id="50ea8-104">Displays the page that has the name  *pagename*  in the currently active window.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="50ea8-105">语法</span><span class="sxs-lookup"><span data-stu-id="50ea8-105">Syntax</span></span>

<span data-ttu-id="50ea8-106">GOTOPAGE ("\* \* *pagename* \* \*")</span><span class="sxs-lookup"><span data-stu-id="50ea8-106">GOTOPAGE(" \*\* *pagename* \*\* ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="50ea8-107">参数</span><span class="sxs-lookup"><span data-stu-id="50ea8-107">Parameters</span></span>

|<span data-ttu-id="50ea8-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="50ea8-108">**Name**</span></span>|<span data-ttu-id="50ea8-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="50ea8-109">**Required/Optional**</span></span>|<span data-ttu-id="50ea8-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="50ea8-110">**Data Type**</span></span>|<span data-ttu-id="50ea8-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="50ea8-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="50ea8-112">_pagename_</span><span class="sxs-lookup"><span data-stu-id="50ea8-112">_pagename_</span></span> <br/> |<span data-ttu-id="50ea8-113">必需</span><span class="sxs-lookup"><span data-stu-id="50ea8-113">Required</span></span>  <br/> |<span data-ttu-id="50ea8-114">**String**</span><span class="sxs-lookup"><span data-stu-id="50ea8-114">**String**</span></span> <br/> |<span data-ttu-id="50ea8-115">要进入的页面的名称。</span><span class="sxs-lookup"><span data-stu-id="50ea8-115">The name of the page to go to.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="50ea8-116">注解</span><span class="sxs-lookup"><span data-stu-id="50ea8-116">Remarks</span></span>

<span data-ttu-id="50ea8-117">如果一个窗口已经显示了该页，则该窗口就成为活动窗口。</span><span class="sxs-lookup"><span data-stu-id="50ea8-117">If a window is already displaying the page, that window becomes active.</span></span> <span data-ttu-id="50ea8-118">如果*pagename*不存在, 则应用程序将尝试导航到 https:// *pagename* /。</span><span class="sxs-lookup"><span data-stu-id="50ea8-118">If  *pagename*  does not exist, the application attempts to navigate to https://  *pagename*  /.</span></span> <span data-ttu-id="50ea8-119">如果 Visio 正用作本地服务器，则 GOTOPAGE 函数将不起作用。</span><span class="sxs-lookup"><span data-stu-id="50ea8-119">If Visio is acting as an in-place server, the GOTOPAGE function has no effect.</span></span> 
  
<span data-ttu-id="50ea8-120">可以使用 HYPERLINK 函数浏览到任何 DOS、UNC 或 URL 路径。</span><span class="sxs-lookup"><span data-stu-id="50ea8-120">You can use the HYPERLINK function to navigate to any DOS, UNC, or URL path.</span></span> 
  
<span data-ttu-id="50ea8-p102">在 Visio 产品的早期版本中，此函数以 _GOTOPAGE 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。</span><span class="sxs-lookup"><span data-stu-id="50ea8-p102">In earlier versions of Visio products, this function appears as _GOTOPAGE. Visio versions 4.0 and later accept either style.</span></span> 
  

