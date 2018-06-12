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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 9635c06ffa5638e370312e3b2b29e0c98161a766
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777766"
---
# <a name="pidtagipmsubtreeentryid-canonical-property"></a><span data-ttu-id="fd327-103">PidTagIpmSubtreeEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd327-103">PidTagIpmSubtreeEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="fd327-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fd327-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fd327-105">包含消息存储库文件夹树中的人际邮件 (IPM) 文件夹子树的根的项标识符。</span><span class="sxs-lookup"><span data-stu-id="fd327-105">Contains the entry identifier of the root of the interpersonal message (IPM) folder subtree in the message store's folder tree.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fd327-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="fd327-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fd327-107">PR_IPM_SUBTREE_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="fd327-107">PR_IPM_SUBTREE_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="fd327-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="fd327-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fd327-109">0x35E0</span><span class="sxs-lookup"><span data-stu-id="fd327-109">0x35E0</span></span>  <br/> |
|<span data-ttu-id="fd327-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fd327-110">Data type:</span></span>  <br/> |<span data-ttu-id="fd327-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="fd327-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="fd327-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fd327-112">Area:</span></span>  <br/> |<span data-ttu-id="fd327-113">Folder</span><span class="sxs-lookup"><span data-stu-id="fd327-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fd327-114">备注</span><span class="sxs-lookup"><span data-stu-id="fd327-114">Remarks</span></span>

<span data-ttu-id="fd327-115">此属性表示 IPM 层次结构的根。</span><span class="sxs-lookup"><span data-stu-id="fd327-115">This property represents the root of the IPM hierarchy.</span></span> <span data-ttu-id="fd327-116">IPM 客户端不应显示不支持此属性表示的文件夹的子文件夹的任何文件夹。</span><span class="sxs-lookup"><span data-stu-id="fd327-116">IPM clients should not display any folders that are not subfolders of the folder represented by this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fd327-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="fd327-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="fd327-118">头文件</span><span class="sxs-lookup"><span data-stu-id="fd327-118">Header files</span></span>

<span data-ttu-id="fd327-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fd327-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="fd327-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fd327-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="fd327-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fd327-121">Mapitags.h</span></span>
  
> <span data-ttu-id="fd327-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fd327-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fd327-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd327-123">See also</span></span>



[<span data-ttu-id="fd327-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fd327-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fd327-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd327-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fd327-126">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fd327-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fd327-127">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fd327-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

