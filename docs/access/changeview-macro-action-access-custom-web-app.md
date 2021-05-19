---
title: 'ChangeView 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7eb20f21-0218-4a2c-9bbc-90218a1e87bc
description: 可以使用 ChangeView 操作在视图之间就地导航。
ms.openlocfilehash: 0c1e27c264a826d38ec2efbd5be9bc6237ad7437
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425356"
---
# <a name="changeview-macro-action-access-custom-web-app"></a><span data-ttu-id="588cd-103">ChangeView 宏操作 (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="588cd-103">ChangeView Macro Action (Access custom web app)</span></span>

<span data-ttu-id="588cd-104">可以使用 **ChangeView** 操作在视图之间就地导航。</span><span class="sxs-lookup"><span data-stu-id="588cd-104">You can use the **ChangeView** action to navigate between views in place.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="588cd-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="588cd-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="588cd-107">设置</span><span class="sxs-lookup"><span data-stu-id="588cd-107">Setting</span></span>

<span data-ttu-id="588cd-108">**ChangeView** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="588cd-108">The **ChangeView** action has the following arguments.</span></span> 
  
|<span data-ttu-id="588cd-109">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="588cd-109">**Action argument**</span></span>|<span data-ttu-id="588cd-110">**必需**</span><span class="sxs-lookup"><span data-stu-id="588cd-110">**Required**</span></span>|<span data-ttu-id="588cd-111">**描述**</span><span class="sxs-lookup"><span data-stu-id="588cd-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="588cd-112">表格</span><span class="sxs-lookup"><span data-stu-id="588cd-112">Table</span></span>  <br/> |<span data-ttu-id="588cd-113">是</span><span class="sxs-lookup"><span data-stu-id="588cd-113">Yes</span></span>  <br/> |<span data-ttu-id="588cd-114">要打开的表的名称。</span><span class="sxs-lookup"><span data-stu-id="588cd-114">The name of the table to open.</span></span>  <br/> |
|<span data-ttu-id="588cd-115">查看</span><span class="sxs-lookup"><span data-stu-id="588cd-115">View</span></span>  <br/> |<span data-ttu-id="588cd-116">是</span><span class="sxs-lookup"><span data-stu-id="588cd-116">Yes</span></span>  <br/> |<span data-ttu-id="588cd-117">要打开的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="588cd-117">The name of the view to open.</span></span>  <br/> |
|<span data-ttu-id="588cd-118">其中</span><span class="sxs-lookup"><span data-stu-id="588cd-118">Where</span></span>  <br/> |<span data-ttu-id="588cd-119">否</span><span class="sxs-lookup"><span data-stu-id="588cd-119">No</span></span>  <br/> |<span data-ttu-id="588cd-120">如果指定，则将替换对象记录源的 Where 条件。</span><span class="sxs-lookup"><span data-stu-id="588cd-120">If specified, replaces the Where condition of the object record source.</span></span>  <br/> |
|<span data-ttu-id="588cd-121">Order By</span><span class="sxs-lookup"><span data-stu-id="588cd-121">Order By</span></span>  <br/> |<span data-ttu-id="588cd-122">否</span><span class="sxs-lookup"><span data-stu-id="588cd-122">No</span></span>  <br/> |<span data-ttu-id="588cd-123">一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。</span><span class="sxs-lookup"><span data-stu-id="588cd-123">A string expression that includes the name of the field or fields on which to sort records and the optional ASC or DESC keywords.</span></span> <span data-ttu-id="588cd-124">默认情况下，此参数为空。</span><span class="sxs-lookup"><span data-stu-id="588cd-124">By default, this argument is blank.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="588cd-125">备注</span><span class="sxs-lookup"><span data-stu-id="588cd-125">Remarks</span></span>

<span data-ttu-id="588cd-126">调用 **ChangeView** 操作时，将清除用户应用的任何排序或筛选。</span><span class="sxs-lookup"><span data-stu-id="588cd-126">Any sorting or filtering applied by the user is cleared when the **ChangeView** action is called.</span></span> 
  
<span data-ttu-id="588cd-127">*OrderBy* 参数是您希望对记录进行排序的一个或多个字段的名称。</span><span class="sxs-lookup"><span data-stu-id="588cd-127">The  *OrderBy*  argument is the name of the field or fields on which you want to sort records.</span></span> <span data-ttu-id="588cd-128">如果使用多个字段名称，需用逗号 (,) 分隔每个名称。</span><span class="sxs-lookup"><span data-stu-id="588cd-128">When you use more than one field name, separate the names with a comma (,).</span></span> 
  
<span data-ttu-id="588cd-129">设置  *OrderBy 参数*  时，默认情况下记录按升序排序。</span><span class="sxs-lookup"><span data-stu-id="588cd-129">When you set the  *OrderBy*  argument, the records are sorted by default in ascending order.</span></span> 
  

