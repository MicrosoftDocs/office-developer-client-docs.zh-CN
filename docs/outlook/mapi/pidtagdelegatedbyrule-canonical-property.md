---
title: PidTagDelegatedByRule 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDelegatedByRule
api_type:
- HeaderDef
ms.assetid: 284b5001-5de6-4c4e-8e5c-0593ae1b301f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 47458e2468215c6539ad07533c36564d37da8b96
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359917"
---
# <a name="pidtagdelegatedbyrule-canonical-property"></a><span data-ttu-id="f7e93-103">PidTagDelegatedByRule 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7e93-103">PidTagDelegatedByRule Canonical Property</span></span>

  
  
<span data-ttu-id="f7e93-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7e93-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f7e93-105">指示文件夹的邮件是否由规则委派。</span><span class="sxs-lookup"><span data-stu-id="f7e93-105">Indicates whether a folder's message is delegated by a rule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f7e93-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f7e93-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f7e93-107">PR_DELEGATED_BY_RULE</span><span class="sxs-lookup"><span data-stu-id="f7e93-107">PR_DELEGATED_BY_RULE</span></span>  <br/> |
|<span data-ttu-id="f7e93-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f7e93-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f7e93-109">0x3FE3</span><span class="sxs-lookup"><span data-stu-id="f7e93-109">0x3FE3</span></span>  <br/> |
|<span data-ttu-id="f7e93-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f7e93-110">Data type:</span></span>  <br/> |<span data-ttu-id="f7e93-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="f7e93-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="f7e93-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f7e93-112">Area:</span></span>  <br/> |<span data-ttu-id="f7e93-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="f7e93-113">MAPI status</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="f7e93-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="f7e93-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f7e93-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="f7e93-115">Protocol specifications</span></span>

<span data-ttu-id="f7e93-116">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f7e93-116">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f7e93-117">指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="f7e93-117">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="f7e93-118">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f7e93-118">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f7e93-119">在服务器上处理传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f7e93-119">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f7e93-120">头文件</span><span class="sxs-lookup"><span data-stu-id="f7e93-120">Header files</span></span>

<span data-ttu-id="f7e93-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f7e93-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="f7e93-122">提供数据类型定义</span><span class="sxs-lookup"><span data-stu-id="f7e93-122">Provides data type definitions</span></span>
    
<span data-ttu-id="f7e93-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f7e93-123">Mapitags.h</span></span>
  
> <span data-ttu-id="f7e93-124">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f7e93-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f7e93-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7e93-125">See also</span></span>



[<span data-ttu-id="f7e93-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f7e93-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f7e93-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7e93-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f7e93-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f7e93-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f7e93-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f7e93-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

