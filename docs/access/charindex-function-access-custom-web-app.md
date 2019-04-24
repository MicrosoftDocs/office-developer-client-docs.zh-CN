---
title: CharIndex 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 340ed9a8-6f82-4aa8-a951-2c453b3d1ac4
description: 在文本表达式中搜索其他文本表达式, 如果找到, 则返回其起始位置。
ms.openlocfilehash: dc6906f70bc5bb17e12855d69946281909962988
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282605"
---
# <a name="charindex-function-access-custom-web-app"></a><span data-ttu-id="48c15-103">CharIndex 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="48c15-103">CharIndex function (Access custom web app)</span></span>

<span data-ttu-id="48c15-104">在文本表达式中搜索其他文本表达式, 如果找到, 则返回其起始位置。</span><span class="sxs-lookup"><span data-stu-id="48c15-104">Searches a text expression for another text expression and returns its starting position if found.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="48c15-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="48c15-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="48c15-107">语法</span><span class="sxs-lookup"><span data-stu-id="48c15-107">Syntax</span></span>

<span data-ttu-id="48c15-108">**CharIndex**(*TextExpression*、 *WithinText*、[*Start*])</span><span class="sxs-lookup"><span data-stu-id="48c15-108">**CharIndex** (*TextExpression*, *WithinText*, [*Start*])</span></span> 
  
|<span data-ttu-id="48c15-109">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="48c15-109">**Argument Name**</span></span>|<span data-ttu-id="48c15-110">**必需**</span><span class="sxs-lookup"><span data-stu-id="48c15-110">**Required**</span></span>|<span data-ttu-id="48c15-111">**描述**</span><span class="sxs-lookup"><span data-stu-id="48c15-111">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="48c15-112">*TextExpression*</span><span class="sxs-lookup"><span data-stu-id="48c15-112">*TextExpression*</span></span>  <br/> |<span data-ttu-id="48c15-113">是</span><span class="sxs-lookup"><span data-stu-id="48c15-113">Yes</span></span>  <br/> |<span data-ttu-id="48c15-114">包含要查找的文本的文本表达式。</span><span class="sxs-lookup"><span data-stu-id="48c15-114">A text expression that contains the text to be found.</span></span>  <br/> |
| <span data-ttu-id="48c15-115">*WithinText*</span><span class="sxs-lookup"><span data-stu-id="48c15-115">*WithinText*</span></span>  <br/> |<span data-ttu-id="48c15-116">是</span><span class="sxs-lookup"><span data-stu-id="48c15-116">Yes</span></span>  <br/> |<span data-ttu-id="48c15-117">要搜索的文本表达式。</span><span class="sxs-lookup"><span data-stu-id="48c15-117">The text expression to be searched.</span></span>  <br/> |
| <span data-ttu-id="48c15-118">*Start*</span><span class="sxs-lookup"><span data-stu-id="48c15-118">*Start*</span></span>  <br/> |<span data-ttu-id="48c15-119">否</span><span class="sxs-lookup"><span data-stu-id="48c15-119">No</span></span>  <br/> |<span data-ttu-id="48c15-120">一个整数, 指定*WithinText*中要开始搜索的位置。</span><span class="sxs-lookup"><span data-stu-id="48c15-120">An integer that specifies the location in  *WithinText*  to begin the search.</span></span> <span data-ttu-id="48c15-121">如果未指定*Start* , 则为负数, 或者为 0, 则搜索将从*WithinText*的开头开始。</span><span class="sxs-lookup"><span data-stu-id="48c15-121">If  *Start*  is not specified, is a negative number, or is 0, the search starts at the beginning of  *WithinText*  .</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="48c15-122">注解</span><span class="sxs-lookup"><span data-stu-id="48c15-122">Remarks</span></span>

<span data-ttu-id="48c15-123">如果*TextExpression*或*WithinText*为 null, 则*CharIndex*将返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="48c15-123">If either  *TextExpression*  or  *WithinText*  is NULL,  *CharIndex*  returns NULL.</span></span> 
  
<span data-ttu-id="48c15-124">如果在*WithinText*中找不到*TextExpression* , 则*CharIndex*将返回0。</span><span class="sxs-lookup"><span data-stu-id="48c15-124">If  *TextExpression*  is not found within  *WithinText*,  *CharIndex*  returns 0.</span></span> 
  
<span data-ttu-id="48c15-125">返回的起始位置是从1开始的, 而不是从0开始的。</span><span class="sxs-lookup"><span data-stu-id="48c15-125">The starting position returned is 1-based, not 0-based.</span></span>
  

