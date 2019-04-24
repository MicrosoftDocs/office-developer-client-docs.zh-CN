---
title: 显示表控件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0882be14-573c-440c-954f-76ef70eea33e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 37f6cd0320894d500416672c3dd0d90ee3324b40
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337028"
---
# <a name="displaying-table-controls"></a><span data-ttu-id="10b72-103">显示表控件</span><span class="sxs-lookup"><span data-stu-id="10b72-103">Displaying Table Controls</span></span>

  
  
<span data-ttu-id="10b72-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="10b72-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="10b72-105">有许多不同类型的控件, MAPI 都不唯一。</span><span class="sxs-lookup"><span data-stu-id="10b72-105">There are many different types of controls, none unique to MAPI.</span></span> <span data-ttu-id="10b72-106">但是, MAPI 定义了自己的结构, 这些结构与[BuildDisplayTable](builddisplaytable.md)结合使用, 以描述每个控件所涉及的独特数据集。</span><span class="sxs-lookup"><span data-stu-id="10b72-106">However, MAPI defines its own structures that are used in conjunction with [BuildDisplayTable](builddisplaytable.md) to describe the unique set of data involved with each control.</span></span> 
  
<span data-ttu-id="10b72-107">下表列出了描述每种类型的控件的结构。</span><span class="sxs-lookup"><span data-stu-id="10b72-107">The following table lists the structures that describe each type of control.</span></span> 
  
|<span data-ttu-id="10b72-108">**控制结构**</span><span class="sxs-lookup"><span data-stu-id="10b72-108">**Control structure**</span></span>|<span data-ttu-id="10b72-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="10b72-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="10b72-110">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="10b72-110">DTBLBUTTON</span></span>](dtblbutton.md) <br/> |<span data-ttu-id="10b72-111">描述按钮控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-111">Describes a button control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-112">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="10b72-112">DTBLCHECKBOX</span></span>](dtblcheckbox.md) <br/> |<span data-ttu-id="10b72-113">描述复选框控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-113">Describes a check box control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-114">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="10b72-114">DTBLCOMBOBOX</span></span>](dtblcombobox.md) <br/> |<span data-ttu-id="10b72-115">描述组合框控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-115">Describes a combo box control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-116">DTBLDDLBX</span><span class="sxs-lookup"><span data-stu-id="10b72-116">DTBLDDLBX</span></span>](dtblddlbx.md) <br/> |<span data-ttu-id="10b72-117">描述下拉列表框控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-117">Describes a drop-down list box control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-118">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="10b72-118">DTBLEDIT</span></span>](dtbledit.md) <br/> |<span data-ttu-id="10b72-119">介绍编辑控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-119">Describes an edit control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-120">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="10b72-120">DTBLGROUPBOX</span></span>](dtblgroupbox.md) <br/> |<span data-ttu-id="10b72-121">描述分组框控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-121">Describes a group box control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-122">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="10b72-122">DTBLLABEL</span></span>](dtbllabel.md) <br/> |<span data-ttu-id="10b72-123">介绍标签控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-123">Describes a label control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-124">DTBLLBX</span><span class="sxs-lookup"><span data-stu-id="10b72-124">DTBLLBX</span></span>](dtbllbx.md) <br/> |<span data-ttu-id="10b72-125">描述列表框控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-125">Describes a list box control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-126">DTBLMVDDLBOX</span><span class="sxs-lookup"><span data-stu-id="10b72-126">DTBLMVDDLBOX</span></span>](dtblmvddlbox.md) <br/> |<span data-ttu-id="10b72-127">介绍多值下拉列表框控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-127">Describes a multiple-value drop-down list box control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-128">DTBLMVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="10b72-128">DTBLMVLISTBOX</span></span>](dtblmvlistbox.md) <br/> |<span data-ttu-id="10b72-129">描述多值列表框控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-129">Describes a multiple-value list box control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-130">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="10b72-130">DTBLPAGE</span></span>](dtblpage.md) <br/> |<span data-ttu-id="10b72-131">介绍选项卡式页面控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-131">Describes a tabbed page control.</span></span>  <br/> |
|[<span data-ttu-id="10b72-132">DTBLRADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="10b72-132">DTBLRADIOBUTTON</span></span>](dtblradiobutton.md) <br/> |<span data-ttu-id="10b72-133">介绍选项按钮控件。</span><span class="sxs-lookup"><span data-stu-id="10b72-133">Describes an option button control.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="10b72-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10b72-134">See also</span></span>



[<span data-ttu-id="10b72-135">显示表实现</span><span class="sxs-lookup"><span data-stu-id="10b72-135">Display Table Implementation</span></span>](display-table-implementation.md)

