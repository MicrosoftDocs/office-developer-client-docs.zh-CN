---
title: 材料 （英文） 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4d8d6a34-f884-40a4-b330-5c104d16cf97
description: 其他文本字符串中插入的文本字符串。 删除指定的开始位置处的第一个字符串中的字符长度及其的开始位置处的第一个字符串中插入第二个字符串。
ms.openlocfilehash: 5540bb5936803370835a0c3d80b420edc13d0de6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773609"
---
# <a name="stuff-function-access-custom-web-app"></a><span data-ttu-id="0bf39-104">材料 （英文） 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="0bf39-104">Stuff Function (Access custom web app)</span></span>

<span data-ttu-id="0bf39-105">其他文本字符串中插入的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="0bf39-105">Inserts a text string into another text string.</span></span> <span data-ttu-id="0bf39-106">删除指定的开始位置处的第一个字符串中的字符长度及其的开始位置处的第一个字符串中插入第二个字符串。</span><span class="sxs-lookup"><span data-stu-id="0bf39-106">It deletes a specified length of characters in the first string at the start position and then inserts the second string into the first string at the start position.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0bf39-p103">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="0bf39-p103">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0bf39-109">语法</span><span class="sxs-lookup"><span data-stu-id="0bf39-109">Syntax</span></span>

 <span data-ttu-id="0bf39-110">**材料 （英文)**（*IntoTextExpression*，*启动*，*长度*， *ThisTextExpression*）</span><span class="sxs-lookup"><span data-stu-id="0bf39-110">**Stuff** (*IntoTextExpression*, *Start*, *Length*, *ThisTextExpression*)</span></span> 
  
<span data-ttu-id="0bf39-111">**资料**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="0bf39-111">The **Stuff** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="0bf39-112">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="0bf39-112">**Argument name**</span></span>|<span data-ttu-id="0bf39-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="0bf39-113">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="0bf39-114">*IntoTextExpression*</span><span class="sxs-lookup"><span data-stu-id="0bf39-114">*IntoTextExpression*</span></span>  <br/> |<span data-ttu-id="0bf39-115">指定将插入*ThisTextExpression*指定的文本的文本的文本表达式。</span><span class="sxs-lookup"><span data-stu-id="0bf39-115">A text expression that specifies the text into which the text specified by the  *ThisTextExpression*  will be inserted.</span></span>  <br/> |
| <span data-ttu-id="0bf39-116">*Start*</span><span class="sxs-lookup"><span data-stu-id="0bf39-116">*Start*</span></span>  <br/> |<span data-ttu-id="0bf39-117">一个整数值，指定要启动删除和插入的位置。</span><span class="sxs-lookup"><span data-stu-id="0bf39-117">An integer value that specifies the location to start deletion and insertion.</span></span> <span data-ttu-id="0bf39-118">如果开始或长度为负数，则返回空字符串。</span><span class="sxs-lookup"><span data-stu-id="0bf39-118">If start or length is negative, a null string is returned.</span></span> <span data-ttu-id="0bf39-119">如果开始长于第一个*IntoTextExpression* ，则返回空字符串。</span><span class="sxs-lookup"><span data-stu-id="0bf39-119">If start is longer than the first  *IntoTextExpression*  , a null string is returned.</span></span>  <br/> |
| <span data-ttu-id="0bf39-120">*Length*</span><span class="sxs-lookup"><span data-stu-id="0bf39-120">*Length*</span></span>  <br/> |<span data-ttu-id="0bf39-121">一个整数，指定要删除的字符数。</span><span class="sxs-lookup"><span data-stu-id="0bf39-121">An integer that specifies the number of characters to delete.</span></span> <span data-ttu-id="0bf39-122">如果长度大于第一个*IntoTextExpression* ，删除发生最多为最后一个*IntoTextExpression*中的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="0bf39-122">If length is longer than the first  *IntoTextExpression*  , deletion occurs up to the last character in the last  *IntoTextExpression*  .</span></span>  <br/> |
| <span data-ttu-id="0bf39-123">*ThisTextExpression*</span><span class="sxs-lookup"><span data-stu-id="0bf39-123">*ThisTextExpression*</span></span>  <br/> |<span data-ttu-id="0bf39-124">文本表达式帽指定*IntoTextExpression*中插入的文本。</span><span class="sxs-lookup"><span data-stu-id="0bf39-124">A text expression hat specifies the text to insert into  *IntoTextExpression*  .</span></span> <span data-ttu-id="0bf39-125">该表达式将替换开头*开始*的*IntoTextExpression*长度的字符。</span><span class="sxs-lookup"><span data-stu-id="0bf39-125">This expression will replace length characters of  *IntoTextExpression*  beginning at  *Start*  .</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0bf39-126">说明</span><span class="sxs-lookup"><span data-stu-id="0bf39-126">Remarks</span></span>

<span data-ttu-id="0bf39-127">如果*启动*或*长度*参数为负，或如果的起始位置大于第一个字符串的长度，则返回空字符串。</span><span class="sxs-lookup"><span data-stu-id="0bf39-127">If the  *Start*  or  *Length*  arguments are negative, or if the starting position is larger than length of the first string, a null string is returned.</span></span> <span data-ttu-id="0bf39-128">如果的起始位置为 0，则返回 null 值。</span><span class="sxs-lookup"><span data-stu-id="0bf39-128">If the start position is 0, a null value is returned.</span></span> <span data-ttu-id="0bf39-129">如果要删除的长度超过的第一个字符串，它将删除第一个字符串中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="0bf39-129">If the length to delete is longer than the first string, it is deleted to the first character in the first string.</span></span> 
  

