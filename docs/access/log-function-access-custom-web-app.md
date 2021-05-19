---
title: 'Log Function (Access 自定义 Web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a897e812-08dc-49c9-954b-e8908a0daab3
description: 返回指定表达式的自然对数或给定底数的对数。
ms.openlocfilehash: e2cfd1cf4ad3c1bf44778737faa0f697333f5234
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419294"
---
# <a name="log-function-access-custom-web-app"></a><span data-ttu-id="b3364-103">Log Function (Access 自定义 Web app) </span><span class="sxs-lookup"><span data-stu-id="b3364-103">Log Function (Access custom web app)</span></span>

<span data-ttu-id="b3364-104">返回指定表达式的自然对数或给定底数的对数。</span><span class="sxs-lookup"><span data-stu-id="b3364-104">Returns the natural logarithm, or the logarithm of the given base, of the specified expression.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b3364-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3364-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b3364-107">语法</span><span class="sxs-lookup"><span data-stu-id="b3364-107">Syntax</span></span>

 <span data-ttu-id="b3364-108">**Log** (*NumericExpression*  ， [  *Base*  ]) </span><span class="sxs-lookup"><span data-stu-id="b3364-108">**Log** (*NumericExpression*  , [  *Base*  ])</span></span> 
  
<span data-ttu-id="b3364-109">**Log** 函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="b3364-109">The **Log** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="b3364-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="b3364-110">**Argument name**</span></span>|<span data-ttu-id="b3364-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="b3364-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="b3364-112">*NumericExpression*</span><span class="sxs-lookup"><span data-stu-id="b3364-112">*NumericExpression*</span></span>  <br/> |<span data-ttu-id="b3364-113">要用于对数的正数。</span><span class="sxs-lookup"><span data-stu-id="b3364-113">The positive number for which you want the logarithm.</span></span>  <br/> |
| <span data-ttu-id="b3364-114">*Base*</span><span class="sxs-lookup"><span data-stu-id="b3364-114">*Base*</span></span>  <br/> |<span data-ttu-id="b3364-115">对数的底数。</span><span class="sxs-lookup"><span data-stu-id="b3364-115">The base of the logarithm.</span></span> <span data-ttu-id="b3364-116">如果省略 **，Log** 函数将返回自然对数。</span><span class="sxs-lookup"><span data-stu-id="b3364-116">If omitted, the **Log** function returns the natural logarithm.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b3364-117">备注</span><span class="sxs-lookup"><span data-stu-id="b3364-117">Remarks</span></span>

<span data-ttu-id="b3364-118">函数 **Log10** 相似，但始终返回常见的对数，即基数为 10 的对数。</span><span class="sxs-lookup"><span data-stu-id="b3364-118">The function **Log10** is similar, but always returns the common logarithm, meaning the logarithm for the base 10.</span></span> 
  
<span data-ttu-id="b3364-119">自然对数是 e 底数的对数，其中 e 是一个约等于 2.718281828 的常数。</span><span class="sxs-lookup"><span data-stu-id="b3364-119">The natural logarithm is the logarithm to the base e, where e is an irrational constant approximately equal to 2.718281828.</span></span>
  

