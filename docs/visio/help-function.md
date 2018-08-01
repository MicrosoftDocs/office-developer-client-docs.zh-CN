---
title: HELP 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251436
localization_priority: Normal
ms.assetid: 5b358c38-6ed1-3fbe-c1d1-1a56ebbaa870
description: 打开搜索框中的指定关键字的 HTML 帮助文件。
ms.openlocfilehash: 4671b18333bdae953c487662cd880849233df7f5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780391"
---
# <a name="help-function"></a><span data-ttu-id="cfcb2-103">HELP 函数</span><span class="sxs-lookup"><span data-stu-id="cfcb2-103">HELP Function</span></span>

<span data-ttu-id="cfcb2-104">打开**搜索**框中的指定*关键字*的 HTML 帮助文件。</span><span class="sxs-lookup"><span data-stu-id="cfcb2-104">Opens an HTML Help file with the specifed  *keyword*  in the **Search** box.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="cfcb2-105">语法</span><span class="sxs-lookup"><span data-stu-id="cfcb2-105">Syntax</span></span>

<span data-ttu-id="cfcb2-106">帮助 ("* * *filename.chm!keyword* * *")</span><span class="sxs-lookup"><span data-stu-id="cfcb2-106">HELP(" ** *filename.chm!keyword* ** ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="cfcb2-107">参数</span><span class="sxs-lookup"><span data-stu-id="cfcb2-107">Parameters</span></span>

|<span data-ttu-id="cfcb2-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="cfcb2-108">**Name**</span></span>|<span data-ttu-id="cfcb2-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="cfcb2-109">**Required/Optional**</span></span>|<span data-ttu-id="cfcb2-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cfcb2-110">**Data Type**</span></span>|<span data-ttu-id="cfcb2-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="cfcb2-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cfcb2-112">_filename.chm!keyword_</span><span class="sxs-lookup"><span data-stu-id="cfcb2-112">_filename.chm!keyword_</span></span> <br/> |<span data-ttu-id="cfcb2-113">必需</span><span class="sxs-lookup"><span data-stu-id="cfcb2-113">Required</span></span>  <br/> |<span data-ttu-id="cfcb2-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="cfcb2-114">**String**</span></span> <br/> | <span data-ttu-id="cfcb2-115">要搜索的帮助文件的文件名和关键字。</span><span class="sxs-lookup"><span data-stu-id="cfcb2-115">The filename of the Help file and the keyword to search for.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cfcb2-116">注解</span><span class="sxs-lookup"><span data-stu-id="cfcb2-116">Remarks</span></span>

<span data-ttu-id="cfcb2-117">如果未不指定任何*关键字*，则帮助函数将打开的帮助文件的内容页。</span><span class="sxs-lookup"><span data-stu-id="cfcb2-117">If no  *keyword*  is specified, the HELP function opens the contents page of the Help file.</span></span> 
  
## <a name="example"></a><span data-ttu-id="cfcb2-118">示例</span><span class="sxs-lookup"><span data-stu-id="cfcb2-118">Example</span></span>

<span data-ttu-id="cfcb2-119">HELP("visio.chm!shapesheet")</span><span class="sxs-lookup"><span data-stu-id="cfcb2-119">HELP("visio.chm!shapesheet")</span></span> 
  
<span data-ttu-id="cfcb2-120">打开文件 Visio 帮助文件，并显示关键字为“shapesheet”的主题列表。</span><span class="sxs-lookup"><span data-stu-id="cfcb2-120">Opens the Visio Help file and displays a list of the topic(s) whose keyword is "shapesheet."</span></span> 
  

