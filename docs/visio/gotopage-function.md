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
description: 将显示在当前的活动窗口中具有名称 pagename 页。
ms.openlocfilehash: c96585406b6104aeedbe46c35024a4f13bb0953e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397147"
---
# <a name="gotopage-function"></a><span data-ttu-id="fdf34-103">GOTOPAGE 函数</span><span class="sxs-lookup"><span data-stu-id="fdf34-103">GOTOPAGE Function</span></span>

<span data-ttu-id="fdf34-104">将显示在当前的活动窗口中具有名称*pagename*页。</span><span class="sxs-lookup"><span data-stu-id="fdf34-104">Displays the page that has the name  *pagename*  in the currently active window.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="fdf34-105">语法</span><span class="sxs-lookup"><span data-stu-id="fdf34-105">Syntax</span></span>

<span data-ttu-id="fdf34-106">GOTOPAGE ("\* \* *pagename* \* \*")</span><span class="sxs-lookup"><span data-stu-id="fdf34-106">GOTOPAGE(" \*\* *pagename* \*\* ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="fdf34-107">参数</span><span class="sxs-lookup"><span data-stu-id="fdf34-107">Parameters</span></span>

|<span data-ttu-id="fdf34-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="fdf34-108">**Name**</span></span>|<span data-ttu-id="fdf34-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="fdf34-109">**Required/Optional**</span></span>|<span data-ttu-id="fdf34-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fdf34-110">**Data Type**</span></span>|<span data-ttu-id="fdf34-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="fdf34-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="fdf34-112">_pagename_</span><span class="sxs-lookup"><span data-stu-id="fdf34-112">_pagename_</span></span> <br/> |<span data-ttu-id="fdf34-113">必需</span><span class="sxs-lookup"><span data-stu-id="fdf34-113">Required</span></span>  <br/> |<span data-ttu-id="fdf34-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="fdf34-114">**String**</span></span> <br/> |<span data-ttu-id="fdf34-115">要进入的页面的名称。</span><span class="sxs-lookup"><span data-stu-id="fdf34-115">The name of the page to go to.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fdf34-116">注解</span><span class="sxs-lookup"><span data-stu-id="fdf34-116">Remarks</span></span>

<span data-ttu-id="fdf34-117">窗口已显示页上，如果该窗口将变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="fdf34-117">If a window is already displaying the page, that window becomes active.</span></span> <span data-ttu-id="fdf34-118">如果不存在*pagename* ，应用程序尝试导航到 https:// *pagename* /。</span><span class="sxs-lookup"><span data-stu-id="fdf34-118">If  *pagename*  does not exist, the application attempts to navigate to https://  *pagename*  /.</span></span> <span data-ttu-id="fdf34-119">如果 Visio 正在就地服务器，GOTOPAGE 函数不起作用。</span><span class="sxs-lookup"><span data-stu-id="fdf34-119">If Visio is acting as an in-place server, the GOTOPAGE function has no effect.</span></span> 
  
<span data-ttu-id="fdf34-120">可以使用 HYPERLINK 函数浏览到任何 DOS、UNC 或 URL 路径。</span><span class="sxs-lookup"><span data-stu-id="fdf34-120">You can use the HYPERLINK function to navigate to any DOS, UNC, or URL path.</span></span> 
  
<span data-ttu-id="fdf34-p102">在 Visio 产品的早期版本中，此函数以 _GOTOPAGE 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。</span><span class="sxs-lookup"><span data-stu-id="fdf34-p102">In earlier versions of Visio products, this function appears as _GOTOPAGE. Visio versions 4.0 and later accept either style.</span></span> 
  

