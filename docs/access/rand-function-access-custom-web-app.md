---
title: Rand 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6390b325-025e-4546-bb19-1cd1c45ceb5a
description: 返回一个伪随机数字 0 与 1 之间。
ms.openlocfilehash: ed0f9991b2b1d9553d6d45524d6b1e4e5321ea7e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773587"
---
# <a name="rand-function-access-custom-web-app"></a><span data-ttu-id="06201-103">Rand 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="06201-103">Rand Function (Access custom web app)</span></span>

<span data-ttu-id="06201-104">返回一个伪随机数字 0 与 1 之间。</span><span class="sxs-lookup"><span data-stu-id="06201-104">Returns a pseudo-random number between 0 and 1.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="06201-p101">[!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="06201-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="06201-107">语法</span><span class="sxs-lookup"><span data-stu-id="06201-107">Syntax</span></span>

 <span data-ttu-id="06201-108">**Rand**（[*种子*]）</span><span class="sxs-lookup"><span data-stu-id="06201-108">**Rand** ( [  *Seed*  ])</span></span> 
  
<span data-ttu-id="06201-109">**Rand**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="06201-109">The **Rand** function contains the following argument.</span></span> 
  
|<span data-ttu-id="06201-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="06201-110">**Argument name**</span></span>|<span data-ttu-id="06201-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="06201-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="06201-112">*Seed*</span><span class="sxs-lookup"><span data-stu-id="06201-112">*Seed*</span></span>  <br/> |<span data-ttu-id="06201-113">提供的种子值整数表达式。</span><span class="sxs-lookup"><span data-stu-id="06201-113">An integer expression that gives the seed value.</span></span> <span data-ttu-id="06201-114">如果未指定*种子*，随机分配种子值。</span><span class="sxs-lookup"><span data-stu-id="06201-114">If  *Seed*  is not specified, a seed value is assigned at random.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="06201-115">备注</span><span class="sxs-lookup"><span data-stu-id="06201-115">Remarks</span></span>

<span data-ttu-id="06201-116">重复调用具有相同的种子的**Rand**函数返回相同的结果。</span><span class="sxs-lookup"><span data-stu-id="06201-116">Repetitive calls of the **Rand** function with the same seed return the same results.</span></span> 
  

