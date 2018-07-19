---
title: 等于 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 70bc707a-3a61-4d75-816d-0defd0806319
description: 比较两个表达式相等。
ms.openlocfilehash: efdd06a1735190d63c13c4df8230e1d29d71c1dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773462"
---
# <a name="equals-access-custom-web-app"></a><span data-ttu-id="a8367-103">等于 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="a8367-103">Equals (Access custom web app)</span></span>

<span data-ttu-id="a8367-104">比较两个表达式相等。</span><span class="sxs-lookup"><span data-stu-id="a8367-104">Compares the equality of two expressions.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a8367-p101"> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="a8367-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="a8367-107">语法</span><span class="sxs-lookup"><span data-stu-id="a8367-107">Syntax</span></span>

`= (Equals)`

<span data-ttu-id="a8367-108">*表达式*  =  *表达式*</span><span class="sxs-lookup"><span data-stu-id="a8367-108">*expression*  =  *expression*</span></span> 
  
<span data-ttu-id="a8367-109">*表达式* 是任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="a8367-109">*expression*  Is any valid expression.</span></span> <span data-ttu-id="a8367-110">如果表达式不属于同一字段数据类型，必须隐式转换为的数据类型的另一个表达式的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a8367-110">If the expressions are not of the same data type, the data type for one expression must be implicitly convertible to the data type of the other.</span></span> <span data-ttu-id="a8367-111">转换取决于数据类型优先级的规则。</span><span class="sxs-lookup"><span data-stu-id="a8367-111">The conversion depends on the rules of data type precedence.</span></span> 
  
## <a name="return-type"></a><span data-ttu-id="a8367-112">返回类型</span><span class="sxs-lookup"><span data-stu-id="a8367-112">Return Type</span></span>

<span data-ttu-id="a8367-113">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="a8367-113">**Boolean**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a8367-114">说明</span><span class="sxs-lookup"><span data-stu-id="a8367-114">Remarks</span></span>

<span data-ttu-id="a8367-115">当您比较两个 NULL 表达式时，则结果为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="a8367-115">When you compare two NULL expressions, the result is TRUE.</span></span>
  
<span data-ttu-id="a8367-116">始终为非 NULL 值比较 NULL 导致 FALSE。</span><span class="sxs-lookup"><span data-stu-id="a8367-116">Comparing NULL to a non-NULL value always results in FALSE.</span></span>
  

