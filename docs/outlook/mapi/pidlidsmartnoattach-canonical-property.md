---
title: PidLidSmartNoAttach 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSmartNoAttach
api_type:
- COM
ms.assetid: 60299c1b-1b46-4c3a-8fb9-a2b4d3383aac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 43e10652a7dccdf0da6592df0f9fc2daf5ea9bee
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777035"
---
# <a name="pidlidsmartnoattach-canonical-property"></a><span data-ttu-id="1df4d-103">PidLidSmartNoAttach 规范属性</span><span class="sxs-lookup"><span data-stu-id="1df4d-103">PidLidSmartNoAttach Canonical Property</span></span>

  
  
<span data-ttu-id="1df4d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1df4d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1df4d-105">代表是否被视为上一条消息的附件为隐藏。</span><span class="sxs-lookup"><span data-stu-id="1df4d-105">Represents whether the attachments on a message are considered as hidden.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1df4d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1df4d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1df4d-107">dispidSmartNoAttach</span><span class="sxs-lookup"><span data-stu-id="1df4d-107">dispidSmartNoAttach</span></span>  <br/> |
|<span data-ttu-id="1df4d-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="1df4d-108">Property set:</span></span>  <br/> |<span data-ttu-id="1df4d-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="1df4d-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="1df4d-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="1df4d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="1df4d-111">0x00008514</span><span class="sxs-lookup"><span data-stu-id="1df4d-111">0x00008514</span></span>  <br/> |
|<span data-ttu-id="1df4d-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1df4d-112">Data type:</span></span>  <br/> |<span data-ttu-id="1df4d-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="1df4d-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="1df4d-114">区域：</span><span class="sxs-lookup"><span data-stu-id="1df4d-114">Area:</span></span>  <br/> |<span data-ttu-id="1df4d-115">运行时配置</span><span class="sxs-lookup"><span data-stu-id="1df4d-115">Run-time configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1df4d-116">说明</span><span class="sxs-lookup"><span data-stu-id="1df4d-116">Remarks</span></span>

<span data-ttu-id="1df4d-117">此属性为 TRUE，如果邮件的附件被视为为隐藏。</span><span class="sxs-lookup"><span data-stu-id="1df4d-117">This property is TRUE if the attachments of the message are considered as hidden.</span></span>
  
<span data-ttu-id="1df4d-118">表示消息对象是否有任何最终用户可见附件。</span><span class="sxs-lookup"><span data-stu-id="1df4d-118">It indicates whether the message object has no end-user visible attachments.</span></span> <span data-ttu-id="1df4d-119">此属性可能未设置;如果是这样，则假定的默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1df4d-119">This property may be unset; if so, a default value of FALSE is assumed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1df4d-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="1df4d-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1df4d-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="1df4d-121">Protocol specifications</span></span>

<span data-ttu-id="1df4d-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1df4d-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1df4d-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="1df4d-123">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1df4d-124">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1df4d-124">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1df4d-125">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="1df4d-125">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1df4d-126">头文件</span><span class="sxs-lookup"><span data-stu-id="1df4d-126">Header files</span></span>

<span data-ttu-id="1df4d-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1df4d-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="1df4d-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1df4d-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1df4d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1df4d-129">See also</span></span>



[<span data-ttu-id="1df4d-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1df4d-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1df4d-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1df4d-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1df4d-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1df4d-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1df4d-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1df4d-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

