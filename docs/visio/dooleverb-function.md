---
title: DOOLEVERB 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251421
localization_priority: Normal
ms.assetid: d276c122-6326-75a7-220c-6a78e94e0db0
description: 执行动词 OLE 对象。
ms.openlocfilehash: a7786c3ef2b4039e288596ed367083a4ed3a6c13
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780130"
---
# <a name="dooleverb-function"></a><span data-ttu-id="f988b-103">DOOLEVERB 函数</span><span class="sxs-lookup"><span data-stu-id="f988b-103">DOOLEVERB Function</span></span>

<span data-ttu-id="f988b-104">执行动词 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="f988b-104">Executes a verb for the OLE object.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f988b-105">语法</span><span class="sxs-lookup"><span data-stu-id="f988b-105">Syntax</span></span>

<span data-ttu-id="f988b-106">DOOLEVERB ("* **动词** *")</span><span class="sxs-lookup"><span data-stu-id="f988b-106">DOOLEVERB(" ** *verb* ** ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f988b-107">参数</span><span class="sxs-lookup"><span data-stu-id="f988b-107">Parameters</span></span>

|<span data-ttu-id="f988b-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="f988b-108">**Name**</span></span>|<span data-ttu-id="f988b-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f988b-109">**Required/Optional**</span></span>|<span data-ttu-id="f988b-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f988b-110">**Data Type**</span></span>|<span data-ttu-id="f988b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f988b-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f988b-112">_"动作"_</span><span class="sxs-lookup"><span data-stu-id="f988b-112">_"verb"_</span></span> <br/> |<span data-ttu-id="f988b-113">必需</span><span class="sxs-lookup"><span data-stu-id="f988b-113">Required</span></span>  <br/> |<span data-ttu-id="f988b-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="f988b-114">**String**</span></span> <br/> |<span data-ttu-id="f988b-115">要执行的动作。</span><span class="sxs-lookup"><span data-stu-id="f988b-115">The verb to execute.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f988b-116">注解</span><span class="sxs-lookup"><span data-stu-id="f988b-116">Remarks</span></span>

<span data-ttu-id="f988b-p101">在 Visio 的早期版本中，此函数以 _DOOLEVERB 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。</span><span class="sxs-lookup"><span data-stu-id="f988b-p101">In earlier versions of Visio, this function appears as _DOOLEVERB. Visio versions 4.0 and later accept either style.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f988b-119">示例</span><span class="sxs-lookup"><span data-stu-id="f988b-119">Example</span></span>

<span data-ttu-id="f988b-120">DOOLEVERB("edit")</span><span class="sxs-lookup"><span data-stu-id="f988b-120">DOOLEVERB("edit")</span></span>
  
<span data-ttu-id="f988b-121">运行 OLE 对象程序，并显示链接或嵌入的对象，以便进行编辑。</span><span class="sxs-lookup"><span data-stu-id="f988b-121">Runs the OLE object program and displays the linked or embedded object so that it can be edited.</span></span>
  

