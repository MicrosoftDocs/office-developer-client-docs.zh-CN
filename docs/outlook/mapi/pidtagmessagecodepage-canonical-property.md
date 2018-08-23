---
title: PidTagMessageCodepage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageCodepage
api_type:
- HeaderDef
ms.assetid: eef73e34-470c-4c37-94ce-ea95fe83bc10
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f75a5e10a59d7c6db4e43d2552a38d523b537790
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580199"
---
# <a name="pidtagmessagecodepage-canonical-property"></a><span data-ttu-id="5268c-103">PidTagMessageCodepage 规范属性</span><span class="sxs-lookup"><span data-stu-id="5268c-103">PidTagMessageCodepage Canonical Property</span></span>

  
  
<span data-ttu-id="5268c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5268c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5268c-105">包含用于消息的代码页。</span><span class="sxs-lookup"><span data-stu-id="5268c-105">Contains the code page that is used for the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5268c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5268c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5268c-107">PR_MESSAGE_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="5268c-107">PR_MESSAGE_CODEPAGE</span></span>  <br/> |
|<span data-ttu-id="5268c-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="5268c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5268c-109">0x3FFD</span><span class="sxs-lookup"><span data-stu-id="5268c-109">0x3FFD</span></span>  <br/> |
|<span data-ttu-id="5268c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5268c-110">Data type:</span></span>  <br/> |<span data-ttu-id="5268c-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="5268c-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="5268c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5268c-112">Area:</span></span>  <br/> |<span data-ttu-id="5268c-113">Common</span><span class="sxs-lookup"><span data-stu-id="5268c-113">Common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5268c-114">注解</span><span class="sxs-lookup"><span data-stu-id="5268c-114">Remarks</span></span>

<span data-ttu-id="5268c-115">如果此属性设置为零 (0)，则使用的文件夹对象代码页。</span><span class="sxs-lookup"><span data-stu-id="5268c-115">The folder object code page is used if this property is set to zero (0).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5268c-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="5268c-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5268c-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="5268c-117">Protocol specifications</span></span>

<span data-ttu-id="5268c-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5268c-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5268c-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="5268c-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5268c-120">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5268c-120">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5268c-121">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="5268c-121">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="5268c-122">[[MS OXPFOAB]](http://msdn.microsoft.com/library/258a07a7-34a7-4373-87c1-cddf51447d00%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5268c-122">[[MS-OXPFOAB]](http://msdn.microsoft.com/library/258a07a7-34a7-4373-87c1-cddf51447d00%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5268c-123">指定从服务器的脱机通讯簿 (OAB) 数据交付给客户端的方法。</span><span class="sxs-lookup"><span data-stu-id="5268c-123">Specifies the method of delivering offline address book (OAB) data from server to client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5268c-124">头文件</span><span class="sxs-lookup"><span data-stu-id="5268c-124">Header files</span></span>

<span data-ttu-id="5268c-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5268c-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="5268c-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5268c-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="5268c-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5268c-127">Mapitags.h</span></span>
  
> <span data-ttu-id="5268c-128">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5268c-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5268c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5268c-129">See also</span></span>



[<span data-ttu-id="5268c-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5268c-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5268c-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5268c-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5268c-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5268c-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5268c-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5268c-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

