---
title: IIf 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 58a24f46-c61d-432a-a957-d831e960795d
description: 检查它是否条件得到满足，并在如果如果为 true，则另一个返回一个值为 FALSE。
ms.openlocfilehash: 26240735341a316a3aed08a12c42e8b6e7af805f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773425"
---
# <a name="iif-function-access-custom-web-app"></a><span data-ttu-id="08189-103">IIf 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="08189-103">IIf function (Access custom web app)</span></span>

<span data-ttu-id="08189-104">检查它是否条件得到满足，并在如果如果为 true，则另一个返回一个值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="08189-104">Checks whether a condition is met, and returns one value if TRUE of another on if it is FALSE.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="08189-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="08189-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="08189-107">语法</span><span class="sxs-lookup"><span data-stu-id="08189-107">Syntax</span></span>

<span data-ttu-id="08189-108">**IIf**(*条件*， *TrueValue*， *FalseValue*)</span><span class="sxs-lookup"><span data-stu-id="08189-108">**IIf** (*Condition*, *TrueValue*, *FalseValue*)</span></span> 
  
<span data-ttu-id="08189-109">**IIf**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="08189-109">The **IIf** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="08189-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="08189-110">**Argument name**</span></span>|<span data-ttu-id="08189-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="08189-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="08189-112">*条件*</span><span class="sxs-lookup"><span data-stu-id="08189-112">*Condition*</span></span>  <br/> |<span data-ttu-id="08189-113">要计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="08189-113">The expression that you want to evaluate.</span></span>  <br/> |
| <span data-ttu-id="08189-114">*TrueValue*</span><span class="sxs-lookup"><span data-stu-id="08189-114">*TrueValue*</span></span>  <br/> |<span data-ttu-id="08189-115">值或表达式返回如果*条件*为 True。</span><span class="sxs-lookup"><span data-stu-id="08189-115">Value or expression returned if  *Condition*  is True.</span></span>  <br/> |
| <span data-ttu-id="08189-116">*FalseValue*</span><span class="sxs-lookup"><span data-stu-id="08189-116">*FalseValue*</span></span>  <br/> |<span data-ttu-id="08189-117">值或表达式返回如果*条件*为 False。</span><span class="sxs-lookup"><span data-stu-id="08189-117">Value or expression returned if  *Condition*  is False.</span></span>  <br/> |
   
## <a name="example"></a><span data-ttu-id="08189-118">示例</span><span class="sxs-lookup"><span data-stu-id="08189-118">Example</span></span>

<span data-ttu-id="08189-119">以下表达式可显示联系人的完整名称其中表包含 FirstName、 MiddleInitial 和 LastName 字段。</span><span class="sxs-lookup"><span data-stu-id="08189-119">The following expression can be used to display the full name of a person where the table contains FirstName, MiddleInitial, and LastName fields.</span></span> <span data-ttu-id="08189-120">如果 MiddleInitial 字段为空，组合仅的 FirstName 和 LastName 字段以显示完整的名称。</span><span class="sxs-lookup"><span data-stu-id="08189-120">If the MiddleInitial field is blank, only the FirstName and LastName fields are combined to display the full name.</span></span>
  
`IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))`


