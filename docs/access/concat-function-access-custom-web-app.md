---
title: 'Concat 函数 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 38ad6365-79df-4342-9b76-ca27b8ab8952
description: 返回一个字符串，该字符串是组合两个或多个字符串值的结果。
ms.openlocfilehash: b8f52c292e64939f9464bc666ecc4bc341580f94
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423270"
---
# <a name="concat-function-access-custom-web-app"></a><span data-ttu-id="5308f-103">Concat 函数 (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="5308f-103">Concat function (Access custom web app)</span></span>

<span data-ttu-id="5308f-104">返回一个字符串，该字符串是组合两个或多个字符串值的结果。</span><span class="sxs-lookup"><span data-stu-id="5308f-104">Returns a string that is the result of combining two or more string values.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5308f-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="5308f-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5308f-107">语法</span><span class="sxs-lookup"><span data-stu-id="5308f-107">Syntax</span></span>

<span data-ttu-id="5308f-108">**Concat** (*Value1，* *Value2*， ...[*ValueN*]) </span><span class="sxs-lookup"><span data-stu-id="5308f-108">**Concat** (*Value1*, *Value2*, …[*ValueN*])</span></span> 
  
<span data-ttu-id="5308f-109">**Concat** 函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="5308f-109">The **Concat** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="5308f-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="5308f-110">**Argument Name**</span></span>|<span data-ttu-id="5308f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5308f-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5308f-112">值</span><span class="sxs-lookup"><span data-stu-id="5308f-112">Value</span></span>  <br/> |<span data-ttu-id="5308f-113">要与其他值连接的字符串值。</span><span class="sxs-lookup"><span data-stu-id="5308f-113">A string value to concatenate to the other values.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5308f-114">备注</span><span class="sxs-lookup"><span data-stu-id="5308f-114">Remarks</span></span>

<span data-ttu-id="5308f-115">**Concat** 采用可变数量的字符串参数，将它们连接为一个字符串。</span><span class="sxs-lookup"><span data-stu-id="5308f-115">**Concat** takes a variable number of string arguments and concatenates them into a single string.</span></span> <span data-ttu-id="5308f-116">至少需要两个字符串参数;否则，将引发错误。</span><span class="sxs-lookup"><span data-stu-id="5308f-116">A minimum of two string arguments are required; otherwise, an error is raised.</span></span> 
  
<span data-ttu-id="5308f-117">所有参数都隐式转换为字符串数据类型，然后连接。</span><span class="sxs-lookup"><span data-stu-id="5308f-117">All arguments are implicitly converted to string data types and then concatenated.</span></span>
  
## <a name="example"></a><span data-ttu-id="5308f-118">示例</span><span class="sxs-lookup"><span data-stu-id="5308f-118">Example</span></span>

<span data-ttu-id="5308f-119">下面的表达式可用于显示表中包含 FirstName、MiddleInitial 和 LastName 字段的人的全名。</span><span class="sxs-lookup"><span data-stu-id="5308f-119">The following expression can be used to display the full name of a person where the table contains FirstName, MiddleInitial, and LastName fields.</span></span> <span data-ttu-id="5308f-120">如果 MiddleInitial 字段为空，则只合并 FirstName 和 LastName 字段以显示全名。</span><span class="sxs-lookup"><span data-stu-id="5308f-120">If the MiddleInitial field is blank, only the FirstName and LastName fields are combined to display the full name.</span></span>
  
```vb
IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))
```


