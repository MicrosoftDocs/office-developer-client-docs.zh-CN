---
title: 'StopMacro 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: af28534b-6f0d-43ee-ae89-ee2f85da1af1
description: 可以使用 StopMacro 操作停止当前运行的宏。
ms.openlocfilehash: 8b80422a297647d556fb4b20cc15fb93e8853466
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429493"
---
# <a name="stopmacro-macro-action-access-custom-web-app"></a><span data-ttu-id="04de5-103">StopMacro 宏操作 (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="04de5-103">StopMacro Macro Action (Access custom web app)</span></span>

<span data-ttu-id="04de5-104">可以使用 **StopMacro** 操作停止当前运行的宏。</span><span class="sxs-lookup"><span data-stu-id="04de5-104">You can use the **StopMacro** action to stop the currently running macro.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="04de5-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="04de5-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="04de5-107">设置</span><span class="sxs-lookup"><span data-stu-id="04de5-107">Setting</span></span>

<span data-ttu-id="04de5-108">**StopMacro** 操作没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="04de5-108">The **StopMacro** action doesn't have any arguments.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="04de5-109">备注</span><span class="sxs-lookup"><span data-stu-id="04de5-109">Remarks</span></span>

<span data-ttu-id="04de5-110">当条件需要停止宏时，通常使用此操作。</span><span class="sxs-lookup"><span data-stu-id="04de5-110">You typically use this action when a condition makes it necessary to stop the macro.</span></span> <span data-ttu-id="04de5-111">例如，您可能在 UI (用户界面) 打开一个视图，该视图显示在当前视图中输入的日期的每日订单总数。</span><span class="sxs-lookup"><span data-stu-id="04de5-111">For example, you might create a user interface (UI) macro that opens a view showing the daily order totals for the date entered in the current view.</span></span> <span data-ttu-id="04de5-112">可以使用条件表达式确保对话框中的"订单日期"控件包含有效日期。</span><span class="sxs-lookup"><span data-stu-id="04de5-112">You could use a conditional expression to be sure that the Order Date control on the dialog box contains a valid date.</span></span> <span data-ttu-id="04de5-113">如果没有 **，MessageBox** 操作可以显示错误消息， **并且 StopMacro** 操作可以停止 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="04de5-113">If it doesn't, the **MessageBox** action can display an error message and the **StopMacro** action can stop the UI macro.</span></span> 
  

