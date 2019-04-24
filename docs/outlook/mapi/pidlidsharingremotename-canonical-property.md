---
title: PidLidSharingRemoteName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingRemoteName
api_type:
- COM
ms.assetid: be975f74-4b95-45a4-bbee-959fa8e4ad45
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3be288b606e197b350c1b053303077c1cb984e9c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303092"
---
# <a name="pidlidsharingremotename-canonical-property"></a><span data-ttu-id="08e2c-103">PidLidSharingRemoteName 规范属性</span><span class="sxs-lookup"><span data-stu-id="08e2c-103">PidLidSharingRemoteName Canonical Property</span></span>

  
  
<span data-ttu-id="08e2c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="08e2c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="08e2c-105">指定要共享的远程文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="08e2c-105">Specifies the name of the remote folder that is being shared.</span></span> <span data-ttu-id="08e2c-106">这是共享邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="08e2c-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="08e2c-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="08e2c-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="08e2c-108">dispidSharingRemoteName</span><span class="sxs-lookup"><span data-stu-id="08e2c-108">dispidSharingRemoteName</span></span>  <br/> |
|<span data-ttu-id="08e2c-109">属性集:</span><span class="sxs-lookup"><span data-stu-id="08e2c-109">Property set:</span></span>  <br/> |<span data-ttu-id="08e2c-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="08e2c-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="08e2c-111">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="08e2c-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="08e2c-112">0x00008A05</span><span class="sxs-lookup"><span data-stu-id="08e2c-112">0x00008A05</span></span>  <br/> |
|<span data-ttu-id="08e2c-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="08e2c-113">Data type:</span></span>  <br/> |<span data-ttu-id="08e2c-114">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="08e2c-114">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="08e2c-115">区域：</span><span class="sxs-lookup"><span data-stu-id="08e2c-115">Area:</span></span>  <br/> |<span data-ttu-id="08e2c-116">共享</span><span class="sxs-lookup"><span data-stu-id="08e2c-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="08e2c-117">注解</span><span class="sxs-lookup"><span data-stu-id="08e2c-117">Remarks</span></span>

<span data-ttu-id="08e2c-118">此属性必须设置为要共享的文件夹上的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="08e2c-118">This property must be set to the value of the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property on the folder being shared.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="08e2c-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="08e2c-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="08e2c-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="08e2c-120">Protocol specifications</span></span>

<span data-ttu-id="08e2c-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08e2c-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08e2c-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="08e2c-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="08e2c-123">[[毫秒-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08e2c-123">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08e2c-124">在客户端之间共享邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="08e2c-124">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="08e2c-125">头文件</span><span class="sxs-lookup"><span data-stu-id="08e2c-125">Header files</span></span>

<span data-ttu-id="08e2c-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="08e2c-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="08e2c-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="08e2c-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="08e2c-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08e2c-128">See also</span></span>



[<span data-ttu-id="08e2c-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="08e2c-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="08e2c-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="08e2c-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="08e2c-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="08e2c-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="08e2c-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="08e2c-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

