---
title: Concat 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 38ad6365-79df-4342-9b76-ca27b8ab8952
description: 返回一个字符串, 表示组合两个或更多字符串值的结果。
ms.openlocfilehash: b8f52c292e64939f9464bc666ecc4bc341580f94
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282290"
---
# <a name="concat-function-access-custom-web-app"></a><span data-ttu-id="21999-103">Concat 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="21999-103">Concat function (Access custom web app)</span></span>

<span data-ttu-id="21999-104">返回一个字符串, 表示组合两个或更多字符串值的结果。</span><span class="sxs-lookup"><span data-stu-id="21999-104">Returns a string that is the result of combining two or more string values.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="21999-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="21999-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="21999-107">语法</span><span class="sxs-lookup"><span data-stu-id="21999-107">Syntax</span></span>

<span data-ttu-id="21999-108">**Concat**(*Value1*、 *Value2*、.。。[*ValueN*])</span><span class="sxs-lookup"><span data-stu-id="21999-108">**Concat** (*Value1*, *Value2*, …[*ValueN*])</span></span> 
  
<span data-ttu-id="21999-109">**Concat**函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="21999-109">The **Concat** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="21999-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="21999-110">**Argument Name**</span></span>|<span data-ttu-id="21999-111">**Description**</span><span class="sxs-lookup"><span data-stu-id="21999-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="21999-112">值</span><span class="sxs-lookup"><span data-stu-id="21999-112">Value</span></span>  <br/> |<span data-ttu-id="21999-113">要连接到其他值的字符串值。</span><span class="sxs-lookup"><span data-stu-id="21999-113">A string value to concatenate to the other values.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="21999-114">注解</span><span class="sxs-lookup"><span data-stu-id="21999-114">Remarks</span></span>

<span data-ttu-id="21999-115">**Concat**采用可变数目的字符串参数, 并将它们连接为单个字符串。</span><span class="sxs-lookup"><span data-stu-id="21999-115">**Concat** takes a variable number of string arguments and concatenates them into a single string.</span></span> <span data-ttu-id="21999-116">至少需要两个字符串参数。否则, 将引发错误。</span><span class="sxs-lookup"><span data-stu-id="21999-116">A minimum of two string arguments are required; otherwise, an error is raised.</span></span> 
  
<span data-ttu-id="21999-117">所有参数都隐式转换为 string 数据类型, 然后进行连接。</span><span class="sxs-lookup"><span data-stu-id="21999-117">All arguments are implicitly converted to string data types and then concatenated.</span></span>
  
## <a name="example"></a><span data-ttu-id="21999-118">示例</span><span class="sxs-lookup"><span data-stu-id="21999-118">Example</span></span>

<span data-ttu-id="21999-119">下面的表达式可用于显示表中包含 FirstName、MiddleInitial 和 LastName 字段的人员的完整名称。</span><span class="sxs-lookup"><span data-stu-id="21999-119">The following expression can be used to display the full name of a person where the table contains FirstName, MiddleInitial, and LastName fields.</span></span> <span data-ttu-id="21999-120">如果 "MiddleInitial" 字段为空, 则只会组合 "名字" 和 "姓氏" 字段以显示完整名称。</span><span class="sxs-lookup"><span data-stu-id="21999-120">If the MiddleInitial field is blank, only the FirstName and LastName fields are combined to display the full name.</span></span>
  
```vb
IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))
```


