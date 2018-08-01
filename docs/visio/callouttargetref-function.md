---
title: CALLOUTTARGETREF 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c67cfd32-5911-d8e9-dd51-fd4885dd2b0d
description: 返回对标注形状的目标形状的工作表引用。
ms.openlocfilehash: 1b0cb7c6737a810a0ade65f19afaff7bb4b9f616
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779796"
---
# <a name="callouttargetref-function"></a><span data-ttu-id="a1089-103">CALLOUTTARGETREF 函数</span><span class="sxs-lookup"><span data-stu-id="a1089-103">CALLOUTTARGETREF Function</span></span>

<span data-ttu-id="a1089-104">返回对标注形状的目标形状的工作表引用。</span><span class="sxs-lookup"><span data-stu-id="a1089-104">Returns a sheet reference to the target shape of the callout shape.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="a1089-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="a1089-105">Version Information</span></span>

<span data-ttu-id="a1089-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="a1089-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="a1089-107">语法</span><span class="sxs-lookup"><span data-stu-id="a1089-107">Syntax</span></span>

<span data-ttu-id="a1089-108">CALLOUTTARGETREF()!</span><span class="sxs-lookup"><span data-stu-id="a1089-108">CALLOUTTARGETREF()!</span></span>
  
### <a name="return-value"></a><span data-ttu-id="a1089-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a1089-109">Return value</span></span>

<span data-ttu-id="a1089-110">ShapeSheet 参考</span><span class="sxs-lookup"><span data-stu-id="a1089-110">ShapeSheet reference</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a1089-111">注解</span><span class="sxs-lookup"><span data-stu-id="a1089-111">Remarks</span></span>

<span data-ttu-id="a1089-112">如果形状不是标注形状，或者不与目标形状相关联，则 CALLOUTTARGETREF 返回 #REF。</span><span class="sxs-lookup"><span data-stu-id="a1089-112">If the shape is not a callout shape, or if it is not associated with a target shape, CALLOUTTARGETREF returns #REF.</span></span>
  
## <a name="example"></a><span data-ttu-id="a1089-113">示例</span><span class="sxs-lookup"><span data-stu-id="a1089-113">Example</span></span>

<span data-ttu-id="a1089-114">CALLOUTTARGETREF()!Height</span><span class="sxs-lookup"><span data-stu-id="a1089-114">CALLOUTTARGETREF()!Height</span></span> 
  
<span data-ttu-id="a1089-115">返回与标注相关的形状的 Height 单元格中的值。</span><span class="sxs-lookup"><span data-stu-id="a1089-115">Returns the value in the Height cell of the shape that is associated with the callout.</span></span> 
  

