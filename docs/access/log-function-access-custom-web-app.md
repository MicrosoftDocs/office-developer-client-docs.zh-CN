---
title: Log 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a897e812-08dc-49c9-954b-e8908a0daab3
description: 返回自然对数或指定表达式的给定基础的对数。
ms.openlocfilehash: 5004b2b32e89a9d68364d271e8b94d72b012a62c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773423"
---
# <a name="log-function-access-custom-web-app"></a><span data-ttu-id="1fb6d-103">Log 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="1fb6d-103">Log Function (Access custom web app)</span></span>

<span data-ttu-id="1fb6d-104">返回自然对数或指定表达式的给定基础的对数。</span><span class="sxs-lookup"><span data-stu-id="1fb6d-104">Returns the natural logarithm, or the logarithm of the given base, of the specified expression.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1fb6d-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="1fb6d-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1fb6d-107">语法</span><span class="sxs-lookup"><span data-stu-id="1fb6d-107">Syntax</span></span>

 <span data-ttu-id="1fb6d-108">**日志**(*NumericExpression* ，[*基本*])</span><span class="sxs-lookup"><span data-stu-id="1fb6d-108">**Log** (*NumericExpression*  , [  *Base*  ])</span></span> 
  
<span data-ttu-id="1fb6d-109">**Log**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="1fb6d-109">The **Log** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="1fb6d-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="1fb6d-110">**Argument name**</span></span>|<span data-ttu-id="1fb6d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="1fb6d-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="1fb6d-112">*NumericExpression*</span><span class="sxs-lookup"><span data-stu-id="1fb6d-112">*NumericExpression*</span></span>  <br/> |<span data-ttu-id="1fb6d-113">要计算其对数的正数。</span><span class="sxs-lookup"><span data-stu-id="1fb6d-113">The positive number for which you want the logarithm.</span></span>  <br/> |
| <span data-ttu-id="1fb6d-114">*Base*</span><span class="sxs-lookup"><span data-stu-id="1fb6d-114">*Base*</span></span>  <br/> |<span data-ttu-id="1fb6d-115">对数的基。</span><span class="sxs-lookup"><span data-stu-id="1fb6d-115">The base of the logarithm.</span></span> <span data-ttu-id="1fb6d-116">如果省略，则**Log**函数返回的自然对数。</span><span class="sxs-lookup"><span data-stu-id="1fb6d-116">If omitted, the **Log** function returns the natural logarithm.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1fb6d-117">说明</span><span class="sxs-lookup"><span data-stu-id="1fb6d-117">Remarks</span></span>

<span data-ttu-id="1fb6d-118">**Log10**函数类似，但始终返回常用对数，意味着以 10 为底的对数。</span><span class="sxs-lookup"><span data-stu-id="1fb6d-118">The function **Log10** is similar, but always returns the common logarithm, meaning the logarithm for the base 10.</span></span> 
  
<span data-ttu-id="1fb6d-119">自然对数是 e，为底的对数其中 e 是约等于 2.718281828 irrational 常量。</span><span class="sxs-lookup"><span data-stu-id="1fb6d-119">The natural logarithm is the logarithm to the base e, where e is an irrational constant approximately equal to 2.718281828.</span></span>
  

