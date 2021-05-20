---
title: CONTAINERSHEETREF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bbdb2dea-4f75-b73e-a98a-0031f34dff2c
description: 返回对包含形状的指定容器的工作表引用。
ms.openlocfilehash: 473d8c0b81ecc568c1d4f3a3b3a885e1ceb4e00d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437264"
---
# <a name="containersheetref-function"></a><span data-ttu-id="9ff1e-103">CONTAINERSHEETREF 函数</span><span class="sxs-lookup"><span data-stu-id="9ff1e-103">CONTAINERSHEETREF Function</span></span>

<span data-ttu-id="9ff1e-104">返回对包含形状的指定容器的工作表引用。</span><span class="sxs-lookup"><span data-stu-id="9ff1e-104">Returns a sheet reference to the specified container that contains the shape.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="9ff1e-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="9ff1e-105">Version Information</span></span>

<span data-ttu-id="9ff1e-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="9ff1e-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="9ff1e-107">语法</span><span class="sxs-lookup"><span data-stu-id="9ff1e-107">Syntax</span></span>

<span data-ttu-id="9ff1e-108">CONTAINERSHEETREF (\*\* *index* \*\* \*\* *[， category]* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="9ff1e-108">CONTAINERSHEETREF(\*\* *index* \*\* \*\* *[, category]* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="9ff1e-109">参数</span><span class="sxs-lookup"><span data-stu-id="9ff1e-109">Parameters</span></span>

|<span data-ttu-id="9ff1e-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="9ff1e-110">**Name**</span></span>|<span data-ttu-id="9ff1e-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="9ff1e-111">**Required/Optional**</span></span>|<span data-ttu-id="9ff1e-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9ff1e-112">**Data Type**</span></span>|<span data-ttu-id="9ff1e-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="9ff1e-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="9ff1e-114">_index_</span><span class="sxs-lookup"><span data-stu-id="9ff1e-114">_index_</span></span> <br/> |<span data-ttu-id="9ff1e-115">必需</span><span class="sxs-lookup"><span data-stu-id="9ff1e-115">Required</span></span>  <br/> |<span data-ttu-id="9ff1e-116">**Integer**</span><span class="sxs-lookup"><span data-stu-id="9ff1e-116">**Integer**</span></span> <br/> |<span data-ttu-id="9ff1e-p101">从 1 开始的容器索引。有关详细信息，请参阅“注解”。</span><span class="sxs-lookup"><span data-stu-id="9ff1e-p101">The 1-based index of the container. See Remarks for more information.</span></span>  <br/> |
| <span data-ttu-id="9ff1e-119">_category_</span><span class="sxs-lookup"><span data-stu-id="9ff1e-119">_category_</span></span> <br/> |<span data-ttu-id="9ff1e-120">可选</span><span class="sxs-lookup"><span data-stu-id="9ff1e-120">Optional</span></span>  <br/> |<span data-ttu-id="9ff1e-121">**字符串**</span><span class="sxs-lookup"><span data-stu-id="9ff1e-121">**String**</span></span> <br/> |<span data-ttu-id="9ff1e-p102">容器的类别。有关详细信息，请参阅“注解”。</span><span class="sxs-lookup"><span data-stu-id="9ff1e-p102">The category of the container. See Remarks for more information.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="9ff1e-124">返回值</span><span class="sxs-lookup"><span data-stu-id="9ff1e-124">Return value</span></span>

<span data-ttu-id="9ff1e-125">ShapeSheet 参考</span><span class="sxs-lookup"><span data-stu-id="9ff1e-125">ShapeSheet reference</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9ff1e-126">备注</span><span class="sxs-lookup"><span data-stu-id="9ff1e-126">Remarks</span></span>

<span data-ttu-id="9ff1e-127">根据容器从前向后的 Z 顺序计算容器的索引。</span><span class="sxs-lookup"><span data-stu-id="9ff1e-127">The index of a container is calculated based on the z-order of containers from front to back.</span></span>
  
 <span data-ttu-id="9ff1e-128">*类别*  是用户定义的字符串，可用于对形状进行分类。</span><span class="sxs-lookup"><span data-stu-id="9ff1e-128">*Categories*  are user-defined strings that you can use to categorize shapes.</span></span> <span data-ttu-id="9ff1e-129">可以在形状 ShapeSheet 的 User.msvShapeCategories 单元格中定义类别。</span><span class="sxs-lookup"><span data-stu-id="9ff1e-129">You can define categories in the User.msvShapeCategories cell in the ShapeSheet for a shape.</span></span> <span data-ttu-id="9ff1e-130">可以通过用分号分隔类别为形状定义多个类别。</span><span class="sxs-lookup"><span data-stu-id="9ff1e-130">You can define multiple categories for a shape by separating the categories with semi-colons.</span></span> 
  
<span data-ttu-id="9ff1e-131">如果形状不是容器的成员，或者没有容器与指定的索引号和类别相匹配，则 CONTAINERSHEETREF 返回 #REF!。</span><span class="sxs-lookup"><span data-stu-id="9ff1e-131">If the shape is not a member of a container, or if there is no container that matches both the specified index number and the category, CONTAINERSHEETREF returns #REF!.</span></span>
  
## <a name="example"></a><span data-ttu-id="9ff1e-132">示例</span><span class="sxs-lookup"><span data-stu-id="9ff1e-132">Example</span></span>

<span data-ttu-id="9ff1e-133">CONTAINERSHEETREF (1) ！Height</span><span class="sxs-lookup"><span data-stu-id="9ff1e-133">CONTAINERSHEETREF(1)!Height</span></span> 
  
<span data-ttu-id="9ff1e-134">返回容器的 Height 单元格中的值，该容器位于形状所属页面的最顶层。</span><span class="sxs-lookup"><span data-stu-id="9ff1e-134">Returns the value in the Height cell of the container that is most forward on the page to which the shape belongs.</span></span> 
  

