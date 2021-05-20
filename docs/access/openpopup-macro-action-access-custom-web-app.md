---
title: 'OpenPopup 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 850de802-e417-4884-8d14-571de52aa391
description: 在弹出窗口中打开指定的视图。
ms.openlocfilehash: 2a8b67fcbf31c42f13b36f06d14d9d046be68c68
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427386"
---
# <a name="openpopup-macro-action-access-custom-web-app"></a><span data-ttu-id="d692e-103">OpenPopup 宏操作 (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="d692e-103">OpenPopup Macro Action (Access custom web app)</span></span>

<span data-ttu-id="d692e-104">在弹出窗口中打开指定的视图。</span><span class="sxs-lookup"><span data-stu-id="d692e-104">Opens the specified view in a popup window.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d692e-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="d692e-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d692e-107">语法</span><span class="sxs-lookup"><span data-stu-id="d692e-107">Syntax</span></span>

 <span data-ttu-id="d692e-108">**OpenPopup** (*View*、 *Where=*、 *Order By*) </span><span class="sxs-lookup"><span data-stu-id="d692e-108">**OpenPopup** (*View*, *Where=*, *Order By*)</span></span> 
  
<span data-ttu-id="d692e-109">**OpenPopup** 操作包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="d692e-109">The **OpenPopup** action contains the following arguments.</span></span> 
  
|<span data-ttu-id="d692e-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="d692e-110">**Argument name**</span></span>|<span data-ttu-id="d692e-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d692e-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="d692e-112">*View*</span><span class="sxs-lookup"><span data-stu-id="d692e-112">*View*</span></span>  <br/> |<span data-ttu-id="d692e-113">要打开的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="d692e-113">The name of the view to open.</span></span>  <br/> |
| <span data-ttu-id="d692e-114">*Where=*</span><span class="sxs-lookup"><span data-stu-id="d692e-114">*Where=*</span></span>  <br/> |<span data-ttu-id="d692e-115">一个有效的 SQL WHERE 子句 (没有单词 WHERE) 来限制视图中的记录。</span><span class="sxs-lookup"><span data-stu-id="d692e-115">A valid SQL WHERE clause (without the word WHERE) that restricts the records in the view.</span></span>  <br/> |
| <span data-ttu-id="d692e-116">*Order By*</span><span class="sxs-lookup"><span data-stu-id="d692e-116">*Order By*</span></span>  <br/> |<span data-ttu-id="d692e-117">一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。</span><span class="sxs-lookup"><span data-stu-id="d692e-117">A string expression that includes the name of the field or fields on which to sort records and the optional ASC or DESC keywords.</span></span> <span data-ttu-id="d692e-118">默认情况下，此参数为空。</span><span class="sxs-lookup"><span data-stu-id="d692e-118">By default, this argument is blank.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d692e-119">备注</span><span class="sxs-lookup"><span data-stu-id="d692e-119">Remarks</span></span>

<span data-ttu-id="d692e-120">处理 **OpenPopup 操作后，当前** 宏结束。</span><span class="sxs-lookup"><span data-stu-id="d692e-120">The current macro ends once the **OpenPopup** action is processed.</span></span> 
  
<span data-ttu-id="d692e-121">调用 **OpenPopup** 操作时，将清除用户应用的任何排序或筛选。</span><span class="sxs-lookup"><span data-stu-id="d692e-121">Any sorting or filtering applied by the user is cleared when the **OpenPopup** action is called.</span></span> 
  
<span data-ttu-id="d692e-122">*OrderBy* 参数是您希望对记录进行排序的一个或多个字段的名称。</span><span class="sxs-lookup"><span data-stu-id="d692e-122">The  *OrderBy*  argument is the name of the field or fields on which you want to sort records.</span></span> <span data-ttu-id="d692e-123">如果使用多个字段名称，需用逗号 (,) 分隔每个名称。</span><span class="sxs-lookup"><span data-stu-id="d692e-123">When you use more than one field name, separate the names with a comma (,).</span></span> 
  
<span data-ttu-id="d692e-124">设置  *OrderBy 参数*  时，默认情况下记录按升序排序。</span><span class="sxs-lookup"><span data-stu-id="d692e-124">When you set the  *OrderBy*  argument, the records are sorted by default in ascending order.</span></span> 
  

