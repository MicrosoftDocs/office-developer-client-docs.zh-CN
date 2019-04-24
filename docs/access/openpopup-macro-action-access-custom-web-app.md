---
title: OpenPopup 宏操作 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 850de802-e417-4884-8d14-571de52aa391
description: 在弹出窗口中打开指定的视图。
ms.openlocfilehash: 2a8b67fcbf31c42f13b36f06d14d9d046be68c68
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308111"
---
# <a name="openpopup-macro-action-access-custom-web-app"></a><span data-ttu-id="baa2b-103">OpenPopup 宏操作 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="baa2b-103">OpenPopup Macro Action (Access custom web app)</span></span>

<span data-ttu-id="baa2b-104">在弹出窗口中打开指定的视图。</span><span class="sxs-lookup"><span data-stu-id="baa2b-104">Opens the specified view in a popup window.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="baa2b-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="baa2b-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="baa2b-107">语法</span><span class="sxs-lookup"><span data-stu-id="baa2b-107">Syntax</span></span>

 <span data-ttu-id="baa2b-108">**OpenPopup**(*View*, *Where =*, *Order By*)</span><span class="sxs-lookup"><span data-stu-id="baa2b-108">**OpenPopup** (*View*, *Where=*, *Order By*)</span></span> 
  
<span data-ttu-id="baa2b-109">**OpenPopup**操作包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="baa2b-109">The **OpenPopup** action contains the following arguments.</span></span> 
  
|<span data-ttu-id="baa2b-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="baa2b-110">**Argument name**</span></span>|<span data-ttu-id="baa2b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="baa2b-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="baa2b-112">*View*</span><span class="sxs-lookup"><span data-stu-id="baa2b-112">*View*</span></span>  <br/> |<span data-ttu-id="baa2b-113">要打开的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="baa2b-113">The name of the view to open.</span></span>  <br/> |
| <span data-ttu-id="baa2b-114">*Where =*</span><span class="sxs-lookup"><span data-stu-id="baa2b-114">*Where=*</span></span>  <br/> |<span data-ttu-id="baa2b-115">限制视图中的记录的有效 SQL WHERE 子句 (不带 word WHERE)。</span><span class="sxs-lookup"><span data-stu-id="baa2b-115">A valid SQL WHERE clause (without the word WHERE) that restricts the records in the view.</span></span>  <br/> |
| <span data-ttu-id="baa2b-116">*Order By*</span><span class="sxs-lookup"><span data-stu-id="baa2b-116">*Order By*</span></span>  <br/> |<span data-ttu-id="baa2b-117">一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。</span><span class="sxs-lookup"><span data-stu-id="baa2b-117">A string expression that includes the name of the field or fields on which to sort records and the optional ASC or DESC keywords.</span></span> <span data-ttu-id="baa2b-118">默认情况下, 此参数为空。</span><span class="sxs-lookup"><span data-stu-id="baa2b-118">By default, this argument is blank.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="baa2b-119">注解</span><span class="sxs-lookup"><span data-stu-id="baa2b-119">Remarks</span></span>

<span data-ttu-id="baa2b-120">处理完**OpenPopup**操作后, 当前宏即会结束。</span><span class="sxs-lookup"><span data-stu-id="baa2b-120">The current macro ends once the **OpenPopup** action is processed.</span></span> 
  
<span data-ttu-id="baa2b-121">调用**OpenPopup**操作时, 将清除用户应用的任何排序或筛选。</span><span class="sxs-lookup"><span data-stu-id="baa2b-121">Any sorting or filtering applied by the user is cleared when the **OpenPopup** action is called.</span></span> 
  
<span data-ttu-id="baa2b-122">*OrderBy*参数是要对记录进行排序所依据的一个或多个字段的名称。</span><span class="sxs-lookup"><span data-stu-id="baa2b-122">The  *OrderBy*  argument is the name of the field or fields on which you want to sort records.</span></span> <span data-ttu-id="baa2b-123">如果使用多个字段名称，需用逗号 (,) 分隔每个名称。</span><span class="sxs-lookup"><span data-stu-id="baa2b-123">When you use more than one field name, separate the names with a comma (,).</span></span> 
  
<span data-ttu-id="baa2b-124">在设置*OrderBy*参数时, 默认情况下将按升序对记录进行排序。</span><span class="sxs-lookup"><span data-stu-id="baa2b-124">When you set the  *OrderBy*  argument, the records are sorted by default in ascending order.</span></span> 
  

