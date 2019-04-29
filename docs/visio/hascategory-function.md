---
title: HASCATEGORY 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed3c997b-0a58-0432-c468-a24614b67f2e
description: 如果形状的类别列表中包含指定的字符串，则返回 TRUE。
ms.openlocfilehash: 902819f981b53aed96695e181ab556d3841d97c9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433351"
---
# <a name="hascategory-function"></a><span data-ttu-id="20723-103">HASCATEGORY 函数</span><span class="sxs-lookup"><span data-stu-id="20723-103">HASCATEGORY Function</span></span>

<span data-ttu-id="20723-104">如果形状的类别列表中包含指定的字符串，则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="20723-104">Returns TRUE if the specified string is found in the shape's category list.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="20723-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="20723-105">Version Information</span></span>

<span data-ttu-id="20723-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="20723-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="20723-107">语法</span><span class="sxs-lookup"><span data-stu-id="20723-107">Syntax</span></span>

<span data-ttu-id="20723-108">HASCATEGORY (\* \* *category* \* \*)</span><span class="sxs-lookup"><span data-stu-id="20723-108">HASCATEGORY(\*\* *category* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="20723-109">参数</span><span class="sxs-lookup"><span data-stu-id="20723-109">Parameters</span></span>

|<span data-ttu-id="20723-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="20723-110">**Name**</span></span>|<span data-ttu-id="20723-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="20723-111">**Required/Optional**</span></span>|<span data-ttu-id="20723-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="20723-112">**Data Type**</span></span>|<span data-ttu-id="20723-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="20723-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="20723-114">_类别_</span><span class="sxs-lookup"><span data-stu-id="20723-114">_category_</span></span> <br/> |<span data-ttu-id="20723-115">必需</span><span class="sxs-lookup"><span data-stu-id="20723-115">Required</span></span>  <br/> |<span data-ttu-id="20723-116">**String**</span><span class="sxs-lookup"><span data-stu-id="20723-116">**String**</span></span> <br/> |<span data-ttu-id="20723-117">要搜索的类别。</span><span class="sxs-lookup"><span data-stu-id="20723-117">The category to search for.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="20723-118">返回值</span><span class="sxs-lookup"><span data-stu-id="20723-118">Return value</span></span>

 <span data-ttu-id="20723-119">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="20723-119">**Boolean**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="20723-120">说明</span><span class="sxs-lookup"><span data-stu-id="20723-120">Remarks</span></span>

 <span data-ttu-id="20723-121">*类别*是用户定义的字符串, 可用于对形状进行分类。</span><span class="sxs-lookup"><span data-stu-id="20723-121">*Categories*  are user-defined strings that you can use to categorize shapes.</span></span> <span data-ttu-id="20723-122">可以在形状 ShapeSheet 的 User.msvShapeCategories 单元格中定义类别。</span><span class="sxs-lookup"><span data-stu-id="20723-122">You can define categories in the User.msvShapeCategories cell in the ShapeSheet for a shape.</span></span> <span data-ttu-id="20723-123">可以通过用分号分隔类别来为形状定义多个类别。</span><span class="sxs-lookup"><span data-stu-id="20723-123">You can define multiple categories for a shape by separating the categories with semi-colons.</span></span> 
  

