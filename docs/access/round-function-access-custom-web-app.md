---
title: Round 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4af7fbe2-ee34-4a52-b55e-ce3983313b5e
description: 返回一个四舍五入或截断到指定长度或精度的数值。
ms.openlocfilehash: 0afab8c3434aef58c4bb25aee22eefd95732797b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413743"
---
# <a name="round-function-access-custom-web-app"></a><span data-ttu-id="e06d1-103">Round 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="e06d1-103">Round Function (Access custom web app)</span></span>

<span data-ttu-id="e06d1-104">返回一个四舍五入或截断到指定长度或精度的数值。</span><span class="sxs-lookup"><span data-stu-id="e06d1-104">Returns a numeric value, either rounded or truncated, to the specified length or precision.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e06d1-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="e06d1-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e06d1-107">语法</span><span class="sxs-lookup"><span data-stu-id="e06d1-107">Syntax</span></span>

 <span data-ttu-id="e06d1-108">**四舍五入**(*Number*, *Precision* , [ *TruncateInsteadOfRound* ])</span><span class="sxs-lookup"><span data-stu-id="e06d1-108">**Round** (*Number*, *Precision*  , [  *TruncateInsteadOfRound*  ])</span></span> 
  
<span data-ttu-id="e06d1-109">**Round**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="e06d1-109">The **Round** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="e06d1-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="e06d1-110">**Argument name**</span></span>|<span data-ttu-id="e06d1-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e06d1-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e06d1-112">*Number*</span><span class="sxs-lookup"><span data-stu-id="e06d1-112">*Number*</span></span>  <br/> |<span data-ttu-id="e06d1-113">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="e06d1-113">A numeric expression.</span></span>  <br/> |
| <span data-ttu-id="e06d1-114">*精密*</span><span class="sxs-lookup"><span data-stu-id="e06d1-114">*Precision*</span></span>  <br/> |<span data-ttu-id="e06d1-115">将*数字*舍入到的精度。</span><span class="sxs-lookup"><span data-stu-id="e06d1-115">The precision to which  *Number*  is to be rounded.</span></span>  <span data-ttu-id="e06d1-116">*精度*必须为数值表达式。</span><span class="sxs-lookup"><span data-stu-id="e06d1-116">*Precision*  must be a numeric expression.</span></span> <span data-ttu-id="e06d1-117">如果*精度*为正数, 则将*数字*四舍五入为由 length 指定的小数位数。</span><span class="sxs-lookup"><span data-stu-id="e06d1-117">When  *Precision*  is a positive number,  *Number*  is rounded to the number of decimal positions specified by length.</span></span> <span data-ttu-id="e06d1-118">当*精度*为负数时,*数字*按长度指定, 在小数点的左侧进行四舍五入。</span><span class="sxs-lookup"><span data-stu-id="e06d1-118">When  *Precision*  is a negative number,  *Number*  is rounded on the left side of the decimal point, as specified by length.</span></span>  <br/> |
| <span data-ttu-id="e06d1-119">*TruncateInsteadOfRound*</span><span class="sxs-lookup"><span data-stu-id="e06d1-119">*TruncateInsteadOfRound*</span></span>  <br/> |<span data-ttu-id="e06d1-120">要执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="e06d1-120">The type of operation to perform.</span></span> <span data-ttu-id="e06d1-121">省略或设置为0时, 将四舍五入*数字*。</span><span class="sxs-lookup"><span data-stu-id="e06d1-121">When omitted or set to 0,  *Number*  is rounded.</span></span> <span data-ttu-id="e06d1-122">如果指定非0值, 则将截断*Number* 。</span><span class="sxs-lookup"><span data-stu-id="e06d1-122">When a value other than 0 is specified,  *Number*  is truncated.</span></span> <span data-ttu-id="e06d1-123">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="e06d1-123">The default value is 0.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e06d1-124">说明</span><span class="sxs-lookup"><span data-stu-id="e06d1-124">Remarks</span></span>

 <span data-ttu-id="e06d1-125">**Round**始终返回一个值。</span><span class="sxs-lookup"><span data-stu-id="e06d1-125">**Round** always returns a value.</span></span> <span data-ttu-id="e06d1-126">如果 length 为负值且大于小数点前的位数, 则**四舍五入**返回0。</span><span class="sxs-lookup"><span data-stu-id="e06d1-126">If length is negative and larger than the number of digits before the decimal point, **Round** returns 0.</span></span> 
  

