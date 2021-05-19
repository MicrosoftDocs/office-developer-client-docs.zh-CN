---
title: 'SetVariable Macro Action (Access 自定义 Web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: a4ffbd02-eed7-43ed-9da2-f0d1ff5d8014
description: 可以使用 SetVariable 操作创建一个临时变量，并设置为特定值。 然后，可以在后续操作中将变量用作条件或参数，也可以将变量用于 UI 或宏 (用户界面) 变量。
ms.openlocfilehash: 54c23868a5bfb66a2fb08465361583c6e9b5ed49
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433918"
---
# <a name="setvariable-macro-action-access-custom-web-app"></a><span data-ttu-id="3a18d-104">SetVariable Macro Action (Access 自定义 Web app) </span><span class="sxs-lookup"><span data-stu-id="3a18d-104">SetVariable Macro Action (Access custom web app)</span></span>

<span data-ttu-id="3a18d-105">可以使用 **SetVariable** 操作创建一个临时变量，并设置为特定值。</span><span class="sxs-lookup"><span data-stu-id="3a18d-105">You can use the **SetVariable** action to create a temporary variable and set it to a specific value.</span></span> <span data-ttu-id="3a18d-106">然后，可以在后续操作中将变量用作条件或参数，也可以将变量用于 UI 或宏 (用户界面) 变量。</span><span class="sxs-lookup"><span data-stu-id="3a18d-106">The variable can then be used as a condition or argument in subsequent actions, or you can use the variable in another user interface (UI) macro.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3a18d-p103">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="3a18d-p103">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="3a18d-109">设置</span><span class="sxs-lookup"><span data-stu-id="3a18d-109">Setting</span></span>

<span data-ttu-id="3a18d-110">**SetVariable** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="3a18d-110">The **SetVariable** action has the following arguments.</span></span> 
  
|<span data-ttu-id="3a18d-111">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="3a18d-111">**Action argument**</span></span>|<span data-ttu-id="3a18d-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="3a18d-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3a18d-113">"变量"</span><span class="sxs-lookup"><span data-stu-id="3a18d-113">**Variable**</span></span> <br/> |<span data-ttu-id="3a18d-114">请输入临时变量的名称。</span><span class="sxs-lookup"><span data-stu-id="3a18d-114">Enter the name of the temporary variable.</span></span>  <br/> |
|<span data-ttu-id="3a18d-115">**值 =**</span><span class="sxs-lookup"><span data-stu-id="3a18d-115">**Value =**</span></span> <br/> |<span data-ttu-id="3a18d-116">请输入将用来设置此临时变量的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="3a18d-116">Enter an expression that will be used to set the value for this temporary variable.</span></span> <span data-ttu-id="3a18d-117">不要将等号的表达式 () **=** 表达式。</span><span class="sxs-lookup"><span data-stu-id="3a18d-117">Do not precede the expression with the equal (**=** ) sign.</span></span> <span data-ttu-id="3a18d-118">You can click the **Build** button ![Formula](media/buildbut_ZA06047218.gif "Formula") to use the Expression Builder to set this argument.</span><span class="sxs-lookup"><span data-stu-id="3a18d-118">You can click the **Build** button ![Formula](media/buildbut_ZA06047218.gif "Formula") to use the Expression Builder to set this argument.</span></span>  <br/> |
   

