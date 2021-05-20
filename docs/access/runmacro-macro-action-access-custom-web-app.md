---
title: 'RunMacro 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 59ba365d-cff5-4126-bc22-4d5a37578aab
description: 可以使用 RunMacro 操作在 UI (运行用户界面) 宏。
ms.openlocfilehash: 98e3b17a6c64fa12ac37e4551d45714c873f5ccb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438440"
---
# <a name="runmacro-macro-action-access-custom-web-app"></a><span data-ttu-id="30b10-103">RunMacro 宏操作 (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="30b10-103">RunMacro Macro Action (Access custom web app)</span></span>

<span data-ttu-id="30b10-104">可以使用 **RunMacro** 操作在 UI 宏中 (用户界面) 用户界面。</span><span class="sxs-lookup"><span data-stu-id="30b10-104">You can use the **RunMacro** action to run a user interface (UI) macro.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="30b10-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="30b10-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="30b10-107">设置</span><span class="sxs-lookup"><span data-stu-id="30b10-107">Setting</span></span>

<span data-ttu-id="30b10-108">**RunMacro** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="30b10-108">The **RunMacro** action has the following arguments.</span></span> 
  
|<span data-ttu-id="30b10-109">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="30b10-109">**Action argument**</span></span>|<span data-ttu-id="30b10-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="30b10-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="30b10-111">**宏名**</span><span class="sxs-lookup"><span data-stu-id="30b10-111">**Macro Name**</span></span> <br/> |<span data-ttu-id="30b10-112">要运行的 UI 宏的名称。</span><span class="sxs-lookup"><span data-stu-id="30b10-112">The name of the UI macro to run.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="30b10-113">备注</span><span class="sxs-lookup"><span data-stu-id="30b10-113">Remarks</span></span>

<span data-ttu-id="30b10-114">运行包含 **RunMacro** 操作且到达 **RunMacro** 操作时，Access 将运行调用的 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="30b10-114">When you run a UI macro containing the **RunMacro** action, and it reaches the **RunMacro** action, Access runs the called UI macro.</span></span> <span data-ttu-id="30b10-115">调用的 UI 宏完成后，Access 将返回到原始 UI 宏并运行下一个操作。</span><span class="sxs-lookup"><span data-stu-id="30b10-115">When the called UI macro has finished, Access returns to the original UI macro and runs the next action.</span></span> 
  

