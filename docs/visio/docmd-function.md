---
title: DOCMD 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60100
localization_priority: Normal
ms.assetid: 6574edeb-eb6f-afd9-89c4-eb5996dffa30
description: 执行已确定的命令。
ms.openlocfilehash: 9e5c02c9a90f3aab66c5d582c83d7d9d892f964c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413071"
---
# <a name="docmd-function"></a><span data-ttu-id="f53f5-103">DOCMD 函数</span><span class="sxs-lookup"><span data-stu-id="f53f5-103">DOCMD Function</span></span>

<span data-ttu-id="f53f5-104">执行已确定的命令。</span><span class="sxs-lookup"><span data-stu-id="f53f5-104">Performs the identified command.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f53f5-105">语法</span><span class="sxs-lookup"><span data-stu-id="f53f5-105">Syntax</span></span>

 <span data-ttu-id="f53f5-106">**DOCMD**( _commandID_)</span><span class="sxs-lookup"><span data-stu-id="f53f5-106">**DOCMD**( _commandID_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="f53f5-107">参数</span><span class="sxs-lookup"><span data-stu-id="f53f5-107">Parameters</span></span>

|<span data-ttu-id="f53f5-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="f53f5-108">**Name**</span></span>|<span data-ttu-id="f53f5-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f53f5-109">**Required/Optional**</span></span>|<span data-ttu-id="f53f5-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f53f5-110">**Data Type**</span></span>|<span data-ttu-id="f53f5-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f53f5-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f53f5-112">_commandID_</span><span class="sxs-lookup"><span data-stu-id="f53f5-112">_commandID_</span></span> <br/> |<span data-ttu-id="f53f5-113">必需</span><span class="sxs-lookup"><span data-stu-id="f53f5-113">Required</span></span>  <br/> |<span data-ttu-id="f53f5-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="f53f5-114">**Number**</span></span> <br/> | <span data-ttu-id="f53f5-115">要执行的命令。</span><span class="sxs-lookup"><span data-stu-id="f53f5-115">The command to perform.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f53f5-116">说明</span><span class="sxs-lookup"><span data-stu-id="f53f5-116">Remarks</span></span>

<span data-ttu-id="f53f5-117">有关 DOCMD 函数支持的命令的列表, 请参阅 Microsoft Visio 2013 Automation Reference 中的 "DOCMD/DOCMD 命令" 主题。</span><span class="sxs-lookup"><span data-stu-id="f53f5-117">For a list of commands that are supported with the DOCMD function, see the topic "DoCmd/DOCMD commands" in the Microsoft Visio 2013 Automation Reference.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f53f5-118">示例</span><span class="sxs-lookup"><span data-stu-id="f53f5-118">Example</span></span>

 `DOCMD (1312)`
  
<span data-ttu-id="f53f5-119">导致在用户界面中显示 **“形状数据”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="f53f5-119">Causes the **Shape Data** dialog box to appear in the user interface.</span></span> 
  

