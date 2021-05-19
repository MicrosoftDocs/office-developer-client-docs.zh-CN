---
title: 'SubString Function (Access 自定义 Web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae99a0fa-76c4-4c07-9ae9-a7abce23394f
description: 返回文本表达式的一部分。
ms.openlocfilehash: af93620905af366f41bcc50ab6102114acd3db9f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433470"
---
# <a name="substring-function-access-custom-web-app"></a><span data-ttu-id="91f55-103">SubString Function (Access 自定义 Web app) </span><span class="sxs-lookup"><span data-stu-id="91f55-103">SubString Function (Access custom web app)</span></span>

<span data-ttu-id="91f55-104">返回文本表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="91f55-104">Returns part of a text expression.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="91f55-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="91f55-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="91f55-107">语法</span><span class="sxs-lookup"><span data-stu-id="91f55-107">Syntax</span></span>

 <span data-ttu-id="91f55-108">**SubString** (*TextExpression、Start、Length*)  </span><span class="sxs-lookup"><span data-stu-id="91f55-108">**SubString** (*TextExpression*, *Start*, *Length*)</span></span> 
  
<span data-ttu-id="91f55-109">**SubString** 函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="91f55-109">The **SubString** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="91f55-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="91f55-110">**Argument name**</span></span>|<span data-ttu-id="91f55-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="91f55-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="91f55-112">*TextExpression*</span><span class="sxs-lookup"><span data-stu-id="91f55-112">*TextExpression*</span></span>  <br/> |<span data-ttu-id="91f55-113">文本表达式。</span><span class="sxs-lookup"><span data-stu-id="91f55-113">A text expression.</span></span>  <br/> |
| <span data-ttu-id="91f55-114">*Start*</span><span class="sxs-lookup"><span data-stu-id="91f55-114">*Start*</span></span>  <br/> |<span data-ttu-id="91f55-115">一个整数表达式，指定返回的字符的起始位置。</span><span class="sxs-lookup"><span data-stu-id="91f55-115">An integer expression that specifies where the returned characters start.</span></span> <span data-ttu-id="91f55-116">如果 start 小于 1，则返回的表达式将从 expression 中指定的第一个字符开始。</span><span class="sxs-lookup"><span data-stu-id="91f55-116">If start is less than 1, the returned expression will begin at the first character that is specified in expression.</span></span> <span data-ttu-id="91f55-117">在这种情况下，返回的字符数是 start + length- 1 或 0 之和的最多值。</span><span class="sxs-lookup"><span data-stu-id="91f55-117">In this case, the number of characters that are returned is the largest value of either the sum of start + length- 1 or 0.</span></span> <span data-ttu-id="91f55-118">如果 start 大于值表达式中的字符数，则返回零长度表达式。</span><span class="sxs-lookup"><span data-stu-id="91f55-118">If start is greater than the number of characters in the value expression, a zero-length expression is returned.</span></span>  <br/> |
| <span data-ttu-id="91f55-119">*Length*</span><span class="sxs-lookup"><span data-stu-id="91f55-119">*Length*</span></span>  <br/> |<span data-ttu-id="91f55-120">一个正整数表达式，指定将返回的表达式字符数。</span><span class="sxs-lookup"><span data-stu-id="91f55-120">A positive integer expression that specifies how many characters of the expression will be returned.</span></span> <span data-ttu-id="91f55-121">如果 length 为负数，则生成错误并终止语句。</span><span class="sxs-lookup"><span data-stu-id="91f55-121">If length is negative, an error is generated and the statement is terminated.</span></span> <span data-ttu-id="91f55-122">如果 start 和 length 的和大于 expression 中的字符数，则返回从 start 开始的整个值表达式。</span><span class="sxs-lookup"><span data-stu-id="91f55-122">If the sum of start and length is greater than the number of characters in expression, the whole value expression beginning at start is returned.</span></span>  <br/> |
   

