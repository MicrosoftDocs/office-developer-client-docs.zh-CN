---
title: CharIndex 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 340ed9a8-6f82-4aa8-a951-2c453b3d1ac4
description: 搜索其他文本表达式，如果其起始位置的返回的文本表达式找到。
ms.openlocfilehash: 86a46f57c64028530217326127eece887127c4c3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773460"
---
# <a name="charindex-function-access-custom-web-app"></a><span data-ttu-id="3bf7f-103">CharIndex 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="3bf7f-103">CharIndex function (Access custom web app)</span></span>

<span data-ttu-id="3bf7f-104">搜索其他文本表达式，如果其起始位置的返回的文本表达式找到。</span><span class="sxs-lookup"><span data-stu-id="3bf7f-104">Searches a text expression for another text expression and returns its starting position if found.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3bf7f-p101">[!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="3bf7f-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="3bf7f-107">语法</span><span class="sxs-lookup"><span data-stu-id="3bf7f-107">Syntax</span></span>

<span data-ttu-id="3bf7f-108">**CharIndex**(*TextExpression*， *WithinText*，[*启动*])</span><span class="sxs-lookup"><span data-stu-id="3bf7f-108">**CharIndex** (*TextExpression*, *WithinText*, [*Start*])</span></span> 
  
|<span data-ttu-id="3bf7f-109">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="3bf7f-109">**Argument Name**</span></span>|<span data-ttu-id="3bf7f-110">**必需**</span><span class="sxs-lookup"><span data-stu-id="3bf7f-110">**Required**</span></span>|<span data-ttu-id="3bf7f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="3bf7f-111">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="3bf7f-112">*TextExpression*</span><span class="sxs-lookup"><span data-stu-id="3bf7f-112">*TextExpression*</span></span>  <br/> |<span data-ttu-id="3bf7f-113">可访问</span><span class="sxs-lookup"><span data-stu-id="3bf7f-113">Yes</span></span>  <br/> |<span data-ttu-id="3bf7f-114">一个包含要找的文本的文本表达式。</span><span class="sxs-lookup"><span data-stu-id="3bf7f-114">A text expression that contains the text to be found.</span></span>  <br/> |
| <span data-ttu-id="3bf7f-115">*WithinText*</span><span class="sxs-lookup"><span data-stu-id="3bf7f-115">*WithinText*</span></span>  <br/> |<span data-ttu-id="3bf7f-116">可访问</span><span class="sxs-lookup"><span data-stu-id="3bf7f-116">Yes</span></span>  <br/> |<span data-ttu-id="3bf7f-117">要搜索的文本表达式。</span><span class="sxs-lookup"><span data-stu-id="3bf7f-117">The text expression to be searched.</span></span>  <br/> |
| <span data-ttu-id="3bf7f-118">*Start*</span><span class="sxs-lookup"><span data-stu-id="3bf7f-118">*Start*</span></span>  <br/> |<span data-ttu-id="3bf7f-119">否</span><span class="sxs-lookup"><span data-stu-id="3bf7f-119">No</span></span>  <br/> |<span data-ttu-id="3bf7f-120">一个整数，指定*WithinText*开始搜索中的位置。</span><span class="sxs-lookup"><span data-stu-id="3bf7f-120">An integer that specifies the location in  *WithinText*  to begin the search.</span></span> <span data-ttu-id="3bf7f-121">如果*启动*未指定，为负数，或者为 0，则搜索开始*WithinText*开头。</span><span class="sxs-lookup"><span data-stu-id="3bf7f-121">If  *Start*  is not specified, is a negative number, or is 0, the search starts at the beginning of  *WithinText*  .</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3bf7f-122">说明</span><span class="sxs-lookup"><span data-stu-id="3bf7f-122">Remarks</span></span>

<span data-ttu-id="3bf7f-123">如果*TextExpression*或*WithinText*为 NULL，则*CharIndex*将返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="3bf7f-123">If either  *TextExpression*  or  *WithinText*  is NULL,  *CharIndex*  returns NULL.</span></span> 
  
<span data-ttu-id="3bf7f-124">如果*WithinText*中找不到*TextExpression* ， *CharIndex*将返回 0。</span><span class="sxs-lookup"><span data-stu-id="3bf7f-124">If  *TextExpression*  is not found within  *WithinText*,  *CharIndex*  returns 0.</span></span> 
  
<span data-ttu-id="3bf7f-125">基于 1，不是从 0 开始，返回的起始位置。</span><span class="sxs-lookup"><span data-stu-id="3bf7f-125">The starting position returned is 1-based, not 0-based.</span></span>
  

