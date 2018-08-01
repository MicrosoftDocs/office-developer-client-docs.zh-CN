---
title: CONTAINERSHEETREF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bbdb2dea-4f75-b73e-a98a-0031f34dff2c
description: 返回对包含形状的指定容器的工作表引用。
ms.openlocfilehash: 6392b4c1a2652f1a831dc585c0be0f430a5ffe0e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779980"
---
# <a name="containersheetref-function"></a><span data-ttu-id="2a7d7-103">CONTAINERSHEETREF 函数</span><span class="sxs-lookup"><span data-stu-id="2a7d7-103">CONTAINERSHEETREF Function</span></span>

<span data-ttu-id="2a7d7-104">返回对包含形状的指定容器的工作表引用。</span><span class="sxs-lookup"><span data-stu-id="2a7d7-104">Returns a sheet reference to the specified container that contains the shape.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="2a7d7-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="2a7d7-105">Version Information</span></span>

<span data-ttu-id="2a7d7-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="2a7d7-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2a7d7-107">语法</span><span class="sxs-lookup"><span data-stu-id="2a7d7-107">Syntax</span></span>

<span data-ttu-id="2a7d7-108">CONTAINERSHEETREF (* **索引** * * * *[、 类别]* * *)</span><span class="sxs-lookup"><span data-stu-id="2a7d7-108">CONTAINERSHEETREF(** *index* ** ** *[, category]* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="2a7d7-109">参数</span><span class="sxs-lookup"><span data-stu-id="2a7d7-109">Parameters</span></span>

|<span data-ttu-id="2a7d7-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="2a7d7-110">**Name**</span></span>|<span data-ttu-id="2a7d7-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="2a7d7-111">**Required/Optional**</span></span>|<span data-ttu-id="2a7d7-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2a7d7-112">**Data Type**</span></span>|<span data-ttu-id="2a7d7-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a7d7-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2a7d7-114">_index_</span><span class="sxs-lookup"><span data-stu-id="2a7d7-114">_index_</span></span> <br/> |<span data-ttu-id="2a7d7-115">必需</span><span class="sxs-lookup"><span data-stu-id="2a7d7-115">Required</span></span>  <br/> |<span data-ttu-id="2a7d7-116">**Integer**</span><span class="sxs-lookup"><span data-stu-id="2a7d7-116">**Integer**</span></span> <br/> |<span data-ttu-id="2a7d7-p101">从 1 开始的容器索引。有关详细信息，请参阅“注解”。</span><span class="sxs-lookup"><span data-stu-id="2a7d7-p101">The 1-based index of the container. See Remarks for more information.</span></span>  <br/> |
| <span data-ttu-id="2a7d7-119">_category_</span><span class="sxs-lookup"><span data-stu-id="2a7d7-119">_category_</span></span> <br/> |<span data-ttu-id="2a7d7-120">可选</span><span class="sxs-lookup"><span data-stu-id="2a7d7-120">Optional</span></span>  <br/> |<span data-ttu-id="2a7d7-121">**字符串**</span><span class="sxs-lookup"><span data-stu-id="2a7d7-121">**String**</span></span> <br/> |<span data-ttu-id="2a7d7-p102">容器的类别。有关详细信息，请参阅“注解”。</span><span class="sxs-lookup"><span data-stu-id="2a7d7-p102">The category of the container. See Remarks for more information.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="2a7d7-124">返回值</span><span class="sxs-lookup"><span data-stu-id="2a7d7-124">Return value</span></span>

<span data-ttu-id="2a7d7-125">ShapeSheet 参考</span><span class="sxs-lookup"><span data-stu-id="2a7d7-125">ShapeSheet reference</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2a7d7-126">注解</span><span class="sxs-lookup"><span data-stu-id="2a7d7-126">Remarks</span></span>

<span data-ttu-id="2a7d7-127">根据容器从前向后的 Z 顺序计算容器的索引。</span><span class="sxs-lookup"><span data-stu-id="2a7d7-127">The index of a container is calculated based on the z-order of containers from front to back.</span></span>
  
 <span data-ttu-id="2a7d7-128">*类别*是可用于对形状进行分类的用户定义的字符串。</span><span class="sxs-lookup"><span data-stu-id="2a7d7-128">*Categories*  are user-defined strings that you can use to categorize shapes.</span></span> <span data-ttu-id="2a7d7-129">您可以在形状的 ShapeSheet User.msvShapeCategories 单元格中定义类别。</span><span class="sxs-lookup"><span data-stu-id="2a7d7-129">You can define categories in the User.msvShapeCategories cell in the ShapeSheet for a shape.</span></span> <span data-ttu-id="2a7d7-130">您可以通过使用分号分隔类别来定义形状的多个类别。</span><span class="sxs-lookup"><span data-stu-id="2a7d7-130">You can define multiple categories for a shape by separating the categories with semi-colons.</span></span> 
  
<span data-ttu-id="2a7d7-131">如果形状不是容器的成员，或者没有容器与指定的索引号和类别相匹配，则 CONTAINERSHEETREF 返回 #REF!。</span><span class="sxs-lookup"><span data-stu-id="2a7d7-131">If the shape is not a member of a container, or if there is no container that matches both the specified index number and the category, CONTAINERSHEETREF returns #REF!.</span></span>
  
## <a name="example"></a><span data-ttu-id="2a7d7-132">示例</span><span class="sxs-lookup"><span data-stu-id="2a7d7-132">Example</span></span>

<span data-ttu-id="2a7d7-133">CONTAINERSHEETREF(1)!Height</span><span class="sxs-lookup"><span data-stu-id="2a7d7-133">CONTAINERSHEETREF(1)!Height</span></span> 
  
<span data-ttu-id="2a7d7-134">返回容器的 Height 单元格中的值，该容器位于形状所属页面的最顶层。</span><span class="sxs-lookup"><span data-stu-id="2a7d7-134">Returns the value in the Height cell of the container that is most forward on the page to which the shape belongs.</span></span> 
  

