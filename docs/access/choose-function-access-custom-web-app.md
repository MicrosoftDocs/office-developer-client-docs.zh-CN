---
title: 'Choose function (Access custom web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 70c1ac24-a28f-4401-91d3-61129578bebd
description: 从值列表返回指定索引中的项。
ms.openlocfilehash: e44655b9c2f4055f1f3dc57befa8adc6884c43b6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414114"
---
# <a name="choose-function-access-custom-web-app"></a><span data-ttu-id="bd773-103">Choose function (Access custom web app) </span><span class="sxs-lookup"><span data-stu-id="bd773-103">Choose function (Access custom web app)</span></span>

<span data-ttu-id="bd773-104">从值列表返回指定索引中的项。</span><span class="sxs-lookup"><span data-stu-id="bd773-104">Returns the item at the specified index from a list of values.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bd773-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="bd773-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="bd773-107">语法</span><span class="sxs-lookup"><span data-stu-id="bd773-107">Syntax</span></span>

<span data-ttu-id="bd773-108">**Choose** (*IndexNumber*， *Value*， [*Value_n*]) </span><span class="sxs-lookup"><span data-stu-id="bd773-108">**Choose** (*IndexNumber*, *Value*, [*Value_n*])</span></span> 
  
<span data-ttu-id="bd773-109">**Choose** 函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="bd773-109">The **Choose** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="bd773-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="bd773-110">**Argument name**</span></span>|<span data-ttu-id="bd773-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="bd773-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="bd773-112">*IndexNumber*</span><span class="sxs-lookup"><span data-stu-id="bd773-112">*IndexNumber*</span></span>  <br/> |<span data-ttu-id="bd773-113">一个整数表达式，表示从 1 到以下项目列表中的索引。</span><span class="sxs-lookup"><span data-stu-id="bd773-113">An integer expression that represents a 1-based index into the list of the items following it.</span></span>  <br/> |
| <span data-ttu-id="bd773-114">*值*</span><span class="sxs-lookup"><span data-stu-id="bd773-114">*Value*</span></span>  <br/> |<span data-ttu-id="bd773-115">任何值的列表数据类型。</span><span class="sxs-lookup"><span data-stu-id="bd773-115">List of values of any data type.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bd773-116">备注</span><span class="sxs-lookup"><span data-stu-id="bd773-116">Remarks</span></span>

<span data-ttu-id="bd773-117">如果提供的  *IndexNumber*  不是整数，则值将隐式转换为整数。</span><span class="sxs-lookup"><span data-stu-id="bd773-117">If the provided  *IndexNumber*  is not an integer, then the value is implicitly converted to an integer.</span></span> 
  
<span data-ttu-id="bd773-118">如果索引值超出值数组的界限， **则 Choose** 将返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="bd773-118">If the index value exceeds the bounds of the array of values, **Choose** returns NULL.</span></span> 
  

