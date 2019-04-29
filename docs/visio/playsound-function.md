---
title: PLAYSOUND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251479
localization_priority: Normal
ms.assetid: 098d216f-e699-0e74-f702-ccfa7809c19b
description: 播放声音文件或系统声音。
ms.openlocfilehash: 752412aab6584d2b01235fe88644e3ec3fa5daee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435836"
---
# <a name="playsound-function"></a><span data-ttu-id="83b7e-103">PLAYSOUND 函数</span><span class="sxs-lookup"><span data-stu-id="83b7e-103">PLAYSOUND Function</span></span>

<span data-ttu-id="83b7e-104">播放声音文件或系统声音。</span><span class="sxs-lookup"><span data-stu-id="83b7e-104">Plays a sound file or system sound.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="83b7e-105">语法</span><span class="sxs-lookup"><span data-stu-id="83b7e-105">Syntax</span></span>

<span data-ttu-id="83b7e-106">PLAYSOUND ("\* \* *filename* \* *" | "* \* *alias* \* \*", \* \* *isAlias* \* \*, \* **提示音** \*, \* \* *synch* \* \*)</span><span class="sxs-lookup"><span data-stu-id="83b7e-106">PLAYSOUND(" \*\* *filename* \*\* "|" \*\* *alias* \*\* ", \*\* *isAlias* \*\*, \*\* *beep* \*\*, \*\* *synch* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="83b7e-107">参数</span><span class="sxs-lookup"><span data-stu-id="83b7e-107">Parameters</span></span>

|<span data-ttu-id="83b7e-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="83b7e-108">**Name**</span></span>|<span data-ttu-id="83b7e-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="83b7e-109">**Required/Optional**</span></span>|<span data-ttu-id="83b7e-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="83b7e-110">**Data Type**</span></span>|<span data-ttu-id="83b7e-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="83b7e-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="83b7e-112">_filename_</span><span class="sxs-lookup"><span data-stu-id="83b7e-112">_filename_</span></span> <br/> |<span data-ttu-id="83b7e-113">必需</span><span class="sxs-lookup"><span data-stu-id="83b7e-113">Required</span></span>  <br/> |<span data-ttu-id="83b7e-114">**String**</span><span class="sxs-lookup"><span data-stu-id="83b7e-114">**String**</span></span> <br/> |<span data-ttu-id="83b7e-115">要播放的声音文件的名称。</span><span class="sxs-lookup"><span data-stu-id="83b7e-115">The name of the sound file you want to play.</span></span>  <br/> |
| <span data-ttu-id="83b7e-116">_alias_</span><span class="sxs-lookup"><span data-stu-id="83b7e-116">_alias_</span></span> <br/> |<span data-ttu-id="83b7e-117">必需</span><span class="sxs-lookup"><span data-stu-id="83b7e-117">Required</span></span>  <br/> |<span data-ttu-id="83b7e-118">**String**</span><span class="sxs-lookup"><span data-stu-id="83b7e-118">**String**</span></span> <br/> | <span data-ttu-id="83b7e-119">由别名表示的系统声音。</span><span class="sxs-lookup"><span data-stu-id="83b7e-119">A system sound represented by an alias.</span></span>  <br/> |
| <span data-ttu-id="83b7e-120">_isAlias_</span><span class="sxs-lookup"><span data-stu-id="83b7e-120">_isAlias_</span></span> <br/> |<span data-ttu-id="83b7e-121">必需</span><span class="sxs-lookup"><span data-stu-id="83b7e-121">Required</span></span>  <br/> |<span data-ttu-id="83b7e-122">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="83b7e-122">**Boolean**</span></span> <br/> | <span data-ttu-id="83b7e-123">指定前面的表达式是别名还是文件名；使用非零值来指定别名。</span><span class="sxs-lookup"><span data-stu-id="83b7e-123">Specifies whether the preceding expression is an alias or file name; use a non-zero value to specify an alias.</span></span>  <br/> |
| <span data-ttu-id="83b7e-124">_发声_</span><span class="sxs-lookup"><span data-stu-id="83b7e-124">_beep_</span></span> <br/> |<span data-ttu-id="83b7e-125">必需</span><span class="sxs-lookup"><span data-stu-id="83b7e-125">Required</span></span>  <br/> |<span data-ttu-id="83b7e-126">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="83b7e-126">**Boolean**</span></span> <br/> |<span data-ttu-id="83b7e-127">指定在声音无法播放时，Microsoft Visio 是否发出嘟嘟声；使用非零数字来指定发出嘟嘟声。</span><span class="sxs-lookup"><span data-stu-id="83b7e-127">Specifies whether Microsoft Visio beeps when sound can't be played; use a non-zero number to beep.</span></span>  <br/> |
| <span data-ttu-id="83b7e-128">_同步_</span><span class="sxs-lookup"><span data-stu-id="83b7e-128">_synch_</span></span> <br/> |<span data-ttu-id="83b7e-129">必需</span><span class="sxs-lookup"><span data-stu-id="83b7e-129">Required</span></span>  <br/> |<span data-ttu-id="83b7e-130">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="83b7e-130">**Boolean**</span></span> <br/> |<span data-ttu-id="83b7e-131">确定是异步 (0) 播放声音还是同步 (1) 播放声音。</span><span class="sxs-lookup"><span data-stu-id="83b7e-131">Determines whether sounds are played asynchronously (0) or synchronously (1).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="83b7e-132">说明</span><span class="sxs-lookup"><span data-stu-id="83b7e-132">Remarks</span></span>

<span data-ttu-id="83b7e-133">通常应异步播放声音，这样 Visio 就能够在播放声音的同时继续进行处理。</span><span class="sxs-lookup"><span data-stu-id="83b7e-133">You should usually play sounds asynchronously so that Visio can continue processing while it plays the sound.</span></span> <span data-ttu-id="83b7e-134">若要将几种声音组合在一起，请同步播放它们，否则一些声音可能无法播放。</span><span class="sxs-lookup"><span data-stu-id="83b7e-134">To string several sounds together, play them synchronously, or some might fail to play.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="83b7e-135">示例 1</span><span class="sxs-lookup"><span data-stu-id="83b7e-135">Example 1</span></span>

<span data-ttu-id="83b7e-136">PLAYSOUND("chord.wav", 0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="83b7e-136">PLAYSOUND("chord.wav", 0, 0, 0)</span></span>
  
<span data-ttu-id="83b7e-137">无警告嘟嘟声，异步播放音频文件 chord.wav。</span><span class="sxs-lookup"><span data-stu-id="83b7e-137">Plays the wave audio file chord.wav asynchronously with no warning beep.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="83b7e-138">示例 2</span><span class="sxs-lookup"><span data-stu-id="83b7e-138">Example 2</span></span>

<span data-ttu-id="83b7e-139">PLAYSOUND("SystemExclamation", 1, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="83b7e-139">PLAYSOUND("SystemExclamation", 1, 0, 0)</span></span>
  
<span data-ttu-id="83b7e-140">无警告嘟嘟声，异步播放系统感叹声。</span><span class="sxs-lookup"><span data-stu-id="83b7e-140">Plays the system exclamation sound asynchronously with no warning beep.</span></span>
  

