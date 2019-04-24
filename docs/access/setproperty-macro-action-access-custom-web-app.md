---
title: SetProperty 宏操作 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1e97dd95-23f6-4f49-b3b9-2c7261b3a70d
description: 可以使用 SetProperty 操作为视图上的控件设置属性。
ms.openlocfilehash: 1876be32606d66e0570c9e69206a508b8888b157
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307887"
---
# <a name="setproperty-macro-action-access-custom-web-app"></a><span data-ttu-id="9db46-103">SetProperty 宏操作 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="9db46-103">SetProperty Macro Action (Access custom web app)</span></span>

<span data-ttu-id="9db46-104">可以使用**SetProperty**操作为视图上的控件设置属性。</span><span class="sxs-lookup"><span data-stu-id="9db46-104">You can use the **SetProperty** action to set a property for a control on a view.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9db46-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="9db46-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="9db46-107">设置</span><span class="sxs-lookup"><span data-stu-id="9db46-107">Setting</span></span>

<span data-ttu-id="9db46-108">**SetProperty**操作具有下表中列出的参数。</span><span class="sxs-lookup"><span data-stu-id="9db46-108">The **SetProperty** action has the arguments listed in the following table.</span></span> 
  
|<span data-ttu-id="9db46-109">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="9db46-109">**Action argument**</span></span>|<span data-ttu-id="9db46-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="9db46-110">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="9db46-111">_控件名称_</span><span class="sxs-lookup"><span data-stu-id="9db46-111">_Control Name_</span></span> <br/> |<span data-ttu-id="9db46-112">请键入要为其设置属性值的字段或控件的名称。</span><span class="sxs-lookup"><span data-stu-id="9db46-112">Type the name of the field or control for which you want to set the property value.</span></span> <span data-ttu-id="9db46-113">将此参数留空以设置视图的属性。</span><span class="sxs-lookup"><span data-stu-id="9db46-113">Leave this argument blank to set the property for the view.</span></span>  <br/> |
| <span data-ttu-id="9db46-114">_Property_</span><span class="sxs-lookup"><span data-stu-id="9db46-114">_Property_</span></span> <br/> |<span data-ttu-id="9db46-p103">请选择要设置的属性。有关可以使用此操作设置的属性的列表，请参阅本文的**说明**部分。</span><span class="sxs-lookup"><span data-stu-id="9db46-p103">Select the property that you want to set. See the **Remarks** section in this article for a list of the properties that can be set by using this action.  </span></span><br/> |
| <span data-ttu-id="9db46-117">_值_</span><span class="sxs-lookup"><span data-stu-id="9db46-117">_Value_</span></span> <br/> |<span data-ttu-id="9db46-p104">请键入要设置的属性值。对于值为“是”或“否”的属性，使用 **-1** 代表“是”，**0** 代表“否”。</span><span class="sxs-lookup"><span data-stu-id="9db46-p104">Type the value that the property is to be set to. For properties whose values are either Yes or No, use **-1** for Yes and **0** for No.  </span></span><br/> |
   
## <a name="remarks"></a><span data-ttu-id="9db46-120">注解</span><span class="sxs-lookup"><span data-stu-id="9db46-120">Remarks</span></span>

<span data-ttu-id="9db46-121">可以使用**SetProperty**操作设置控件的下列属性:</span><span class="sxs-lookup"><span data-stu-id="9db46-121">You can use the **SetProperty** action to set the following properties of a control:</span></span> 
  
- <span data-ttu-id="9db46-122">Caption</span><span class="sxs-lookup"><span data-stu-id="9db46-122">Caption</span></span>
    
- <span data-ttu-id="9db46-123">已启用</span><span class="sxs-lookup"><span data-stu-id="9db46-123">Enabled</span></span>
    
- <span data-ttu-id="9db46-124">ForeColor</span><span class="sxs-lookup"><span data-stu-id="9db46-124">ForeColor</span></span>
    
- <span data-ttu-id="9db46-125">值</span><span class="sxs-lookup"><span data-stu-id="9db46-125">Value</span></span>
    
- <span data-ttu-id="9db46-126">Visible</span><span class="sxs-lookup"><span data-stu-id="9db46-126">Visible</span></span>
    
<span data-ttu-id="9db46-127">如果为 \*\* *值* \*\* 参数输入的值无效，则不会发生错误，但 Access 可能会根据解释该参数的方式将属性更改为其他值。</span><span class="sxs-lookup"><span data-stu-id="9db46-127">If you enter an invalid value for the \*\* *Value* \*\* argument, no error occurs, but Access might change the property to a different value, depending on how it interprets the argument.</span></span> 
  

