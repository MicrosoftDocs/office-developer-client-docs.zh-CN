---
title: SetVariable 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: a4ffbd02-eed7-43ed-9da2-f0d1ff5d8014
description: 您可以使用 SetVariable 操作创建一个临时变量并将其设置为特定值。 该变量然后可作为条件或在后续操作的参数或您可以在另一个用户界面 (UI) 宏中使用该变量。
ms.openlocfilehash: 28daa4e8de247fbe4ca0d7a3fa8a908f6d7d885d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773602"
---
# <a name="setvariable-macro-action-access-custom-web-app"></a><span data-ttu-id="2112a-104">SetVariable 宏操作 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="2112a-104">SetVariable Macro Action (Access custom web app)</span></span>

<span data-ttu-id="2112a-105">您可以使用**SetVariable**操作创建一个临时变量并将其设置为特定值。</span><span class="sxs-lookup"><span data-stu-id="2112a-105">You can use the **SetVariable** action to create a temporary variable and set it to a specific value.</span></span> <span data-ttu-id="2112a-106">该变量然后可作为条件或在后续操作的参数或您可以在另一个用户界面 (UI) 宏中使用该变量。</span><span class="sxs-lookup"><span data-stu-id="2112a-106">The variable can then be used as a condition or argument in subsequent actions, or you can use the variable in another user interface (UI) macro.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2112a-p103">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="2112a-p103">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="2112a-109">设置</span><span class="sxs-lookup"><span data-stu-id="2112a-109">Setting</span></span>

<span data-ttu-id="2112a-110">**SetVariable**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="2112a-110">The **SetVariable** action has the following arguments.</span></span> 
  
|<span data-ttu-id="2112a-111">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="2112a-111">**Action argument**</span></span>|<span data-ttu-id="2112a-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="2112a-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2112a-113">"变量"</span><span class="sxs-lookup"><span data-stu-id="2112a-113">**Variable**</span></span> <br/> |<span data-ttu-id="2112a-114">请输入临时变量的名称。</span><span class="sxs-lookup"><span data-stu-id="2112a-114">Enter the name of the temporary variable.</span></span>  <br/> |
|<span data-ttu-id="2112a-115">**值 =**</span><span class="sxs-lookup"><span data-stu-id="2112a-115">**Value =**</span></span> <br/> |<span data-ttu-id="2112a-116">输入将用于设置为临时变量的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="2112a-116">Enter an expression that will be used to set the value for this temporary variable.</span></span> <span data-ttu-id="2112a-117">不要在前对表达式与等 (**=** ) 登录。</span><span class="sxs-lookup"><span data-stu-id="2112a-117">Do not precede the expression with the equal (**=** ) sign.</span></span> <span data-ttu-id="2112a-118">您可以单击![公式](media/buildbut_ZA06047218.gif "公式")中使用表达式生成器设置此参数的**生成**按钮。</span><span class="sxs-lookup"><span data-stu-id="2112a-118">You can click the **Build** button ![Formula](media/buildbut_ZA06047218.gif "Formula") to use the Expression Builder to set this argument.</span></span>  <br/> |
   

