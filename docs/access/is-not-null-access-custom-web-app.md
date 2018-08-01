---
title: '[不] 是 NULL （访问自定义 web 应用程序）'
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b941a0c7-9753-4920-bb6d-cbba94ba9422
description: 确定指定的表达式是否为 NULL。
ms.openlocfilehash: fcbceb1e8edac65fe232ba9c2b12195b99db9545
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773452"
---
# <a name="is-not-null-access-custom-web-app"></a><span data-ttu-id="d382d-103">[不] 是 NULL （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="d382d-103">IS [NOT] NULL (Access custom web app)</span></span>

<span data-ttu-id="d382d-104">确定指定的表达式是否为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d382d-104">Determines whether a specified expression is NULL.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d382d-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="d382d-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d382d-107">语法</span><span class="sxs-lookup"><span data-stu-id="d382d-107">Syntax</span></span>

 <span data-ttu-id="d382d-108">*表达式***IS**[ ** ]**NULL**</span><span class="sxs-lookup"><span data-stu-id="d382d-108">*expression* **IS** [  *NOT*  ] **NULL**</span></span>
  
<span data-ttu-id="d382d-109">**IS [NOT] NULL**谓词包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="d382d-109">The **IS [NOT] NULL** predicate contains the following arguments.</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d382d-110">*expression*</span><span class="sxs-lookup"><span data-stu-id="d382d-110">*expression*</span></span>  <br/> |<span data-ttu-id="d382d-111">任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="d382d-111">Any valid expression.</span></span>  <br/> |
| <span data-ttu-id="d382d-112">*NOT*</span><span class="sxs-lookup"><span data-stu-id="d382d-112">*NOT*</span></span>  <br/> |<span data-ttu-id="d382d-113">指定布尔值的结果取反。</span><span class="sxs-lookup"><span data-stu-id="d382d-113">Specifies that the Boolean result be negated.</span></span> <span data-ttu-id="d382d-114">谓词取消其返回值，如果的值不是 NULL 值和 FALSE 如果值为 NULL，则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="d382d-114">The predicate reverses its return values, returning TRUE if the value is not NULL, and FALSE if the value is NULL.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d382d-115">说明</span><span class="sxs-lookup"><span data-stu-id="d382d-115">Remarks</span></span>

<span data-ttu-id="d382d-116">如果*表达式*的值为 NULL，则为 NULL，则返回 TRUE;否则，将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="d382d-116">If the value of  *expression*  is NULL, IS NULL returns TRUE; otherwise, it returns FALSE.</span></span> 
  
<span data-ttu-id="d382d-117">如果表达式的值为 NULL，则不是 NULL 返回 FALSE;否则，将返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="d382d-117">If the value of expression is NULL, IS NOT NULL returns FALSE; otherwise, it returns TRUE.</span></span>
  

