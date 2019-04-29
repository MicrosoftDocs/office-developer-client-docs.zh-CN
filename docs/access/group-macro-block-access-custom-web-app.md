---
title: Group 宏块 (Access 自定义 web 应用)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 312bcad2-b364-4b4c-a8f9-40e11330bde0
description: Group 语句使您能够指定宏内可展开或折叠的操作块。
ms.openlocfilehash: b90f8e305baf23e9df7b070c879f3bc2f7d59311
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418776"
---
# <a name="group-macro-block-access-custom-web-app"></a><span data-ttu-id="1a547-103">Group 宏块 (Access 自定义 web 应用)</span><span class="sxs-lookup"><span data-stu-id="1a547-103">Group Macro Block (Access custom web app)</span></span>

<span data-ttu-id="1a547-104">**Group**语句使您能够指定宏内可展开或折叠的操作块。</span><span class="sxs-lookup"><span data-stu-id="1a547-104">The **Group** statement enables you to specify a block of actions within a macro that you can expand or collapse.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1a547-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="1a547-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="1a547-107">设置</span><span class="sxs-lookup"><span data-stu-id="1a547-107">Setting</span></span>

<span data-ttu-id="1a547-108">**Group** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="1a547-108">The **Group** action has the following arguments.</span></span> 
  
|<span data-ttu-id="1a547-109">**参数**</span><span class="sxs-lookup"><span data-stu-id="1a547-109">**Argument**</span></span>|<span data-ttu-id="1a547-110">**必需**</span><span class="sxs-lookup"><span data-stu-id="1a547-110">**Required**</span></span>|<span data-ttu-id="1a547-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="1a547-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a547-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="1a547-112">**Description**</span></span> <br/> |<span data-ttu-id="1a547-113">否</span><span class="sxs-lookup"><span data-stu-id="1a547-113">No</span></span>  <br/> |<span data-ttu-id="1a547-114">一个在折叠时显示为组标题的字符串。</span><span class="sxs-lookup"><span data-stu-id="1a547-114">A string that appears as the title of a group when it is collapsed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1a547-115">说明</span><span class="sxs-lookup"><span data-stu-id="1a547-115">Remarks</span></span>

<span data-ttu-id="1a547-116">**Group**语句不定义可单独执行的宏区域。</span><span class="sxs-lookup"><span data-stu-id="1a547-116">The **Group** statement does not define a region of a macro that can be executed separately.</span></span> 
  

