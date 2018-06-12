---
title: UPPER 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251509
localization_priority: Normal
ms.assetid: ef94ee0f-dbb8-a2e1-1805-8a6609830d2a
description: 返回一个转换为大写的字符串。
ms.openlocfilehash: df8250ef634b04cb19cbb4e120bd02eb77531a82
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781597"
---
# <a name="upper-function"></a><span data-ttu-id="d0544-103">UPPER 函数</span><span class="sxs-lookup"><span data-stu-id="d0544-103">UPPER Function</span></span>

<span data-ttu-id="d0544-104">返回一个转换为大写的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0544-104">Returns a string converted to uppercase.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="d0544-105">语法</span><span class="sxs-lookup"><span data-stu-id="d0544-105">Syntax</span></span>

<span data-ttu-id="d0544-106">右上 (* **表达式** *)</span><span class="sxs-lookup"><span data-stu-id="d0544-106">UPPER(** *expression* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d0544-107">参数</span><span class="sxs-lookup"><span data-stu-id="d0544-107">Parameters</span></span>

|<span data-ttu-id="d0544-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="d0544-108">**Name**</span></span>|<span data-ttu-id="d0544-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d0544-109">**Required/Optional**</span></span>|<span data-ttu-id="d0544-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d0544-110">**Data Type**</span></span>|<span data-ttu-id="d0544-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d0544-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d0544-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="d0544-112">_expression_</span></span> <br/> |<span data-ttu-id="d0544-113">必需</span><span class="sxs-lookup"><span data-stu-id="d0544-113">Required</span></span>  <br/> |<span data-ttu-id="d0544-114">**而异**</span><span class="sxs-lookup"><span data-stu-id="d0544-114">**Varies**</span></span> <br/> | <span data-ttu-id="d0544-115">可以是字符串、单元格引用或表达式；结果转换为字符串，然后再转换为大写形式。</span><span class="sxs-lookup"><span data-stu-id="d0544-115">A string, a cell reference, or an expression; the result is converted to a string, which is then converted to uppercase.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d0544-116">注解</span><span class="sxs-lookup"><span data-stu-id="d0544-116">Remarks</span></span>

<span data-ttu-id="d0544-117">大小写转换取决于当前的用户设置，并且特定于区域设置。</span><span class="sxs-lookup"><span data-stu-id="d0544-117">The case conversion is locale-specific, based on the current user settings.</span></span> 
  
## <a name="example"></a><span data-ttu-id="d0544-118">示例</span><span class="sxs-lookup"><span data-stu-id="d0544-118">Example</span></span>

<span data-ttu-id="d0544-119">UPPER("mIxEd CAse")</span><span class="sxs-lookup"><span data-stu-id="d0544-119">UPPER("mIxEd CAse")</span></span> 
  
<span data-ttu-id="d0544-120">返回“MIXED CASE”。</span><span class="sxs-lookup"><span data-stu-id="d0544-120">Returns "MIXED CASE".</span></span> 
  

