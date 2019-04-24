---
title: LISTSHEETREF 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 87ddbc35-8577-0a96-20b8-aa7734764c5b
description: 返回对包含形状的列表容器形状的工作表引用。
ms.openlocfilehash: 748a248f68345e97e97ca90a4603b6e164a551c4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32284079"
---
# <a name="listsheetref-function"></a><span data-ttu-id="2829e-103">LISTSHEETREF 函数</span><span class="sxs-lookup"><span data-stu-id="2829e-103">LISTSHEETREF Function</span></span>

<span data-ttu-id="2829e-104">返回对包含形状的列表容器形状的工作表引用。</span><span class="sxs-lookup"><span data-stu-id="2829e-104">Returns a sheet reference to the list container shape that contains the shape.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="2829e-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="2829e-105">Version Information</span></span>

<span data-ttu-id="2829e-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="2829e-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2829e-107">语法</span><span class="sxs-lookup"><span data-stu-id="2829e-107">Syntax</span></span>

<span data-ttu-id="2829e-108">LISTMEMBERCOUNT ()</span><span class="sxs-lookup"><span data-stu-id="2829e-108">LISTMEMBERCOUNT()</span></span>
  
### <a name="return-value"></a><span data-ttu-id="2829e-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2829e-109">Return value</span></span>

<span data-ttu-id="2829e-110">ShapeSheet 参考</span><span class="sxs-lookup"><span data-stu-id="2829e-110">ShapeSheet reference</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2829e-111">注解</span><span class="sxs-lookup"><span data-stu-id="2829e-111">Remarks</span></span>

<span data-ttu-id="2829e-112">如果形状不是列表成员，则 LISTSHEETREF 函数返回 #REF!。</span><span class="sxs-lookup"><span data-stu-id="2829e-112">If the shape is not a list member, the LISTSHEETREF function returns #REF!.</span></span>
  
## <a name="example"></a><span data-ttu-id="2829e-113">示例</span><span class="sxs-lookup"><span data-stu-id="2829e-113">Example</span></span>

<span data-ttu-id="2829e-114">LISTSHEETREF (1)!高度</span><span class="sxs-lookup"><span data-stu-id="2829e-114">LISTSHEETREF(1)!Height</span></span> 
  
<span data-ttu-id="2829e-115">返回包含形状的列表容器形状的 Height 单元格中的值。</span><span class="sxs-lookup"><span data-stu-id="2829e-115">Returns the value in the Height cell of the list container shape that contains the shape.</span></span> 
  

