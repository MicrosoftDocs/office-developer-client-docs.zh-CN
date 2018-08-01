---
title: 子字符串函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae99a0fa-76c4-4c07-9ae9-a7abce23394f
description: 返回文本表达式的一部分。
ms.openlocfilehash: 49d9afefe4b25d91738e518e0ddb2b902067c038
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773621"
---
# <a name="substring-function-access-custom-web-app"></a><span data-ttu-id="5d7c0-103">子字符串函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="5d7c0-103">SubString Function (Access custom web app)</span></span>

<span data-ttu-id="5d7c0-104">返回文本表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-104">Returns part of a text expression.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5d7c0-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5d7c0-107">语法</span><span class="sxs-lookup"><span data-stu-id="5d7c0-107">Syntax</span></span>

 <span data-ttu-id="5d7c0-108">**子字符串**（*TextExpression*，*启动*，*长度*）</span><span class="sxs-lookup"><span data-stu-id="5d7c0-108">**SubString** (*TextExpression*, *Start*, *Length*)</span></span> 
  
<span data-ttu-id="5d7c0-109">**子字符串**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-109">The **SubString** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="5d7c0-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="5d7c0-110">**Argument name**</span></span>|<span data-ttu-id="5d7c0-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5d7c0-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="5d7c0-112">*TextExpression*</span><span class="sxs-lookup"><span data-stu-id="5d7c0-112">*TextExpression*</span></span>  <br/> |<span data-ttu-id="5d7c0-113">文本表达式。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-113">A text expression.</span></span>  <br/> |
| <span data-ttu-id="5d7c0-114">*Start*</span><span class="sxs-lookup"><span data-stu-id="5d7c0-114">*Start*</span></span>  <br/> |<span data-ttu-id="5d7c0-115">指定返回的字符位置开始一个整数表达式。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-115">An integer expression that specifies where the returned characters start.</span></span> <span data-ttu-id="5d7c0-116">小于 1 开始时，将会在表达式中指定的第一个字符开始返回的表达式。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-116">If start is less than 1, the returned expression will begin at the first character that is specified in expression.</span></span> <span data-ttu-id="5d7c0-117">在这种情况下，返回的字符数是开始 + 长度 1 的总和或 0 的最大值。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-117">In this case, the number of characters that are returned is the largest value of either the sum of start + length- 1 or 0.</span></span> <span data-ttu-id="5d7c0-118">如果 start 大于值表达式中的字符数，则返回零长度表达式。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-118">If start is greater than the number of characters in the value expression, a zero-length expression is returned.</span></span>  <br/> |
| <span data-ttu-id="5d7c0-119">*Length*</span><span class="sxs-lookup"><span data-stu-id="5d7c0-119">*Length*</span></span>  <br/> |<span data-ttu-id="5d7c0-120">将返回一个正整数表达式，指定表达式的字符数。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-120">A positive integer expression that specifies how many characters of the expression will be returned.</span></span> <span data-ttu-id="5d7c0-121">如果长度为负数，将生成一个错误和终止语句。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-121">If length is negative, an error is generated and the statement is terminated.</span></span> <span data-ttu-id="5d7c0-122">如果 start 和 length 的总和大于表达式中的字符数，则返回整个值表达式从开始的开始。</span><span class="sxs-lookup"><span data-stu-id="5d7c0-122">If the sum of start and length is greater than the number of characters in expression, the whole value expression beginning at start is returned.</span></span>  <br/> |
   

