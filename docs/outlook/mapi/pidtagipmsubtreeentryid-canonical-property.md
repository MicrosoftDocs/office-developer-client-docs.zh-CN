---
title: PidTagIpmSubtreeEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmSubtreeEntryId
api_type:
- HeaderDef
ms.assetid: 5763fc78-5192-4162-be27-4aadc7ed65bc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 815685696dfc93bb6241f608ca0157e87e758e7b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412728"
---
# <a name="pidtagipmsubtreeentryid-canonical-property"></a><span data-ttu-id="05118-103">PidTagIpmSubtreeEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="05118-103">PidTagIpmSubtreeEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="05118-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="05118-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="05118-105">包含邮件存储的文件夹树中人际邮件 (IPM) 文件夹子树的根的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="05118-105">Contains the entry identifier of the root of the interpersonal message (IPM) folder subtree in the message store's folder tree.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="05118-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="05118-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="05118-107">PR_IPM_SUBTREE_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="05118-107">PR_IPM_SUBTREE_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="05118-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="05118-108">Identifier:</span></span>  <br/> |<span data-ttu-id="05118-109">0x35E0</span><span class="sxs-lookup"><span data-stu-id="05118-109">0x35E0</span></span>  <br/> |
|<span data-ttu-id="05118-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="05118-110">Data type:</span></span>  <br/> |<span data-ttu-id="05118-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="05118-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="05118-112">区域：</span><span class="sxs-lookup"><span data-stu-id="05118-112">Area:</span></span>  <br/> |<span data-ttu-id="05118-113">Folder</span><span class="sxs-lookup"><span data-stu-id="05118-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="05118-114">说明</span><span class="sxs-lookup"><span data-stu-id="05118-114">Remarks</span></span>

<span data-ttu-id="05118-115">此属性表示 IPM 层次结构的根。</span><span class="sxs-lookup"><span data-stu-id="05118-115">This property represents the root of the IPM hierarchy.</span></span> <span data-ttu-id="05118-116">IPM 客户端不应显示此属性所代表的文件夹的子文件夹的任何文件夹。</span><span class="sxs-lookup"><span data-stu-id="05118-116">IPM clients should not display any folders that are not subfolders of the folder represented by this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="05118-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="05118-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="05118-118">头文件</span><span class="sxs-lookup"><span data-stu-id="05118-118">Header files</span></span>

<span data-ttu-id="05118-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="05118-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="05118-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="05118-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="05118-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="05118-121">Mapitags.h</span></span>
  
> <span data-ttu-id="05118-122">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="05118-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="05118-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05118-123">See also</span></span>



[<span data-ttu-id="05118-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="05118-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="05118-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="05118-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="05118-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="05118-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="05118-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="05118-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

