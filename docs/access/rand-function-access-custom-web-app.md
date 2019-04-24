---
title: Rand 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6390b325-025e-4546-bb19-1cd1c45ceb5a
description: 返回介于0和1之间的伪随机数字。
ms.openlocfilehash: 02d914de9d74083a6ebf76f6d0e556fe51954a24
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307992"
---
# <a name="rand-function-access-custom-web-app"></a><span data-ttu-id="477ad-103">Rand 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="477ad-103">Rand Function (Access custom web app)</span></span>

<span data-ttu-id="477ad-104">返回介于0和1之间的伪随机数字。</span><span class="sxs-lookup"><span data-stu-id="477ad-104">Returns a pseudo-random number between 0 and 1.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="477ad-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="477ad-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="477ad-107">语法</span><span class="sxs-lookup"><span data-stu-id="477ad-107">Syntax</span></span>

 <span data-ttu-id="477ad-108">**Rand**([ *Seed* ])</span><span class="sxs-lookup"><span data-stu-id="477ad-108">**Rand** ( [  *Seed*  ])</span></span> 
  
<span data-ttu-id="477ad-109">**Rand**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="477ad-109">The **Rand** function contains the following argument.</span></span> 
  
|<span data-ttu-id="477ad-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="477ad-110">**Argument name**</span></span>|<span data-ttu-id="477ad-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="477ad-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="477ad-112">*Seed*</span><span class="sxs-lookup"><span data-stu-id="477ad-112">*Seed*</span></span>  <br/> |<span data-ttu-id="477ad-113">提供种子值的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="477ad-113">An integer expression that gives the seed value.</span></span> <span data-ttu-id="477ad-114">如果未指定*种子*, 则会随机分配种子值。</span><span class="sxs-lookup"><span data-stu-id="477ad-114">If  *Seed*  is not specified, a seed value is assigned at random.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="477ad-115">注解</span><span class="sxs-lookup"><span data-stu-id="477ad-115">Remarks</span></span>

<span data-ttu-id="477ad-116">对具有相同种子的**Rand**函数的重复调用将返回相同的结果。</span><span class="sxs-lookup"><span data-stu-id="477ad-116">Repetitive calls of the **Rand** function with the same seed return the same results.</span></span> 
  

