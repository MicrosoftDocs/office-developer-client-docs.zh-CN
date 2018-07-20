---
title: GoToControl 宏操作（Access 自定义 Web 应用）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 6c286821-67d6-4d96-973a-bca7934c7672
description: 可以使用 GoToControl 操作将焦点移动到打开视图的当前记录中的指定控件。
ms.openlocfilehash: ec156d1eb6c510ee38c0268a7b0f51bdde80f887
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773437"
---
# <a name="gotocontrol-macro-action-access-custom-web-app"></a><span data-ttu-id="26e71-103">GoToControl 宏操作（Access 自定义 Web 应用）</span><span class="sxs-lookup"><span data-stu-id="26e71-103">GoToControl Macro Action (Access 2013 custom web app)</span></span>

<span data-ttu-id="26e71-104">可以使用 **GoToControl** 操作将焦点移动到打开视图的当前记录中的指定控件。</span><span class="sxs-lookup"><span data-stu-id="26e71-104">You can use the GoToControl method to move the focus to the specified field or control in the current record of the open form, form datasheet, table datasheet, or query datasheet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="26e71-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-CN/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="26e71-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-CN/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="26e71-107">设置</span><span class="sxs-lookup"><span data-stu-id="26e71-107">Setting</span></span>

<span data-ttu-id="26e71-108">**GoToControl** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="26e71-108">The **RemoveTempVar** action has the following argument.</span></span> 
  
|<span data-ttu-id="26e71-109">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="26e71-109">**Action argument**</span></span>|<span data-ttu-id="26e71-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="26e71-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="26e71-111">**控件名称**</span><span class="sxs-lookup"><span data-stu-id="26e71-111">**Control Name**</span></span> <br/> |<span data-ttu-id="26e71-112">希望获得焦点的字段或控件的名称。</span><span class="sxs-lookup"><span data-stu-id="26e71-112">The name of the field or control for which you want to set the property value.</span></span> <span data-ttu-id="26e71-113">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="26e71-113">This is a required argument.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="26e71-114">说明</span><span class="sxs-lookup"><span data-stu-id="26e71-114">Remarks</span></span>

<span data-ttu-id="26e71-115">当你希望特定字段或控件获得焦点时，可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="26e71-115">You can use this method when you want a particular field or control to have the focus.</span></span> <span data-ttu-id="26e71-116">你可以使用此操作以根据特定的条件在表单中导航。</span><span class="sxs-lookup"><span data-stu-id="26e71-116">You can also use this method to navigate in a form according to certain conditions.</span></span> <span data-ttu-id="26e71-117">例如，如果用户输入婚姻控件不能在健康保险窗体，焦点可以自动跳过配偶姓名控件并移动到下一个控件。</span><span class="sxs-lookup"><span data-stu-id="26e71-117">For example, if the user enters No in a Married control on a health insurance form, the focus can automatically skip the Spouse/partner Name control and move to the next control.</span></span>
  

