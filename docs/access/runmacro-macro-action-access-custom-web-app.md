---
title: RunMacro 宏操作 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 59ba365d-cff5-4126-bc22-4d5a37578aab
description: 可以使用 RunMacro 操作运行用户界面 (UI) 宏。
ms.openlocfilehash: 98e3b17a6c64fa12ac37e4551d45714c873f5ccb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307964"
---
# <a name="runmacro-macro-action-access-custom-web-app"></a><span data-ttu-id="c4fde-103">RunMacro 宏操作 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="c4fde-103">RunMacro Macro Action (Access custom web app)</span></span>

<span data-ttu-id="c4fde-104">可以使用**RunMacro**操作运行用户界面 (UI) 宏。</span><span class="sxs-lookup"><span data-stu-id="c4fde-104">You can use the **RunMacro** action to run a user interface (UI) macro.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c4fde-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="c4fde-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="c4fde-107">设置</span><span class="sxs-lookup"><span data-stu-id="c4fde-107">Setting</span></span>

<span data-ttu-id="c4fde-108">**RunMacro** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="c4fde-108">The **RunMacro** action has the following arguments.</span></span> 
  
|<span data-ttu-id="c4fde-109">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="c4fde-109">**Action argument**</span></span>|<span data-ttu-id="c4fde-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="c4fde-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c4fde-111">**宏名**</span><span class="sxs-lookup"><span data-stu-id="c4fde-111">**Macro Name**</span></span> <br/> |<span data-ttu-id="c4fde-112">要运行的 UI 宏的名称。</span><span class="sxs-lookup"><span data-stu-id="c4fde-112">The name of the UI macro to run.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c4fde-113">注解</span><span class="sxs-lookup"><span data-stu-id="c4fde-113">Remarks</span></span>

<span data-ttu-id="c4fde-114">当您运行包含**runmacro**操作的 UI 宏, 并且它达到**runmacro**操作时, Access 将运行被调用的 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="c4fde-114">When you run a UI macro containing the **RunMacro** action, and it reaches the **RunMacro** action, Access runs the called UI macro.</span></span> <span data-ttu-id="c4fde-115">当调用的 ui 宏完成时, Access 将返回到原始 ui 宏, 并运行下一个操作。</span><span class="sxs-lookup"><span data-stu-id="c4fde-115">When the called UI macro has finished, Access returns to the original UI macro and runs the next action.</span></span> 
  

