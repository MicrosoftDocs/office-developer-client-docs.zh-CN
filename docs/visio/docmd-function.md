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
description: 执行标识的命令。
ms.openlocfilehash: e425dd9605c18d4647787c5df7aeaa4fd5f9e4cd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780114"
---
# <a name="docmd-function"></a><span data-ttu-id="1f7ca-103">DOCMD 函数</span><span class="sxs-lookup"><span data-stu-id="1f7ca-103">DOCMD Function</span></span>

<span data-ttu-id="1f7ca-104">执行标识的命令。</span><span class="sxs-lookup"><span data-stu-id="1f7ca-104">Performs the identified command.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1f7ca-105">语法</span><span class="sxs-lookup"><span data-stu-id="1f7ca-105">Syntax</span></span>

 <span data-ttu-id="1f7ca-106">**DOCMD**( _commandID_)</span><span class="sxs-lookup"><span data-stu-id="1f7ca-106">**DOCMD**( _commandID_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="1f7ca-107">参数</span><span class="sxs-lookup"><span data-stu-id="1f7ca-107">Parameters</span></span>

|<span data-ttu-id="1f7ca-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="1f7ca-108">**Name**</span></span>|<span data-ttu-id="1f7ca-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1f7ca-109">**Required/Optional**</span></span>|<span data-ttu-id="1f7ca-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1f7ca-110">**Data Type**</span></span>|<span data-ttu-id="1f7ca-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="1f7ca-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1f7ca-112">_commandID_</span><span class="sxs-lookup"><span data-stu-id="1f7ca-112">_commandID_</span></span> <br/> |<span data-ttu-id="1f7ca-113">必需</span><span class="sxs-lookup"><span data-stu-id="1f7ca-113">Required</span></span>  <br/> |<span data-ttu-id="1f7ca-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="1f7ca-114">**Number**</span></span> <br/> | <span data-ttu-id="1f7ca-115">要执行的命令。</span><span class="sxs-lookup"><span data-stu-id="1f7ca-115">The command to perform.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f7ca-116">注解</span><span class="sxs-lookup"><span data-stu-id="1f7ca-116">Remarks</span></span>

<span data-ttu-id="1f7ca-117">DOCMD 函数所支持的命令的列表，请参阅主题的 Microsoft Visio 2013 Automation 参考中的"DoCmd/DOCMD 命令"。</span><span class="sxs-lookup"><span data-stu-id="1f7ca-117">For a list of commands that are supported with the DOCMD function, see the topic "DoCmd/DOCMD commands" in the Microsoft Visio 2013 Automation Reference.</span></span> 
  
## <a name="example"></a><span data-ttu-id="1f7ca-118">示例</span><span class="sxs-lookup"><span data-stu-id="1f7ca-118">Example</span></span>

 `DOCMD (1312)`
  
<span data-ttu-id="1f7ca-119">使**形状数据**对话框中，在用户界面中显示。</span><span class="sxs-lookup"><span data-stu-id="1f7ca-119">Causes the **Shape Data** dialog box to appear in the user interface.</span></span> 
  

