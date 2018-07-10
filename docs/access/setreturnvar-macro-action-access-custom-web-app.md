---
title: SetReturnVar 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 57965c84-7a52-4d7c-9c7f-be3d4570576d
description: SetReturnVar 操作创建返回变量，并将其设置为特定值。
ms.openlocfilehash: d0638c8f1e3b184a7c685ad8649c8923bdfd8f50
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773627"
---
# <a name="setreturnvar-macro-action-access-custom-web-app"></a><span data-ttu-id="1ec58-103">SetReturnVar 宏操作 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="1ec58-103">SetReturnVar Macro action (Access custom web app)</span></span>

<span data-ttu-id="1ec58-104">**SetReturnVar**操作创建返回变量，并将其设置为特定值。</span><span class="sxs-lookup"><span data-stu-id="1ec58-104">The **SetReturnVar** action creates a return variable and sets it to a specific value.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1ec58-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="1ec58-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1ec58-107">**SetReturnVar**操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="1ec58-107">The **SetReturnVar** action is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="1ec58-108">设置</span><span class="sxs-lookup"><span data-stu-id="1ec58-108">Setting</span></span>

<span data-ttu-id="1ec58-109">**SetReturnVar**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="1ec58-109">The **SetReturnVar** action has the following arguments.</span></span> 
  
|<span data-ttu-id="1ec58-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="1ec58-110">**Argument name**</span></span>|<span data-ttu-id="1ec58-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="1ec58-111">**Required**</span></span>|<span data-ttu-id="1ec58-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="1ec58-112">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="1ec58-113">_名称_</span><span class="sxs-lookup"><span data-stu-id="1ec58-113">_Name_</span></span> <br/> |<span data-ttu-id="1ec58-114">是</span><span class="sxs-lookup"><span data-stu-id="1ec58-114">Yes</span></span>  <br/> |<span data-ttu-id="1ec58-115">一个用于指定变量名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="1ec58-115">A string that specifies the name of the variable.</span></span>  <br/> |
| <span data-ttu-id="1ec58-116">_Expression_</span><span class="sxs-lookup"><span data-stu-id="1ec58-116">_Expression_</span></span> <br/> |<span data-ttu-id="1ec58-117">是</span><span class="sxs-lookup"><span data-stu-id="1ec58-117">Yes</span></span>  <br/> |<span data-ttu-id="1ec58-118">一个表达式，用于设置为临时变量的值。</span><span class="sxs-lookup"><span data-stu-id="1ec58-118">An expression that will be used to set the value for this temporary variable.</span></span> <span data-ttu-id="1ec58-119">不在表达式前面放等号 （=）。</span><span class="sxs-lookup"><span data-stu-id="1ec58-119">Do not precede the expression with the equal sign (=).</span></span> <span data-ttu-id="1ec58-120">您可以单击**生成**按钮以使用**表达式生成器**设置此参数。</span><span class="sxs-lookup"><span data-stu-id="1ec58-120">You can click the **Build** button to use the **Expression Builder** to set this argument.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1ec58-121">备注</span><span class="sxs-lookup"><span data-stu-id="1ec58-121">Remarks</span></span>

<span data-ttu-id="1ec58-122">**SetReturnVar**操作用于创建**ReturnVar**，这是可供使用**RunDataMacro**操作调用的数据宏的宏的变量。</span><span class="sxs-lookup"><span data-stu-id="1ec58-122">The **SetReturnVar** action is used to create a **ReturnVar**, which is variable that can be used by macros that call a data macro by using the **RunDataMacro** action.</span></span> 
  
<span data-ttu-id="1ec58-123">**ReturnVar**创建**SetReturnVar**操作后，调用宏可以使用它在表达式中。</span><span class="sxs-lookup"><span data-stu-id="1ec58-123">After a **ReturnVar** is created by the **SetReturnVar** action, the calling macro can use it in an expression.</span></span> <span data-ttu-id="1ec58-124">例如，如果您创建名为**UpdateSuccess** **ReturnVar** ，您可以使用该变量使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1ec58-124">For example, if you created a **ReturnVar** named **UpdateSuccess**, you could use the variable by using the following syntax:</span></span>
  
`=[ReturnVars]![UpdateSuccess]`

<span data-ttu-id="1ec58-125">**SetReturnVar**操作可仅在命名的数据宏。</span><span class="sxs-lookup"><span data-stu-id="1ec58-125">The **SetReturnVar** action can be used only in named data macros.</span></span> <span data-ttu-id="1ec58-126">不适用于数据宏附加到的数据宏事件。</span><span class="sxs-lookup"><span data-stu-id="1ec58-126">It is not available in data macros that are attached to a data macro event.</span></span> 
  

