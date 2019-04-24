---
title: GoToControl 宏操作（Access 自定义 Web 应用）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 6c286821-67d6-4d96-973a-bca7934c7672
description: 可以使用 GoToControl 操作将焦点移动到打开视图的当前记录中的指定控件。
ms.openlocfilehash: 2368933a6277615554a565d3bdd973f7d1f366f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302574"
---
# <a name="gotocontrol-macro-action-access-custom-web-app"></a><span data-ttu-id="b4bb5-103">GoToControl 宏操作（Access 自定义 Web 应用）</span><span class="sxs-lookup"><span data-stu-id="b4bb5-103">GoToControl Macro Action (Access custom web app)</span></span>

<span data-ttu-id="b4bb5-104">可以使用 **GoToControl** 操作将焦点移动到打开视图的当前记录中的指定控件。</span><span class="sxs-lookup"><span data-stu-id="b4bb5-104">You can use the **GoToControl** action to move the focus to the specified control in the current record of the open view.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b4bb5-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="b4bb5-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="b4bb5-107">设置</span><span class="sxs-lookup"><span data-stu-id="b4bb5-107">Setting</span></span>

<span data-ttu-id="b4bb5-108">**GoToControl** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="b4bb5-108">The **GoToControl** action has the following argument.</span></span> 
  
|<span data-ttu-id="b4bb5-109">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="b4bb5-109">**Action argument**</span></span>|<span data-ttu-id="b4bb5-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="b4bb5-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4bb5-111">**控件名称**</span><span class="sxs-lookup"><span data-stu-id="b4bb5-111">**Control Name**</span></span> <br/> |<span data-ttu-id="b4bb5-112">希望获得焦点的字段或控件的名称。</span><span class="sxs-lookup"><span data-stu-id="b4bb5-112">The name of the field or control where you want the focus.</span></span> <span data-ttu-id="b4bb5-113">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="b4bb5-113">This is a required argument.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b4bb5-114">说明</span><span class="sxs-lookup"><span data-stu-id="b4bb5-114">Remarks</span></span>

<span data-ttu-id="b4bb5-115">当你希望特定字段或控件获得焦点时，可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="b4bb5-115">You can use this action when you want a particular field or control to have the focus.</span></span> <span data-ttu-id="b4bb5-116">你可以使用此操作以根据特定的条件在表单中导航。</span><span class="sxs-lookup"><span data-stu-id="b4bb5-116">You can also use this action to navigate in a form according to certain conditions.</span></span> <span data-ttu-id="b4bb5-117">例如，如果用户输入婚姻控件不能在健康保险窗体，焦点可以自动跳过配偶姓名控件并移动到下一个控件。</span><span class="sxs-lookup"><span data-stu-id="b4bb5-117">For example, if the user enters No in a Married control on a health insurance form, the focus can automatically skip the Spouse/partner Name control and move to the next control.</span></span>
  

