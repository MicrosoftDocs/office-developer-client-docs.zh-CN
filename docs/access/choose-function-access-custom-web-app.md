---
title: 选择函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 70c1ac24-a28f-4401-91d3-61129578bebd
description: 返回的值列表中指定索引处的项。
ms.openlocfilehash: a6db959945bfcfc15993d3979cb9b2b3da0da904
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773443"
---
# <a name="choose-function-access-custom-web-app"></a><span data-ttu-id="90348-103">选择函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="90348-103">Choose function (Access custom web app)</span></span>

<span data-ttu-id="90348-104">返回的值列表中指定索引处的项。</span><span class="sxs-lookup"><span data-stu-id="90348-104">Returns the item at the specified index from a list of values.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="90348-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="90348-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="90348-107">语法</span><span class="sxs-lookup"><span data-stu-id="90348-107">Syntax</span></span>

<span data-ttu-id="90348-108">**选择**(*IndexNumber*，*值*，[*Value_n*])</span><span class="sxs-lookup"><span data-stu-id="90348-108">**Choose** (*IndexNumber*, *Value*, [*Value_n*])</span></span> 
  
<span data-ttu-id="90348-109">**选择**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="90348-109">The **Choose** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="90348-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="90348-110">**Argument name**</span></span>|<span data-ttu-id="90348-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="90348-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="90348-112">*IndexNumber*</span><span class="sxs-lookup"><span data-stu-id="90348-112">*IndexNumber*</span></span>  <br/> |<span data-ttu-id="90348-113">一个表示 1 开始的索引到列表中的后面它的各项的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="90348-113">An integer expression that represents a 1-based index into the list of the items following it.</span></span>  <br/> |
| <span data-ttu-id="90348-114">*值*</span><span class="sxs-lookup"><span data-stu-id="90348-114">*Value*</span></span>  <br/> |<span data-ttu-id="90348-115">任何数据类型的值的列表。</span><span class="sxs-lookup"><span data-stu-id="90348-115">List of values of any data type.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="90348-116">说明</span><span class="sxs-lookup"><span data-stu-id="90348-116">Remarks</span></span>

<span data-ttu-id="90348-117">如果提供的*IndexNumber*不是整数，则值为整数隐式转换。</span><span class="sxs-lookup"><span data-stu-id="90348-117">If the provided  *IndexNumber*  is not an integer, then the value is implicitly converted to an integer.</span></span> 
  
<span data-ttu-id="90348-118">如果索引值超出值的数组的界限，则**Choose**将返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="90348-118">If the index value exceeds the bounds of the array of values, **Choose** returns NULL.</span></span> 
  

