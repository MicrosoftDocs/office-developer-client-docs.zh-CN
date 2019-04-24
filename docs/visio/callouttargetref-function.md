---
title: CALLOUTTARGETREF 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c67cfd32-5911-d8e9-dd51-fd4885dd2b0d
description: 返回对标注形状的目标形状的工作表引用。
ms.openlocfilehash: aeeb919fb2efc175d8e5ce23f464503c13331249
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337245"
---
# <a name="callouttargetref-function"></a><span data-ttu-id="134b8-103">CALLOUTTARGETREF 函数</span><span class="sxs-lookup"><span data-stu-id="134b8-103">CALLOUTTARGETREF Function</span></span>

<span data-ttu-id="134b8-104">返回对标注形状的目标形状的工作表引用。</span><span class="sxs-lookup"><span data-stu-id="134b8-104">Returns a sheet reference to the target shape of the callout shape.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="134b8-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="134b8-105">Version Information</span></span>

<span data-ttu-id="134b8-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="134b8-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="134b8-107">语法</span><span class="sxs-lookup"><span data-stu-id="134b8-107">Syntax</span></span>

<span data-ttu-id="134b8-108">CALLOUTTARGETREF ()!</span><span class="sxs-lookup"><span data-stu-id="134b8-108">CALLOUTTARGETREF()!</span></span>
  
### <a name="return-value"></a><span data-ttu-id="134b8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="134b8-109">Return value</span></span>

<span data-ttu-id="134b8-110">ShapeSheet 参考</span><span class="sxs-lookup"><span data-stu-id="134b8-110">ShapeSheet reference</span></span>
  
## <a name="remarks"></a><span data-ttu-id="134b8-111">注解</span><span class="sxs-lookup"><span data-stu-id="134b8-111">Remarks</span></span>

<span data-ttu-id="134b8-112">如果形状不是标注形状, 或者形状不与目标形状相关联, 则 CALLOUTTARGETREF 返回 #REF。</span><span class="sxs-lookup"><span data-stu-id="134b8-112">If the shape is not a callout shape, or if it is not associated with a target shape, CALLOUTTARGETREF returns #REF.</span></span>
  
## <a name="example"></a><span data-ttu-id="134b8-113">示例</span><span class="sxs-lookup"><span data-stu-id="134b8-113">Example</span></span>

<span data-ttu-id="134b8-114">CALLOUTTARGETREF ()!高度</span><span class="sxs-lookup"><span data-stu-id="134b8-114">CALLOUTTARGETREF()!Height</span></span> 
  
<span data-ttu-id="134b8-115">返回与标注相关的形状的 Height 单元格中的值。</span><span class="sxs-lookup"><span data-stu-id="134b8-115">Returns the value in the Height cell of the shape that is associated with the callout.</span></span> 
  

