---
title: Equals (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 70bc707a-3a61-4d75-816d-0defd0806319
description: 比较两个表达式的相等性。
ms.openlocfilehash: 8c551e3dbc057433b49bc2558e08feba5ee3d04f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408927"
---
# <a name="equals-access-custom-web-app"></a><span data-ttu-id="0dfdc-103">Equals (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="0dfdc-103">Equals (Access custom web app)</span></span>

<span data-ttu-id="0dfdc-104">比较两个表达式的相等性。</span><span class="sxs-lookup"><span data-stu-id="0dfdc-104">Compares the equality of two expressions.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0dfdc-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="0dfdc-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0dfdc-107">语法</span><span class="sxs-lookup"><span data-stu-id="0dfdc-107">Syntax</span></span>

`= (Equals)`

<span data-ttu-id="0dfdc-108">*表达式*  =  *表达式*</span><span class="sxs-lookup"><span data-stu-id="0dfdc-108">*expression*  =  *expression*</span></span> 
  
<span data-ttu-id="0dfdc-109">“*expression*”表示任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="0dfdc-109">*expression*  Is any valid expression.</span></span> <span data-ttu-id="0dfdc-110">如果表达式不是相同的数据类型, 则一个表达式的数据类型必须可以隐式转换为另一个表达式的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0dfdc-110">If the expressions are not of the same data type, the data type for one expression must be implicitly convertible to the data type of the other.</span></span> <span data-ttu-id="0dfdc-111">转换取决于数据类型优先级的规则。</span><span class="sxs-lookup"><span data-stu-id="0dfdc-111">The conversion depends on the rules of data type precedence.</span></span> 
  
## <a name="return-type"></a><span data-ttu-id="0dfdc-112">返回类型</span><span class="sxs-lookup"><span data-stu-id="0dfdc-112">Return Type</span></span>

<span data-ttu-id="0dfdc-113">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="0dfdc-113">**Boolean**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0dfdc-114">说明</span><span class="sxs-lookup"><span data-stu-id="0dfdc-114">Remarks</span></span>

<span data-ttu-id="0dfdc-115">比较两个 NULL 表达式时, 结果为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="0dfdc-115">When you compare two NULL expressions, the result is TRUE.</span></span>
  
<span data-ttu-id="0dfdc-116">将 NULL 与非 NULL 值进行比较始终会导致 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0dfdc-116">Comparing NULL to a non-NULL value always results in FALSE.</span></span>
  

