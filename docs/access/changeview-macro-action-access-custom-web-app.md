---
title: ChangeView 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7eb20f21-0218-4a2c-9bbc-90218a1e87bc
description: 您可以使用 ChangeView 操作就地视图之间导航。
ms.openlocfilehash: c420846074ef362d3388d40ed8700db0739b7ce0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773454"
---
# <a name="changeview-macro-action-access-custom-web-app"></a><span data-ttu-id="44cce-103">ChangeView 宏操作 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="44cce-103">ChangeView Macro Action (Access custom web app)</span></span>

<span data-ttu-id="44cce-104">您可以使用**ChangeView**操作就地视图之间导航。</span><span class="sxs-lookup"><span data-stu-id="44cce-104">You can use the **ChangeView** action to navigate between views in place.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="44cce-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="44cce-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="44cce-107">设置</span><span class="sxs-lookup"><span data-stu-id="44cce-107">Setting</span></span>

<span data-ttu-id="44cce-108">**ChangeView**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="44cce-108">The **ChangeView** action has the following arguments.</span></span> 
  
|<span data-ttu-id="44cce-109">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="44cce-109">**Action argument**</span></span>|<span data-ttu-id="44cce-110">**必需**</span><span class="sxs-lookup"><span data-stu-id="44cce-110">**Required**</span></span>|<span data-ttu-id="44cce-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="44cce-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44cce-112">Table</span><span class="sxs-lookup"><span data-stu-id="44cce-112">Table</span></span>  <br/> |<span data-ttu-id="44cce-113">可访问</span><span class="sxs-lookup"><span data-stu-id="44cce-113">Yes</span></span>  <br/> |<span data-ttu-id="44cce-114">要打开的表的名称。</span><span class="sxs-lookup"><span data-stu-id="44cce-114">The name of the table to open.</span></span>  <br/> |
|<span data-ttu-id="44cce-115">视图</span><span class="sxs-lookup"><span data-stu-id="44cce-115">View</span></span>  <br/> |<span data-ttu-id="44cce-116">可访问</span><span class="sxs-lookup"><span data-stu-id="44cce-116">Yes</span></span>  <br/> |<span data-ttu-id="44cce-117">要打开的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="44cce-117">The name of the view to open.</span></span>  <br/> |
|<span data-ttu-id="44cce-118">其中</span><span class="sxs-lookup"><span data-stu-id="44cce-118">Where</span></span>  <br/> |<span data-ttu-id="44cce-119">否</span><span class="sxs-lookup"><span data-stu-id="44cce-119">No</span></span>  <br/> |<span data-ttu-id="44cce-120">如果指定，则将替换对象记录源的 Where 条件。</span><span class="sxs-lookup"><span data-stu-id="44cce-120">If specified, replaces the Where condition of the object record source.</span></span>  <br/> |
|<span data-ttu-id="44cce-121">Order By</span><span class="sxs-lookup"><span data-stu-id="44cce-121">Order By</span></span>  <br/> |<span data-ttu-id="44cce-122">否</span><span class="sxs-lookup"><span data-stu-id="44cce-122">No</span></span>  <br/> |<span data-ttu-id="44cce-123">一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。</span><span class="sxs-lookup"><span data-stu-id="44cce-123">A string expression that includes the name of the field or fields on which to sort records and the optional ASC or DESC keywords.</span></span> <span data-ttu-id="44cce-124">默认情况下，此参数为空。</span><span class="sxs-lookup"><span data-stu-id="44cce-124">By default, this argument is blank.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="44cce-125">说明</span><span class="sxs-lookup"><span data-stu-id="44cce-125">Remarks</span></span>

<span data-ttu-id="44cce-126">调用**ChangeView**操作时，会清除任何排序或筛选用户应用的。</span><span class="sxs-lookup"><span data-stu-id="44cce-126">Any sorting or filtering applied by the user is cleared when the **ChangeView** action is called.</span></span> 
  
<span data-ttu-id="44cce-127">*OrderBy*参数是在您要对记录进行排序的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="44cce-127">The  *OrderBy*  argument is the name of the field or fields on which you want to sort records.</span></span> <span data-ttu-id="44cce-128">如果使用多个字段名称，需用逗号 (,) 分隔每个名称。</span><span class="sxs-lookup"><span data-stu-id="44cce-128">When you use more than one field name, separate the names with a comma (,).</span></span> 
  
<span data-ttu-id="44cce-129">当设置*OrderBy*参数时，记录将默认情况下按升序排序。</span><span class="sxs-lookup"><span data-stu-id="44cce-129">When you set the  *OrderBy*  argument, the records are sorted by default in ascending order.</span></span> 
  

