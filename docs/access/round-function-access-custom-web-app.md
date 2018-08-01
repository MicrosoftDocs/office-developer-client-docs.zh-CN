---
title: Round 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4af7fbe2-ee34-4a52-b55e-ce3983313b5e
description: 返回一个数字值，舍入或截断为指定的长度或精度。
ms.openlocfilehash: 5a3df4a4ddd7aace5edf886db5988704e5dd6af3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773604"
---
# <a name="round-function-access-custom-web-app"></a><span data-ttu-id="0339c-103">Round 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="0339c-103">Round Function (Access custom web app)</span></span>

<span data-ttu-id="0339c-104">返回一个数字值，舍入或截断为指定的长度或精度。</span><span class="sxs-lookup"><span data-stu-id="0339c-104">Returns a numeric value, either rounded or truncated, to the specified length or precision.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0339c-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="0339c-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0339c-107">语法</span><span class="sxs-lookup"><span data-stu-id="0339c-107">Syntax</span></span>

 <span data-ttu-id="0339c-108">**圆**（*号码*、*精度*[ *TruncateInsteadOfRound* ]）</span><span class="sxs-lookup"><span data-stu-id="0339c-108">**Round** (*Number*, *Precision*  , [  *TruncateInsteadOfRound*  ])</span></span> 
  
<span data-ttu-id="0339c-109">**Round**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="0339c-109">The **Round** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="0339c-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="0339c-110">**Argument name**</span></span>|<span data-ttu-id="0339c-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="0339c-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="0339c-112">*Number*</span><span class="sxs-lookup"><span data-stu-id="0339c-112">*Number*</span></span>  <br/> |<span data-ttu-id="0339c-113">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="0339c-113">A numeric expression.</span></span>  <br/> |
| <span data-ttu-id="0339c-114">*精度*</span><span class="sxs-lookup"><span data-stu-id="0339c-114">*Precision*</span></span>  <br/> |<span data-ttu-id="0339c-115">精度*数*是要舍入。</span><span class="sxs-lookup"><span data-stu-id="0339c-115">The precision to which  *Number*  is to be rounded.</span></span>  <span data-ttu-id="0339c-116">*精度*必须是数值表达式。</span><span class="sxs-lookup"><span data-stu-id="0339c-116">*Precision*  must be a numeric expression.</span></span> <span data-ttu-id="0339c-117">当*精度*为正数时，则会将*Number*舍入到指定长度的位数。</span><span class="sxs-lookup"><span data-stu-id="0339c-117">When  *Precision*  is a positive number,  *Number*  is rounded to the number of decimal positions specified by length.</span></span> <span data-ttu-id="0339c-118">*精度*时为负数，则会将*Number*舍入指定长度的小数点左侧。</span><span class="sxs-lookup"><span data-stu-id="0339c-118">When  *Precision*  is a negative number,  *Number*  is rounded on the left side of the decimal point, as specified by length.</span></span>  <br/> |
| <span data-ttu-id="0339c-119">*TruncateInsteadOfRound*</span><span class="sxs-lookup"><span data-stu-id="0339c-119">*TruncateInsteadOfRound*</span></span>  <br/> |<span data-ttu-id="0339c-120">要执行的操作类型。</span><span class="sxs-lookup"><span data-stu-id="0339c-120">The type of operation to perform.</span></span> <span data-ttu-id="0339c-121">当省略或设置为 0， *Number*舍入。</span><span class="sxs-lookup"><span data-stu-id="0339c-121">When omitted or set to 0,  *Number*  is rounded.</span></span> <span data-ttu-id="0339c-122">指定一个其他大于 0 的值时，*数字*将被截断。</span><span class="sxs-lookup"><span data-stu-id="0339c-122">When a value other than 0 is specified,  *Number*  is truncated.</span></span> <span data-ttu-id="0339c-123">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="0339c-123">The default value is 0.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0339c-124">说明</span><span class="sxs-lookup"><span data-stu-id="0339c-124">Remarks</span></span>

 <span data-ttu-id="0339c-125">**Round**始终返回一个值。</span><span class="sxs-lookup"><span data-stu-id="0339c-125">**Round** always returns a value.</span></span> <span data-ttu-id="0339c-126">如果长度为负数和大于之前小数点的位数， **Round**返回 0。</span><span class="sxs-lookup"><span data-stu-id="0339c-126">If length is negative and larger than the number of digits before the decimal point, **Round** returns 0.</span></span> 
  

