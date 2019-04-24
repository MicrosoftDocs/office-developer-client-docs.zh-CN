---
title: 内容功能 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4d8d6a34-f884-40a4-b330-5c104d16cf97
description: 将文本字符串插入另一个文本字符串。 它在起始位置删除第一个字符串中的指定长度的字符, 然后将第二个字符串插入到第一个字符串中的起始位置。
ms.openlocfilehash: 591823952faa0d593b6db1f5bfb00cc68a894a8d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311023"
---
# <a name="stuff-function-access-custom-web-app"></a><span data-ttu-id="a84b4-104">内容功能 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="a84b4-104">Stuff Function (Access custom web app)</span></span>

<span data-ttu-id="a84b4-105">将文本字符串插入另一个文本字符串。</span><span class="sxs-lookup"><span data-stu-id="a84b4-105">Inserts a text string into another text string.</span></span> <span data-ttu-id="a84b4-106">它在起始位置删除第一个字符串中的指定长度的字符, 然后将第二个字符串插入到第一个字符串中的起始位置。</span><span class="sxs-lookup"><span data-stu-id="a84b4-106">It deletes a specified length of characters in the first string at the start position and then inserts the second string into the first string at the start position.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a84b4-p103">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="a84b4-p103">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="a84b4-109">语法</span><span class="sxs-lookup"><span data-stu-id="a84b4-109">Syntax</span></span>

 <span data-ttu-id="a84b4-110">**内容**(*IntoTextExpression*、 *Start*、 *Length*、 *ThisTextExpression*)</span><span class="sxs-lookup"><span data-stu-id="a84b4-110">**Stuff** (*IntoTextExpression*, *Start*, *Length*, *ThisTextExpression*)</span></span> 
  
<span data-ttu-id="a84b4-111">**内容**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="a84b4-111">The **Stuff** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="a84b4-112">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="a84b4-112">**Argument name**</span></span>|<span data-ttu-id="a84b4-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="a84b4-113">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="a84b4-114">*IntoTextExpression*</span><span class="sxs-lookup"><span data-stu-id="a84b4-114">*IntoTextExpression*</span></span>  <br/> |<span data-ttu-id="a84b4-115">一个文本表达式, 指定将在其中插入*ThisTextExpression*指定的文本的文本。</span><span class="sxs-lookup"><span data-stu-id="a84b4-115">A text expression that specifies the text into which the text specified by the  *ThisTextExpression*  will be inserted.</span></span>  <br/> |
| <span data-ttu-id="a84b4-116">*Start*</span><span class="sxs-lookup"><span data-stu-id="a84b4-116">*Start*</span></span>  <br/> |<span data-ttu-id="a84b4-117">一个整数值, 用于指定要开始删除和插入的位置。</span><span class="sxs-lookup"><span data-stu-id="a84b4-117">An integer value that specifies the location to start deletion and insertion.</span></span> <span data-ttu-id="a84b4-118">如果 start 或 length 为负值, 则返回一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="a84b4-118">If start or length is negative, a null string is returned.</span></span> <span data-ttu-id="a84b4-119">如果 start 长于第一个*IntoTextExpression* , 则返回 null 字符串。</span><span class="sxs-lookup"><span data-stu-id="a84b4-119">If start is longer than the first  *IntoTextExpression*  , a null string is returned.</span></span>  <br/> |
| <span data-ttu-id="a84b4-120">*Length*</span><span class="sxs-lookup"><span data-stu-id="a84b4-120">*Length*</span></span>  <br/> |<span data-ttu-id="a84b4-121">一个整数, 指定要删除的字符数。</span><span class="sxs-lookup"><span data-stu-id="a84b4-121">An integer that specifies the number of characters to delete.</span></span> <span data-ttu-id="a84b4-122">如果 length 比第一个*IntoTextExpression*长, 则在最后一个*IntoTextExpression*中的最后一个字符处进行删除。</span><span class="sxs-lookup"><span data-stu-id="a84b4-122">If length is longer than the first  *IntoTextExpression*  , deletion occurs up to the last character in the last  *IntoTextExpression*  .</span></span>  <br/> |
| <span data-ttu-id="a84b4-123">*ThisTextExpression*</span><span class="sxs-lookup"><span data-stu-id="a84b4-123">*ThisTextExpression*</span></span>  <br/> |<span data-ttu-id="a84b4-124">文本表达式 hat 指定要插入到*IntoTextExpression*中的文本。</span><span class="sxs-lookup"><span data-stu-id="a84b4-124">A text expression hat specifies the text to insert into  *IntoTextExpression*  .</span></span> <span data-ttu-id="a84b4-125">此表达式将替换*IntoTextExpression*从*Start 开始*的长度字符。</span><span class="sxs-lookup"><span data-stu-id="a84b4-125">This expression will replace length characters of  *IntoTextExpression*  beginning at  *Start*  .</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a84b4-126">注解</span><span class="sxs-lookup"><span data-stu-id="a84b4-126">Remarks</span></span>

<span data-ttu-id="a84b4-127">如果*Start*或*Length*参数为负, 或者起始位置大于第一个字符串的长度, 则返回 null 字符串。</span><span class="sxs-lookup"><span data-stu-id="a84b4-127">If the  *Start*  or  *Length*  arguments are negative, or if the starting position is larger than length of the first string, a null string is returned.</span></span> <span data-ttu-id="a84b4-128">如果起始位置为 0, 则返回 null 值。</span><span class="sxs-lookup"><span data-stu-id="a84b4-128">If the start position is 0, a null value is returned.</span></span> <span data-ttu-id="a84b4-129">如果要删除的长度超过第一个字符串, 将被删除为第一个字符串中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="a84b4-129">If the length to delete is longer than the first string, it is deleted to the first character in the first string.</span></span> 
  

