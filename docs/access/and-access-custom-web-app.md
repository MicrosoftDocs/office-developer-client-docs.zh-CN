---
title: 和 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 44c11a0b-abca-4ea8-8770-f5c1375d8d76
description: 将两个表达式组合在一起, 并在两个表达式均为 true 时返回 true。
ms.openlocfilehash: 247b15b9f8039d06d08c0ce9b2fcb443e3212350
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426280"
---
# <a name="and-access-custom-web-app"></a><span data-ttu-id="984a7-103">和 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="984a7-103">AND (Access custom web app)</span></span>

<span data-ttu-id="984a7-104">将两个表达式组合在一起, 并在两个表达式均为 true 时返回 true。</span><span class="sxs-lookup"><span data-stu-id="984a7-104">Combines two Boolean expressions and returns TRUE when both expressions are TRUE.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="984a7-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="984a7-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="984a7-107">语法</span><span class="sxs-lookup"><span data-stu-id="984a7-107">Syntax</span></span>

 <span data-ttu-id="984a7-108">*boolean_expression***,***boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="984a7-108">*boolean_expression* **AND** *boolean_expression*</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="984a7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="984a7-109">Return value</span></span>

<span data-ttu-id="984a7-110">如果两个表达式均为 true, 则返回 true。</span><span class="sxs-lookup"><span data-stu-id="984a7-110">Returns TRUE when both expressions are TRUE.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="984a7-111">说明</span><span class="sxs-lookup"><span data-stu-id="984a7-111">Remarks</span></span>

<span data-ttu-id="984a7-112">当在一个语句中使用多个逻辑运算符时, 先计算 AND 运算符。</span><span class="sxs-lookup"><span data-stu-id="984a7-112">When more than one logical operator is used in a statement, the AND operators are evaluated first.</span></span> <span data-ttu-id="984a7-113">您可以使用括号更改求值的顺序。</span><span class="sxs-lookup"><span data-stu-id="984a7-113">You can change the order of evaluation by using parentheses.</span></span>
  

