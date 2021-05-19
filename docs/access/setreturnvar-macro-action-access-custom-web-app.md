---
title: 'SetReturnVar 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 57965c84-7a52-4d7c-9c7f-be3d4570576d
description: SetReturnVar 操作创建一个返回变量，并设置为特定值。
ms.openlocfilehash: 29445f5021bed99fe45cee1d34457f1f91ca417d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409592"
---
# <a name="setreturnvar-macro-action-access-custom-web-app"></a><span data-ttu-id="281ec-103">SetReturnVar 宏操作 (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="281ec-103">SetReturnVar Macro action (Access custom web app)</span></span>

<span data-ttu-id="281ec-104">**SetReturnVar** 操作创建一个返回变量，并设置为特定值。</span><span class="sxs-lookup"><span data-stu-id="281ec-104">The **SetReturnVar** action creates a return variable and sets it to a specific value.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="281ec-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="281ec-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="281ec-107">**SetReturnVar** 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="281ec-107">The **SetReturnVar** action is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="281ec-108">设置</span><span class="sxs-lookup"><span data-stu-id="281ec-108">Setting</span></span>

<span data-ttu-id="281ec-109">**SetReturnVar** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="281ec-109">The **SetReturnVar** action has the following arguments.</span></span> 
  
|<span data-ttu-id="281ec-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="281ec-110">**Argument name**</span></span>|<span data-ttu-id="281ec-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="281ec-111">**Required**</span></span>|<span data-ttu-id="281ec-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="281ec-112">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="281ec-113">_名称_</span><span class="sxs-lookup"><span data-stu-id="281ec-113">_Name_</span></span> <br/> |<span data-ttu-id="281ec-114">是</span><span class="sxs-lookup"><span data-stu-id="281ec-114">Yes</span></span>  <br/> |<span data-ttu-id="281ec-115">一个用于指定变量名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="281ec-115">A string that specifies the name of the variable.</span></span>  <br/> |
| <span data-ttu-id="281ec-116">_Expression_</span><span class="sxs-lookup"><span data-stu-id="281ec-116">_Expression_</span></span> <br/> |<span data-ttu-id="281ec-117">是</span><span class="sxs-lookup"><span data-stu-id="281ec-117">Yes</span></span>  <br/> |<span data-ttu-id="281ec-118">一个用于设置该临时变量的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="281ec-118">An expression that will be used to set the value for this temporary variable.</span></span> <span data-ttu-id="281ec-119">该表达式不能以等号 (=) 开头。</span><span class="sxs-lookup"><span data-stu-id="281ec-119">Do not precede the expression with the equal sign (=).</span></span> <span data-ttu-id="281ec-120">单击 **“生成”** 按钮可使用 **“表达式生成器”** 设置该参数。</span><span class="sxs-lookup"><span data-stu-id="281ec-120">You can click the **Build** button to use the **Expression Builder** to set this argument.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="281ec-121">说明</span><span class="sxs-lookup"><span data-stu-id="281ec-121">Remarks</span></span>

<span data-ttu-id="281ec-122">**SetReturnVar** 操作用于创建 **ReturnVar，** 该变量可用于使用 **RunDataMacro** 操作调用数据宏的宏。</span><span class="sxs-lookup"><span data-stu-id="281ec-122">The **SetReturnVar** action is used to create a **ReturnVar**, which is variable that can be used by macros that call a data macro by using the **RunDataMacro** action.</span></span> 
  
<span data-ttu-id="281ec-123">通过 **SetReturnVar** 操作创建 **ReturnVar** 后，调用宏可以在表达式中使用它。</span><span class="sxs-lookup"><span data-stu-id="281ec-123">After a **ReturnVar** is created by the **SetReturnVar** action, the calling macro can use it in an expression.</span></span> <span data-ttu-id="281ec-124">例如，如果创建了一个名为 **UpdateSuccess** 的 **ReturnVar，** 则可以通过使用以下语法来使用 变量：</span><span class="sxs-lookup"><span data-stu-id="281ec-124">For example, if you created a **ReturnVar** named **UpdateSuccess**, you could use the variable by using the following syntax:</span></span>
  
`=[ReturnVars]![UpdateSuccess]`

<span data-ttu-id="281ec-125">**SetReturnVar** 操作只能在命名的数据宏中使用。</span><span class="sxs-lookup"><span data-stu-id="281ec-125">The **SetReturnVar** action can be used only in named data macros.</span></span> <span data-ttu-id="281ec-126">在附加到数据宏事件的数据宏中不可用。</span><span class="sxs-lookup"><span data-stu-id="281ec-126">It is not available in data macros that are attached to a data macro event.</span></span> 
  

