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
ms.openlocfilehash: ca54b749b764e9ea2c7db71d41268303542417f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780899"
---
# <a name="playsound-function"></a><span data-ttu-id="68643-103">PLAYSOUND 函数</span><span class="sxs-lookup"><span data-stu-id="68643-103">PLAYSOUND Function</span></span>

<span data-ttu-id="68643-104">播放声音文件或系统声音。</span><span class="sxs-lookup"><span data-stu-id="68643-104">Plays a sound file or system sound.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="68643-105">语法</span><span class="sxs-lookup"><span data-stu-id="68643-105">Syntax</span></span>

<span data-ttu-id="68643-106">PLAYSOUND ("* * *filename* * *"|"* **别名** *"，* * *isAlias* * *，* **嘟嘟声** *，* **同步** *)</span><span class="sxs-lookup"><span data-stu-id="68643-106">PLAYSOUND(" ** *filename* ** "|" ** *alias* ** ", ** *isAlias* **, ** *beep* **, ** *synch* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="68643-107">参数</span><span class="sxs-lookup"><span data-stu-id="68643-107">Parameters</span></span>

|<span data-ttu-id="68643-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="68643-108">**Name**</span></span>|<span data-ttu-id="68643-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="68643-109">**Required/Optional**</span></span>|<span data-ttu-id="68643-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="68643-110">**Data Type**</span></span>|<span data-ttu-id="68643-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="68643-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="68643-112">_文件名_</span><span class="sxs-lookup"><span data-stu-id="68643-112">_filename_</span></span> <br/> |<span data-ttu-id="68643-113">必需</span><span class="sxs-lookup"><span data-stu-id="68643-113">Required</span></span>  <br/> |<span data-ttu-id="68643-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="68643-114">**String**</span></span> <br/> |<span data-ttu-id="68643-115">要播放的声音文件的名称。</span><span class="sxs-lookup"><span data-stu-id="68643-115">The name of the sound file you want to play.</span></span>  <br/> |
| <span data-ttu-id="68643-116">_alias_</span><span class="sxs-lookup"><span data-stu-id="68643-116">_alias_</span></span> <br/> |<span data-ttu-id="68643-117">必需</span><span class="sxs-lookup"><span data-stu-id="68643-117">Required</span></span>  <br/> |<span data-ttu-id="68643-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="68643-118">**String**</span></span> <br/> | <span data-ttu-id="68643-119">由别名表示的系统声音。</span><span class="sxs-lookup"><span data-stu-id="68643-119">A system sound represented by an alias.</span></span>  <br/> |
| <span data-ttu-id="68643-120">_isAlias_</span><span class="sxs-lookup"><span data-stu-id="68643-120">_isAlias_</span></span> <br/> |<span data-ttu-id="68643-121">必需</span><span class="sxs-lookup"><span data-stu-id="68643-121">Required</span></span>  <br/> |<span data-ttu-id="68643-122">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="68643-122">**Boolean**</span></span> <br/> | <span data-ttu-id="68643-123">指定前面的表达式是别名还是文件名；使用非零值来指定别名。</span><span class="sxs-lookup"><span data-stu-id="68643-123">Specifies whether the preceding expression is an alias or file name; use a non-zero value to specify an alias.</span></span>  <br/> |
| <span data-ttu-id="68643-124">_beep_</span><span class="sxs-lookup"><span data-stu-id="68643-124">_beep_</span></span> <br/> |<span data-ttu-id="68643-125">必需</span><span class="sxs-lookup"><span data-stu-id="68643-125">Required</span></span>  <br/> |<span data-ttu-id="68643-126">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="68643-126">**Boolean**</span></span> <br/> |<span data-ttu-id="68643-127">指定在声音无法播放时，Microsoft Visio 是否发出嘟嘟声；使用非零数字来指定发出嘟嘟声。</span><span class="sxs-lookup"><span data-stu-id="68643-127">Specifies whether Microsoft Visio beeps when sound can't be played; use a non-zero number to beep.</span></span>  <br/> |
| <span data-ttu-id="68643-128">_同步_</span><span class="sxs-lookup"><span data-stu-id="68643-128">_synch_</span></span> <br/> |<span data-ttu-id="68643-129">必需</span><span class="sxs-lookup"><span data-stu-id="68643-129">Required</span></span>  <br/> |<span data-ttu-id="68643-130">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="68643-130">**Boolean**</span></span> <br/> |<span data-ttu-id="68643-131">确定是异步 (0) 播放声音还是同步 (1) 播放声音。</span><span class="sxs-lookup"><span data-stu-id="68643-131">Determines whether sounds are played asynchronously (0) or synchronously (1).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="68643-132">注解</span><span class="sxs-lookup"><span data-stu-id="68643-132">Remarks</span></span>

<span data-ttu-id="68643-p101">通常应异步播放声音，这样 Visio 就能够在播放声音的同时继续进行处理。若要将几种声音组合在一起，请同步播放它们，否则一些声音可能无法播放。
</span><span class="sxs-lookup"><span data-stu-id="68643-p101">You should usually play sounds asynchronously so that Visio can continue processing while it plays the sound. To string several sounds together, play them synchronously, or some might fail to play.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="68643-135">示例 1</span><span class="sxs-lookup"><span data-stu-id="68643-135">Example 1</span></span>

<span data-ttu-id="68643-136">PLAYSOUND("chord.wav", 0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="68643-136">PLAYSOUND("chord.wav", 0, 0, 0)</span></span>
  
<span data-ttu-id="68643-137">无警告嘟嘟声，异步播放音频文件 chord.wav。</span><span class="sxs-lookup"><span data-stu-id="68643-137">Plays the wave audio file chord.wav asynchronously with no warning beep.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="68643-138">示例 2</span><span class="sxs-lookup"><span data-stu-id="68643-138">Example 2</span></span>

<span data-ttu-id="68643-139">PLAYSOUND("SystemExclamation", 1, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="68643-139">PLAYSOUND("SystemExclamation", 1, 0, 0)</span></span>
  
<span data-ttu-id="68643-140">无警告嘟嘟声，异步播放系统感叹声。</span><span class="sxs-lookup"><span data-stu-id="68643-140">Plays the system exclamation sound asynchronously with no warning beep.</span></span>
  

