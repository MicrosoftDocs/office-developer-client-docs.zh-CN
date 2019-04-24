---
title: RunDataMacro 宏操作 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: f6010ac5-6c08-4c1b-a811-ff81b30ed5f0
description: 您可以使用 RunDataMacro 操作来运行独立的数据宏。
ms.openlocfilehash: 68c0e5a3837039bdab1165e686adb3bdf2a5b6f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304240"
---
# <a name="rundatamacro-macro-action-access-custom-web-app"></a><span data-ttu-id="910e2-103">RunDataMacro 宏操作 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="910e2-103">RunDataMacro Macro Action (Access custom web app)</span></span>

<span data-ttu-id="910e2-104">您可以使用**RunDataMacro**操作来运行独立的数据宏。</span><span class="sxs-lookup"><span data-stu-id="910e2-104">You can use the **RunDataMacro** action to run a standalone data macro.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="910e2-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="910e2-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="910e2-107">设置</span><span class="sxs-lookup"><span data-stu-id="910e2-107">Setting</span></span>

<span data-ttu-id="910e2-108">**RunDataMacro** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="910e2-108">The **RunDataMacro** action has the following argument.</span></span> 
  
|<span data-ttu-id="910e2-109">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="910e2-109">**Action argument**</span></span>|<span data-ttu-id="910e2-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="910e2-110">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="910e2-111">_宏名_</span><span class="sxs-lookup"><span data-stu-id="910e2-111">_Macro Name_</span></span> <br/> |<span data-ttu-id="910e2-112">要运行的数据宏的名称。</span><span class="sxs-lookup"><span data-stu-id="910e2-112">The name of the data macro to run.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="910e2-113">注解</span><span class="sxs-lookup"><span data-stu-id="910e2-113">Remarks</span></span>

<span data-ttu-id="910e2-114">当您选择要在宏设计器中运行的数据宏时，Access 将确定该数据宏是否需要参数。</span><span class="sxs-lookup"><span data-stu-id="910e2-114">When you select the data macro that you want to run in the macro designer, Access determines if the data macro requires parameters.</span></span> <span data-ttu-id="910e2-115">如果数据宏需要参数, 则将显示文本框, 您可以在其中键入参数。</span><span class="sxs-lookup"><span data-stu-id="910e2-115">If the data macro requires parameters, text boxes appear where you can type in the arguments.</span></span>
  
<span data-ttu-id="910e2-p103">当您运行包含 **RunDataMacro** 操作的宏并且该宏到达 **RunDataMacro** 操作时，Access 将运行调用的数据宏。当调用的数据宏完成时，Access 将返回到原始宏并运行下一操作。</span><span class="sxs-lookup"><span data-stu-id="910e2-p103">When you run a macro that contains the **RunDataMacro** action and it reaches the **RunDataMacro** action, Access runs the called data macro. When the called data macro has finished, Access returns to the original macro and runs the next action.</span></span> 
  

