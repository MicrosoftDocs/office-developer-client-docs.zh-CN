---
title: OpenPopup 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 850de802-e417-4884-8d14-571de52aa391
description: 在弹出窗口中打开指定的视图。
ms.openlocfilehash: 01e0086dc0b54837cf5f095ec6ac5701b5b0b219
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773575"
---
# <a name="openpopup-macro-action-access-custom-web-app"></a><span data-ttu-id="97d6c-103">OpenPopup 宏操作 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="97d6c-103">OpenPopup Macro Action (Access custom web app)</span></span>

<span data-ttu-id="97d6c-104">在弹出窗口中打开指定的视图。</span><span class="sxs-lookup"><span data-stu-id="97d6c-104">Opens the specified view in a popup window.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="97d6c-p101">[!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="97d6c-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="97d6c-107">语法</span><span class="sxs-lookup"><span data-stu-id="97d6c-107">Syntax</span></span>

 <span data-ttu-id="97d6c-108">**OpenPopup**(在*视图*中，*其中 =*，*按顺序*)</span><span class="sxs-lookup"><span data-stu-id="97d6c-108">**OpenPopup** (*View*, *Where=*, *Order By*)</span></span> 
  
<span data-ttu-id="97d6c-109">**OpenPopup**操作包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="97d6c-109">The **OpenPopup** action contains the following arguments.</span></span> 
  
|<span data-ttu-id="97d6c-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="97d6c-110">**Argument name**</span></span>|<span data-ttu-id="97d6c-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="97d6c-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="97d6c-112">*View*</span><span class="sxs-lookup"><span data-stu-id="97d6c-112">*View*</span></span>  <br/> |<span data-ttu-id="97d6c-113">要打开的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="97d6c-113">The name of the view to open.</span></span>  <br/> |
| <span data-ttu-id="97d6c-114">*其中 =*</span><span class="sxs-lookup"><span data-stu-id="97d6c-114">*Where=*</span></span>  <br/> |<span data-ttu-id="97d6c-115">关键字的有效 SQL WHERE 子句 (不带有单词其中)，它将在视图中的记录。</span><span class="sxs-lookup"><span data-stu-id="97d6c-115">A valid SQL WHERE clause (without the word WHERE) that restricts the records in the view.</span></span>  <br/> |
| <span data-ttu-id="97d6c-116">*Order By*</span><span class="sxs-lookup"><span data-stu-id="97d6c-116">*Order By*</span></span>  <br/> |<span data-ttu-id="97d6c-117">一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。</span><span class="sxs-lookup"><span data-stu-id="97d6c-117">A string expression that includes the name of the field or fields on which to sort records and the optional ASC or DESC keywords.</span></span> <span data-ttu-id="97d6c-118">默认情况下，此参数为空。</span><span class="sxs-lookup"><span data-stu-id="97d6c-118">By default, this argument is blank.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="97d6c-119">说明</span><span class="sxs-lookup"><span data-stu-id="97d6c-119">Remarks</span></span>

<span data-ttu-id="97d6c-120">当前的宏结束后处理**OpenPopup**操作。</span><span class="sxs-lookup"><span data-stu-id="97d6c-120">The current macro ends once the **OpenPopup** action is processed.</span></span> 
  
<span data-ttu-id="97d6c-121">调用**OpenPopup**操作时，会清除任何排序或筛选用户应用的。</span><span class="sxs-lookup"><span data-stu-id="97d6c-121">Any sorting or filtering applied by the user is cleared when the **OpenPopup** action is called.</span></span> 
  
<span data-ttu-id="97d6c-122">*OrderBy*参数是在您要对记录进行排序的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="97d6c-122">The  *OrderBy*  argument is the name of the field or fields on which you want to sort records.</span></span> <span data-ttu-id="97d6c-123">如果使用多个字段名称，需用逗号 (,) 分隔每个名称。</span><span class="sxs-lookup"><span data-stu-id="97d6c-123">When you use more than one field name, separate the names with a comma (,).</span></span> 
  
<span data-ttu-id="97d6c-124">当设置*OrderBy*参数时，记录将默认情况下按升序排序。</span><span class="sxs-lookup"><span data-stu-id="97d6c-124">When you set the  *OrderBy*  argument, the records are sorted by default in ascending order.</span></span> 
  

