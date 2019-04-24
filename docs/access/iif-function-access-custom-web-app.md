---
title: IIf 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 58a24f46-c61d-432a-a957-d831e960795d
description: 检查是否满足某个条件, 如果另一个条件为 FALSE, 则返回一个值。
ms.openlocfilehash: 274a923a96b58421f365b03c566a3a1c16b7c48c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301860"
---
# <a name="iif-function-access-custom-web-app"></a><span data-ttu-id="da434-103">IIf 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="da434-103">IIf function (Access custom web app)</span></span>

<span data-ttu-id="da434-104">检查是否满足某个条件, 如果另一个条件为 FALSE, 则返回一个值。</span><span class="sxs-lookup"><span data-stu-id="da434-104">Checks whether a condition is met, and returns one value if TRUE of another on if it is FALSE.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="da434-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="da434-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="da434-107">语法</span><span class="sxs-lookup"><span data-stu-id="da434-107">Syntax</span></span>

<span data-ttu-id="da434-108">**IIf**(*Condition*、 *TrueValue*、 *FalseValue*)</span><span class="sxs-lookup"><span data-stu-id="da434-108">**IIf** (*Condition*, *TrueValue*, *FalseValue*)</span></span> 
  
<span data-ttu-id="da434-109">**IIf**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="da434-109">The **IIf** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="da434-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="da434-110">**Argument name**</span></span>|<span data-ttu-id="da434-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="da434-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="da434-112">*条件*</span><span class="sxs-lookup"><span data-stu-id="da434-112">*Condition*</span></span>  <br/> |<span data-ttu-id="da434-113">要计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="da434-113">The expression that you want to evaluate.</span></span>  <br/> |
| <span data-ttu-id="da434-114">*TrueValue*</span><span class="sxs-lookup"><span data-stu-id="da434-114">*TrueValue*</span></span>  <br/> |<span data-ttu-id="da434-115">如果*条件*为 True, 则返回值或表达式。</span><span class="sxs-lookup"><span data-stu-id="da434-115">Value or expression returned if  *Condition*  is True.</span></span>  <br/> |
| <span data-ttu-id="da434-116">*FalseValue*</span><span class="sxs-lookup"><span data-stu-id="da434-116">*FalseValue*</span></span>  <br/> |<span data-ttu-id="da434-117">如果*Condition*为 False, 则返回值或表达式。</span><span class="sxs-lookup"><span data-stu-id="da434-117">Value or expression returned if  *Condition*  is False.</span></span>  <br/> |
   
## <a name="example"></a><span data-ttu-id="da434-118">示例</span><span class="sxs-lookup"><span data-stu-id="da434-118">Example</span></span>

<span data-ttu-id="da434-119">下面的表达式可用于显示表中包含 FirstName、MiddleInitial 和 LastName 字段的人员的完整名称。</span><span class="sxs-lookup"><span data-stu-id="da434-119">The following expression can be used to display the full name of a person where the table contains FirstName, MiddleInitial, and LastName fields.</span></span> <span data-ttu-id="da434-120">如果 "MiddleInitial" 字段为空, 则只会组合 "名字" 和 "姓氏" 字段以显示完整名称。</span><span class="sxs-lookup"><span data-stu-id="da434-120">If the MiddleInitial field is blank, only the FirstName and LastName fields are combined to display the full name.</span></span>
  
`IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))`


