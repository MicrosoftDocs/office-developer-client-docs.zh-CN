---
title: 'Access 自定义 web (IIf 函数) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 58a24f46-c61d-432a-a957-d831e960795d
description: 检查条件是否满足，如果为 TRUE，则返回另一个值（如果为 FALSE）。
ms.openlocfilehash: 274a923a96b58421f365b03c566a3a1c16b7c48c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439077"
---
# <a name="iif-function-access-custom-web-app"></a><span data-ttu-id="484f4-103">Access 自定义 web (IIf 函数) </span><span class="sxs-lookup"><span data-stu-id="484f4-103">IIf function (Access custom web app)</span></span>

<span data-ttu-id="484f4-104">检查条件是否满足，如果为 TRUE，则返回另一个值（如果为 FALSE）。</span><span class="sxs-lookup"><span data-stu-id="484f4-104">Checks whether a condition is met, and returns one value if TRUE of another on if it is FALSE.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="484f4-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="484f4-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="484f4-107">语法</span><span class="sxs-lookup"><span data-stu-id="484f4-107">Syntax</span></span>

<span data-ttu-id="484f4-108">**IIf** (*条件*、 *TrueValue*、 *FalseValue*) </span><span class="sxs-lookup"><span data-stu-id="484f4-108">**IIf** (*Condition*, *TrueValue*, *FalseValue*)</span></span> 
  
<span data-ttu-id="484f4-109">**IIf** 函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="484f4-109">The **IIf** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="484f4-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="484f4-110">**Argument name**</span></span>|<span data-ttu-id="484f4-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="484f4-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="484f4-112">*条件*</span><span class="sxs-lookup"><span data-stu-id="484f4-112">*Condition*</span></span>  <br/> |<span data-ttu-id="484f4-113">要计算表达式。</span><span class="sxs-lookup"><span data-stu-id="484f4-113">The expression that you want to evaluate.</span></span>  <br/> |
| <span data-ttu-id="484f4-114">*TrueValue*</span><span class="sxs-lookup"><span data-stu-id="484f4-114">*TrueValue*</span></span>  <br/> |<span data-ttu-id="484f4-115">如果 Condition 为 True，则  *返回值*  或表达式。</span><span class="sxs-lookup"><span data-stu-id="484f4-115">Value or expression returned if  *Condition*  is True.</span></span>  <br/> |
| <span data-ttu-id="484f4-116">*FalseValue*</span><span class="sxs-lookup"><span data-stu-id="484f4-116">*FalseValue*</span></span>  <br/> |<span data-ttu-id="484f4-117">如果 Condition 为 False，则  *返回*  值或表达式。</span><span class="sxs-lookup"><span data-stu-id="484f4-117">Value or expression returned if  *Condition*  is False.</span></span>  <br/> |
   
## <a name="example"></a><span data-ttu-id="484f4-118">示例</span><span class="sxs-lookup"><span data-stu-id="484f4-118">Example</span></span>

<span data-ttu-id="484f4-119">下面的表达式可用于显示表中包含 FirstName、MiddleInitial 和 LastName 字段的人的全名。</span><span class="sxs-lookup"><span data-stu-id="484f4-119">The following expression can be used to display the full name of a person where the table contains FirstName, MiddleInitial, and LastName fields.</span></span> <span data-ttu-id="484f4-120">如果 MiddleInitial 字段为空，则只合并 FirstName 和 LastName 字段以显示全名。</span><span class="sxs-lookup"><span data-stu-id="484f4-120">If the MiddleInitial field is blank, only the FirstName and LastName fields are combined to display the full name.</span></span>
  
`IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))`


