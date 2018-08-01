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
ms.openlocfilehash: 11b3279582c4cfb0d2c2249c6f4eddd7f0260b49
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774817"
---
# <a name="displaying-table-controls"></a><span data-ttu-id="8d907-103">显示表控件</span><span class="sxs-lookup"><span data-stu-id="8d907-103">Displaying Table Controls</span></span>

  
  
<span data-ttu-id="8d907-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8d907-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8d907-105">有许多不同类型的控件，无特有的 MAPI。</span><span class="sxs-lookup"><span data-stu-id="8d907-105">There are many different types of controls, none unique to MAPI.</span></span> <span data-ttu-id="8d907-106">但是，MAPI 定义了使用自己结构[BuildDisplayTable](builddisplaytable.md)来描述数据所涉及的每个控件的唯一一套与结合使用。</span><span class="sxs-lookup"><span data-stu-id="8d907-106">However, MAPI defines its own structures that are used in conjunction with [BuildDisplayTable](builddisplaytable.md) to describe the unique set of data involved with each control.</span></span> 
  
<span data-ttu-id="8d907-107">下表列出了描述每种类型的控件的结构。</span><span class="sxs-lookup"><span data-stu-id="8d907-107">The following table lists the structures that describe each type of control.</span></span> 
  
|<span data-ttu-id="8d907-108">**控制结构**</span><span class="sxs-lookup"><span data-stu-id="8d907-108">**Control structure**</span></span>|<span data-ttu-id="8d907-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="8d907-109">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8d907-110">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="8d907-110">DTBLBUTTON</span></span>](dtblbutton.md) <br/> |<span data-ttu-id="8d907-111">描述一个按钮控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-111">Describes a button control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-112">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="8d907-112">DTBLCHECKBOX</span></span>](dtblcheckbox.md) <br/> |<span data-ttu-id="8d907-113">描述的复选框控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-113">Describes a check box control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-114">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="8d907-114">DTBLCOMBOBOX</span></span>](dtblcombobox.md) <br/> |<span data-ttu-id="8d907-115">介绍组合框控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-115">Describes a combo box control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-116">DTBLDDLBX</span><span class="sxs-lookup"><span data-stu-id="8d907-116">DTBLDDLBX</span></span>](dtblddlbx.md) <br/> |<span data-ttu-id="8d907-117">描述的下拉列表框控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-117">Describes a drop-down list box control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-118">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="8d907-118">DTBLEDIT</span></span>](dtbledit.md) <br/> |<span data-ttu-id="8d907-119">介绍编辑控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-119">Describes an edit control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-120">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="8d907-120">DTBLGROUPBOX</span></span>](dtblgroupbox.md) <br/> |<span data-ttu-id="8d907-121">介绍组框控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-121">Describes a group box control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-122">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="8d907-122">DTBLLABEL</span></span>](dtbllabel.md) <br/> |<span data-ttu-id="8d907-123">介绍 label 控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-123">Describes a label control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-124">DTBLLBX</span><span class="sxs-lookup"><span data-stu-id="8d907-124">DTBLLBX</span></span>](dtbllbx.md) <br/> |<span data-ttu-id="8d907-125">描述列表框控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-125">Describes a list box control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-126">DTBLMVDDLBOX</span><span class="sxs-lookup"><span data-stu-id="8d907-126">DTBLMVDDLBOX</span></span>](dtblmvddlbox.md) <br/> |<span data-ttu-id="8d907-127">介绍了一个多值下拉列表框控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-127">Describes a multiple-value drop-down list box control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-128">DTBLMVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="8d907-128">DTBLMVLISTBOX</span></span>](dtblmvlistbox.md) <br/> |<span data-ttu-id="8d907-129">介绍了一个多值列表框控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-129">Describes a multiple-value list box control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-130">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="8d907-130">DTBLPAGE</span></span>](dtblpage.md) <br/> |<span data-ttu-id="8d907-131">描述的选项卡式的页面控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-131">Describes a tabbed page control.</span></span>  <br/> |
|[<span data-ttu-id="8d907-132">DTBLRADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="8d907-132">DTBLRADIOBUTTON</span></span>](dtblradiobutton.md) <br/> |<span data-ttu-id="8d907-133">介绍选项按钮控件。</span><span class="sxs-lookup"><span data-stu-id="8d907-133">Describes an option button control.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8d907-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d907-134">See also</span></span>



[<span data-ttu-id="8d907-135">显示表实现</span><span class="sxs-lookup"><span data-stu-id="8d907-135">Display Table Implementation</span></span>](display-table-implementation.md)

