---
title: PidNameAudioNotes 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameAudioNotes
api_type:
- COM
ms.assetid: aec4d328-c192-4672-a478-b08442352794
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 188ddf13e623292e95a1af4af54cf4254d7b0345
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360905"
---
# <a name="pidnameaudionotes-canonical-property"></a><span data-ttu-id="7dc9c-103">PidNameAudioNotes 规范属性</span><span class="sxs-lookup"><span data-stu-id="7dc9c-103">PidNameAudioNotes Canonical Property</span></span>

  
  
<span data-ttu-id="7dc9c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7dc9c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7dc9c-105">指定附加到语音邮件的文本注释。</span><span class="sxs-lookup"><span data-stu-id="7dc9c-105">Specifies the textual notes that are attached to a voice message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7dc9c-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="7dc9c-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="7dc9c-107">UMAudioNotes</span><span class="sxs-lookup"><span data-stu-id="7dc9c-107">UMAudioNotes</span></span>  <br/> |
|<span data-ttu-id="7dc9c-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="7dc9c-108">Property set:</span></span>  <br/> |<span data-ttu-id="7dc9c-109">PSETID_UnifiedMessaging</span><span class="sxs-lookup"><span data-stu-id="7dc9c-109">PSETID_UnifiedMessaging</span></span>  <br/> |
|<span data-ttu-id="7dc9c-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="7dc9c-110">Property name:</span></span>  <br/> |<span data-ttu-id="7dc9c-111">UMAudioNotes</span><span class="sxs-lookup"><span data-stu-id="7dc9c-111">UMAudioNotes</span></span>  <br/> |
|<span data-ttu-id="7dc9c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7dc9c-112">Data type:</span></span>  <br/> |<span data-ttu-id="7dc9c-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7dc9c-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7dc9c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7dc9c-114">Area:</span></span>  <br/> |<span data-ttu-id="7dc9c-115">统一消息</span><span class="sxs-lookup"><span data-stu-id="7dc9c-115">Unified messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7dc9c-116">备注</span><span class="sxs-lookup"><span data-stu-id="7dc9c-116">Remarks</span></span>

<span data-ttu-id="7dc9c-117">为了允许最终用户直接在语音邮件上读取和编辑音频笔记，客户端提供了一个编辑框，用户可以在编辑框中键入添加到语音邮件对象的此属性的一组注释。</span><span class="sxs-lookup"><span data-stu-id="7dc9c-117">To enable an end user to read and edit audio notes directly on a voice message, a client provides an edit box where the user can type a set of notes that are added to this property of the voice message object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7dc9c-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7dc9c-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7dc9c-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="7dc9c-119">Protocol specifications</span></span>

<span data-ttu-id="7dc9c-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7dc9c-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7dc9c-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="7dc9c-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7dc9c-122">[[MS-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7dc9c-122">[[MS-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7dc9c-123">指定允许用于表示语音邮件和传真邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="7dc9c-123">Specifies the properties and operations that are permissible for representing voice mail and fax messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7dc9c-124">头文件</span><span class="sxs-lookup"><span data-stu-id="7dc9c-124">Header files</span></span>

<span data-ttu-id="7dc9c-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7dc9c-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="7dc9c-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7dc9c-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7dc9c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7dc9c-127">See also</span></span>



[<span data-ttu-id="7dc9c-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7dc9c-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7dc9c-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7dc9c-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7dc9c-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7dc9c-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7dc9c-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7dc9c-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

