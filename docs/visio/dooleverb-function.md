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
description: 执行 OLE 对象的动作。
ms.openlocfilehash: c339d03a00afdf7f777bb0624ddb8fa75f277e05
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435660"
---
# <a name="dooleverb-function"></a><span data-ttu-id="f954a-103">DOOLEVERB 函数</span><span class="sxs-lookup"><span data-stu-id="f954a-103">DOOLEVERB Function</span></span>

<span data-ttu-id="f954a-104">执行 OLE 对象的动作。</span><span class="sxs-lookup"><span data-stu-id="f954a-104">Executes a verb for the OLE object.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f954a-105">语法</span><span class="sxs-lookup"><span data-stu-id="f954a-105">Syntax</span></span>

<span data-ttu-id="f954a-106">DOOLEVERB ("\* \* *verb* \* \*")</span><span class="sxs-lookup"><span data-stu-id="f954a-106">DOOLEVERB(" \*\* *verb* \*\* ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f954a-107">参数</span><span class="sxs-lookup"><span data-stu-id="f954a-107">Parameters</span></span>

|<span data-ttu-id="f954a-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="f954a-108">**Name**</span></span>|<span data-ttu-id="f954a-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f954a-109">**Required/Optional**</span></span>|<span data-ttu-id="f954a-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f954a-110">**Data Type**</span></span>|<span data-ttu-id="f954a-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f954a-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f954a-112">_动词_</span><span class="sxs-lookup"><span data-stu-id="f954a-112">_"verb"_</span></span> <br/> |<span data-ttu-id="f954a-113">必需</span><span class="sxs-lookup"><span data-stu-id="f954a-113">Required</span></span>  <br/> |<span data-ttu-id="f954a-114">**String**</span><span class="sxs-lookup"><span data-stu-id="f954a-114">**String**</span></span> <br/> |<span data-ttu-id="f954a-115">要执行的动作。</span><span class="sxs-lookup"><span data-stu-id="f954a-115">The verb to execute.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f954a-116">说明</span><span class="sxs-lookup"><span data-stu-id="f954a-116">Remarks</span></span>

<span data-ttu-id="f954a-p101">在 Visio 的早期版本中，此函数以 _DOOLEVERB 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。</span><span class="sxs-lookup"><span data-stu-id="f954a-p101">In earlier versions of Visio, this function appears as _DOOLEVERB. Visio versions 4.0 and later accept either style.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f954a-119">示例</span><span class="sxs-lookup"><span data-stu-id="f954a-119">Example</span></span>

<span data-ttu-id="f954a-120">DOOLEVERB ("edit")</span><span class="sxs-lookup"><span data-stu-id="f954a-120">DOOLEVERB("edit")</span></span>
  
<span data-ttu-id="f954a-121">运行 OLE 对象程序，并显示链接或嵌入的对象，以便进行编辑。</span><span class="sxs-lookup"><span data-stu-id="f954a-121">Runs the OLE object program and displays the linked or embedded object so that it can be edited.</span></span>
  

