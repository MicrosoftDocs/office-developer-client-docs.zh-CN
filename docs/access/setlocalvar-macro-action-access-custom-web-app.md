---
title: 'SetLocalVar 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 12444313-1cfa-49ff-89da-3030fe75c13e
description: SetLocalVar 操作可创建一个临时变量并将其设置为特定值。
ms.openlocfilehash: 2493bc5c908c551e171a8fa7d9eaeea699a04f72
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428114"
---
# <a name="setlocalvar-macro-action-access-custom-web-app"></a><span data-ttu-id="0a84d-103">SetLocalVar 宏操作 (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="0a84d-103">SetLocalVar Macro Action (Access custom web app)</span></span>

<span data-ttu-id="0a84d-104">**SetLocalVar** 操作可创建一个临时变量并将其设置为特定值。</span><span class="sxs-lookup"><span data-stu-id="0a84d-104">The **SetLocalVar** action creates a temporary variable and set it to a specific value.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0a84d-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="0a84d-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0a84d-107">**SetLocalVar** 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="0a84d-107">The **SetLocalVar** action is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="0a84d-108">设置</span><span class="sxs-lookup"><span data-stu-id="0a84d-108">Setting</span></span>

<span data-ttu-id="0a84d-109">**SetLocalVar** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="0a84d-109">The **SetLocalVar** action has the following arguments.</span></span> 
  
|<span data-ttu-id="0a84d-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="0a84d-110">**Argument name**</span></span>|<span data-ttu-id="0a84d-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="0a84d-111">**Required**</span></span>|<span data-ttu-id="0a84d-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="0a84d-112">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a84d-113">**名称**</span><span class="sxs-lookup"><span data-stu-id="0a84d-113">**Name**</span></span> <br/> |<span data-ttu-id="0a84d-114">是</span><span class="sxs-lookup"><span data-stu-id="0a84d-114">Yes</span></span>  <br/> |<span data-ttu-id="0a84d-115">一个用于指定变量名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="0a84d-115">A string that specifies the name of the variable.</span></span>  <br/> |
|<span data-ttu-id="0a84d-116">**Expression**</span><span class="sxs-lookup"><span data-stu-id="0a84d-116">**Expression**</span></span> <br/> |<span data-ttu-id="0a84d-117">是</span><span class="sxs-lookup"><span data-stu-id="0a84d-117">Yes</span></span>  <br/> |<span data-ttu-id="0a84d-118">一个用于设置该临时变量的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="0a84d-118">An expression that will be used to set the value for this temporary variable.</span></span> <span data-ttu-id="0a84d-119">该表达式不能以等号 (=) 开头。</span><span class="sxs-lookup"><span data-stu-id="0a84d-119">Do not precede the expression with the equal sign (=).</span></span> <span data-ttu-id="0a84d-120">单击 **“生成”** 按钮可使用 **“表达式生成器”** 设置该参数。</span><span class="sxs-lookup"><span data-stu-id="0a84d-120">You can click the **Build** button to use the **Expression Builder** to set this argument.</span></span>  <br/> |
   

