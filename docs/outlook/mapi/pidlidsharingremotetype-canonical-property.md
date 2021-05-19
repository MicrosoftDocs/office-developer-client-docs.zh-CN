---
title: PidLidSharingRemoteType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingRemoteType
api_type:
- COM
ms.assetid: e9bc7c7c-86df-45d8-922b-76e3b076144a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3297ca951097c9f3601086809c6e294854c88656
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331206"
---
# <a name="pidlidsharingremotetype-canonical-property"></a><span data-ttu-id="1f95a-103">PidLidSharingRemoteType 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f95a-103">PidLidSharingRemoteType Canonical Property</span></span>

  
  
<span data-ttu-id="1f95a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f95a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f95a-105">指定远程共享文件夹的类型。</span><span class="sxs-lookup"><span data-stu-id="1f95a-105">Specifies the type of the remote shared folder.</span></span> <span data-ttu-id="1f95a-106">这是共享邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="1f95a-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1f95a-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1f95a-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="1f95a-108">dispidSharingRemoteType</span><span class="sxs-lookup"><span data-stu-id="1f95a-108">dispidSharingRemoteType</span></span>  <br/> |
|<span data-ttu-id="1f95a-109">属性集：</span><span class="sxs-lookup"><span data-stu-id="1f95a-109">Property set:</span></span>  <br/> |<span data-ttu-id="1f95a-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="1f95a-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="1f95a-111">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="1f95a-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="1f95a-112">0x00008A1D</span><span class="sxs-lookup"><span data-stu-id="1f95a-112">0x00008A1D</span></span>  <br/> |
|<span data-ttu-id="1f95a-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1f95a-113">Data type:</span></span>  <br/> |<span data-ttu-id="1f95a-114">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1f95a-114">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="1f95a-115">区域：</span><span class="sxs-lookup"><span data-stu-id="1f95a-115">Area:</span></span>  <br/> |<span data-ttu-id="1f95a-116">共享</span><span class="sxs-lookup"><span data-stu-id="1f95a-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f95a-117">备注</span><span class="sxs-lookup"><span data-stu-id="1f95a-117">Remarks</span></span>

<span data-ttu-id="1f95a-118">此属性必须设置为 **与 dispidSharingLocalType** ([PidLidSharingLocalType](pidlidsharinglocaltype-canonical-property.md)) 相同的值，并且应忽略。</span><span class="sxs-lookup"><span data-stu-id="1f95a-118">This property must be set to the same value as the **dispidSharingLocalType** ([PidLidSharingLocalType](pidlidsharinglocaltype-canonical-property.md)) property and should be ignored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1f95a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="1f95a-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1f95a-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="1f95a-120">Protocol specifications</span></span>

<span data-ttu-id="1f95a-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1f95a-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1f95a-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="1f95a-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1f95a-123">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1f95a-123">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1f95a-124">在客户端之间共享邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f95a-124">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1f95a-125">头文件</span><span class="sxs-lookup"><span data-stu-id="1f95a-125">Header files</span></span>

<span data-ttu-id="1f95a-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1f95a-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="1f95a-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1f95a-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1f95a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f95a-128">See also</span></span>



[<span data-ttu-id="1f95a-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1f95a-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1f95a-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f95a-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1f95a-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1f95a-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1f95a-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1f95a-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

