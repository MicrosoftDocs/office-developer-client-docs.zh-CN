---
title: SetProperty 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1e97dd95-23f6-4f49-b3b9-2c7261b3a70d
description: 您可以使用 SetProperty 操作设置视图上的控件的属性。
ms.openlocfilehash: 89ac2b10715d707d3b6ee09ee8ab915384c5acf5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773598"
---
# <a name="setproperty-macro-action-access-custom-web-app"></a><span data-ttu-id="8bbcc-103">SetProperty 宏操作 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="8bbcc-103">SetProperty Macro Action (Access custom web app)</span></span>

<span data-ttu-id="8bbcc-104">您可以使用**SetProperty**操作设置视图上的控件的属性。</span><span class="sxs-lookup"><span data-stu-id="8bbcc-104">You can use the **SetProperty** action to set a property for a control on a view.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8bbcc-p101">[!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="8bbcc-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="8bbcc-107">设置</span><span class="sxs-lookup"><span data-stu-id="8bbcc-107">Setting</span></span>

<span data-ttu-id="8bbcc-108">**SetProperty**操作具有以下表中列出的参数。</span><span class="sxs-lookup"><span data-stu-id="8bbcc-108">The **SetProperty** action has the arguments listed in the following table.</span></span> 
  
|<span data-ttu-id="8bbcc-109">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="8bbcc-109">**Action argument**</span></span>|<span data-ttu-id="8bbcc-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="8bbcc-110">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="8bbcc-111">_控件名称_</span><span class="sxs-lookup"><span data-stu-id="8bbcc-111">_Control Name_</span></span> <br/> |<span data-ttu-id="8bbcc-112">键入您要为其设置属性值的控件的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="8bbcc-112">Type the name of the field or control for which you want to set the property value.</span></span> <span data-ttu-id="8bbcc-113">将此参数留空将视图属性设置。</span><span class="sxs-lookup"><span data-stu-id="8bbcc-113">Leave this argument blank to set the property for the view.</span></span>  <br/> |
| <span data-ttu-id="8bbcc-114">_属性_</span><span class="sxs-lookup"><span data-stu-id="8bbcc-114">_Property_</span></span> <br/> |<span data-ttu-id="8bbcc-115">选择您想要设置的属性。</span><span class="sxs-lookup"><span data-stu-id="8bbcc-115">Select the property that you want to set.</span></span> <span data-ttu-id="8bbcc-116">请参阅**备注**部分中可以使用此操作设置的属性列表。</span><span class="sxs-lookup"><span data-stu-id="8bbcc-116">See the **Remarks** section in this article for a list of the properties that can be set by using this action.</span></span>  <br/> |
| <span data-ttu-id="8bbcc-117">_值_</span><span class="sxs-lookup"><span data-stu-id="8bbcc-117">_Value_</span></span> <br/> |<span data-ttu-id="8bbcc-118">键入的值的属性设置为。</span><span class="sxs-lookup"><span data-stu-id="8bbcc-118">Type the value that the property is to be set to.</span></span> <span data-ttu-id="8bbcc-119">属性，其值为是或是否，使用 **-1** ， **0**表示否。</span><span class="sxs-lookup"><span data-stu-id="8bbcc-119">For properties whose values are either Yes or No, use **-1** for Yes and **0** for No.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8bbcc-120">备注</span><span class="sxs-lookup"><span data-stu-id="8bbcc-120">Remarks</span></span>

<span data-ttu-id="8bbcc-121">您可以使用**SetProperty**操作设置控件的下列属性：</span><span class="sxs-lookup"><span data-stu-id="8bbcc-121">You can use the **SetProperty** action to set the following properties of a control:</span></span> 
  
- <span data-ttu-id="8bbcc-122">Caption</span><span class="sxs-lookup"><span data-stu-id="8bbcc-122">Caption</span></span>
    
- <span data-ttu-id="8bbcc-123">已启用</span><span class="sxs-lookup"><span data-stu-id="8bbcc-123">Enabled</span></span>
    
- <span data-ttu-id="8bbcc-124">前景色</span><span class="sxs-lookup"><span data-stu-id="8bbcc-124">ForeColor</span></span>
    
- <span data-ttu-id="8bbcc-125">值</span><span class="sxs-lookup"><span data-stu-id="8bbcc-125">Value</span></span>
    
- <span data-ttu-id="8bbcc-126">Visible</span><span class="sxs-lookup"><span data-stu-id="8bbcc-126">Visible</span></span>
    
<span data-ttu-id="8bbcc-127">如果为 ** *值* ** 参数输入的值无效，则不会发生错误，但 Access 可能会根据解释该参数的方式将属性更改为其他值。</span><span class="sxs-lookup"><span data-stu-id="8bbcc-127">If you enter an invalid value for the ** *Value* ** argument, no error occurs, but Access might change the property to a different value, depending on how it interprets the argument.</span></span> 
  

