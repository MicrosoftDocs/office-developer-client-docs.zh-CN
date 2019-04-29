---
title: Log 函数 (Access 自定义 web 应用程序)
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
# <a name="log-function-access-custom-web-app"></a><span data-ttu-id="2f246-103">Log 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="2f246-103">Log Function (Access custom web app)</span></span>

<span data-ttu-id="2f246-104">返回指定表达式的自然对数或给定底数的对数。</span><span class="sxs-lookup"><span data-stu-id="2f246-104">Returns the natural logarithm, or the logarithm of the given base, of the specified expression.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2f246-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="2f246-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2f246-107">语法</span><span class="sxs-lookup"><span data-stu-id="2f246-107">Syntax</span></span>

 <span data-ttu-id="2f246-108">**日志**(*NumericExpression* , [ *Base* ])</span><span class="sxs-lookup"><span data-stu-id="2f246-108">**Log** (*NumericExpression*  , [  *Base*  ])</span></span> 
  
<span data-ttu-id="2f246-109">**Log**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="2f246-109">The **Log** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="2f246-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="2f246-110">**Argument name**</span></span>|<span data-ttu-id="2f246-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="2f246-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="2f246-112">*NumericExpression*</span><span class="sxs-lookup"><span data-stu-id="2f246-112">*NumericExpression*</span></span>  <br/> |<span data-ttu-id="2f246-113">要对其进行对数的正数。</span><span class="sxs-lookup"><span data-stu-id="2f246-113">The positive number for which you want the logarithm.</span></span>  <br/> |
| <span data-ttu-id="2f246-114">*Base*</span><span class="sxs-lookup"><span data-stu-id="2f246-114">*Base*</span></span>  <br/> |<span data-ttu-id="2f246-115">对数的底数。</span><span class="sxs-lookup"><span data-stu-id="2f246-115">The base of the logarithm.</span></span> <span data-ttu-id="2f246-116">如果省略, 则**Log**函数返回自然对数。</span><span class="sxs-lookup"><span data-stu-id="2f246-116">If omitted, the **Log** function returns the natural logarithm.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2f246-117">说明</span><span class="sxs-lookup"><span data-stu-id="2f246-117">Remarks</span></span>

<span data-ttu-id="2f246-118">函数**Log10**是类似的, 但总是返回常用对数, 即底数为10的对数。</span><span class="sxs-lookup"><span data-stu-id="2f246-118">The function **Log10** is similar, but always returns the common logarithm, meaning the logarithm for the base 10.</span></span> 
  
<span data-ttu-id="2f246-119">自然对数是底数 e 的对数, 其中 e 是一个 irrational 常量, 约等于2.718281828。</span><span class="sxs-lookup"><span data-stu-id="2f246-119">The natural logarithm is the logarithm to the base e, where e is an irrational constant approximately equal to 2.718281828.</span></span>
  

