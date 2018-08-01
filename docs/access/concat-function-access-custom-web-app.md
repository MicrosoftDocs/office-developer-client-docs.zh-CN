---
title: Concat 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 38ad6365-79df-4342-9b76-ca27b8ab8952
description: 返回 string 类型的值组合两个或多个字符串值的结果。
ms.openlocfilehash: fc0de43e5e42cc1c39ee89cf76058b8039daf279
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773417"
---
# <a name="concat-function-access-custom-web-app"></a><span data-ttu-id="17bf3-103">Concat 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="17bf3-103">Concat function (Access custom web app)</span></span>

<span data-ttu-id="17bf3-104">返回 string 类型的值组合两个或多个字符串值的结果。</span><span class="sxs-lookup"><span data-stu-id="17bf3-104">Returns a string that is the result of combining two or more string values.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="17bf3-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="17bf3-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="17bf3-107">语法</span><span class="sxs-lookup"><span data-stu-id="17bf3-107">Syntax</span></span>

<span data-ttu-id="17bf3-108">**Concat**(*Value1*， *Value2*，...[*ValueN*])</span><span class="sxs-lookup"><span data-stu-id="17bf3-108">**Concat** (*Value1*, *Value2*, …[*ValueN*])</span></span> 
  
<span data-ttu-id="17bf3-109">**Concat**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="17bf3-109">The **Concat** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="17bf3-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="17bf3-110">**Argument Name**</span></span>|<span data-ttu-id="17bf3-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="17bf3-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="17bf3-112">值</span><span class="sxs-lookup"><span data-stu-id="17bf3-112">Value</span></span>  <br/> |<span data-ttu-id="17bf3-113">要连接到其他值的字符串值。</span><span class="sxs-lookup"><span data-stu-id="17bf3-113">A string value to concatenate to the other values.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="17bf3-114">说明</span><span class="sxs-lookup"><span data-stu-id="17bf3-114">Remarks</span></span>

<span data-ttu-id="17bf3-115">**Concat**采用变量的字符串参数数目，并将它们连接到单个字符串。</span><span class="sxs-lookup"><span data-stu-id="17bf3-115">**Concat** takes a variable number of string arguments and concatenates them into a single string.</span></span> <span data-ttu-id="17bf3-116">至少两个字符串参数是必需的;否则，将引发错误。</span><span class="sxs-lookup"><span data-stu-id="17bf3-116">A minimum of two string arguments are required; otherwise, an error is raised.</span></span> 
  
<span data-ttu-id="17bf3-117">所有参数都隐式转换为 string 数据类型，然后连接。</span><span class="sxs-lookup"><span data-stu-id="17bf3-117">All arguments are implicitly converted to string data types and then concatenated.</span></span>
  
## <a name="example"></a><span data-ttu-id="17bf3-118">示例</span><span class="sxs-lookup"><span data-stu-id="17bf3-118">Example</span></span>

<span data-ttu-id="17bf3-119">以下表达式可显示联系人的完整名称其中表包含 FirstName、 MiddleInitial 和 LastName 字段。</span><span class="sxs-lookup"><span data-stu-id="17bf3-119">The following expression can be used to display the full name of a person where the table contains FirstName, MiddleInitial, and LastName fields.</span></span> <span data-ttu-id="17bf3-120">如果 MiddleInitial 字段为空，组合仅的 FirstName 和 LastName 字段以显示完整的名称。</span><span class="sxs-lookup"><span data-stu-id="17bf3-120">If the MiddleInitial field is blank, only the FirstName and LastName fields are combined to display the full name.</span></span>
  
```vb
IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))
```


