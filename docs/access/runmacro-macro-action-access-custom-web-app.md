---
title: RunMacro 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 59ba365d-cff5-4126-bc22-4d5a37578aab
description: 您可以使用 RunMacro 操作运行用户界面 (UI) 宏。
ms.openlocfilehash: 68a59e246c0af8385a17aedcf3da771c720f8fd7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773600"
---
# <a name="runmacro-macro-action-access-custom-web-app"></a><span data-ttu-id="41fbe-103">RunMacro 宏操作 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="41fbe-103">RunMacro Macro Action (Access custom web app)</span></span>

<span data-ttu-id="41fbe-104">您可以使用**RunMacro**操作运行用户界面 (UI) 宏。</span><span class="sxs-lookup"><span data-stu-id="41fbe-104">You can use the **RunMacro** action to run a user interface (UI) macro.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="41fbe-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="41fbe-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="41fbe-107">设置</span><span class="sxs-lookup"><span data-stu-id="41fbe-107">Setting</span></span>

<span data-ttu-id="41fbe-108">**RunMacro** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="41fbe-108">The **RunMacro** action has the following arguments.</span></span> 
  
|<span data-ttu-id="41fbe-109">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="41fbe-109">**Action argument**</span></span>|<span data-ttu-id="41fbe-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="41fbe-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="41fbe-111">**宏名**</span><span class="sxs-lookup"><span data-stu-id="41fbe-111">**Macro Name**</span></span> <br/> |<span data-ttu-id="41fbe-112">要运行的 UI 宏的名称。</span><span class="sxs-lookup"><span data-stu-id="41fbe-112">The name of the UI macro to run.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="41fbe-113">备注</span><span class="sxs-lookup"><span data-stu-id="41fbe-113">Remarks</span></span>

<span data-ttu-id="41fbe-114">当您运行的 UI 宏包含**RunMacro**操作，并会在到达**RunMacro**操作时，Access 将运行该呼叫的 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="41fbe-114">When you run a UI macro containing the **RunMacro** action, and it reaches the **RunMacro** action, Access runs the called UI macro.</span></span> <span data-ttu-id="41fbe-115">在完成呼叫的 UI 宏后，Access 将返回到原来的 UI 宏并运行的下一个操作。</span><span class="sxs-lookup"><span data-stu-id="41fbe-115">When the called UI macro has finished, Access returns to the original UI macro and runs the next action.</span></span> 
  

