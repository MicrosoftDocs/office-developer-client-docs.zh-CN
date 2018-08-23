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
ms.openlocfilehash: ade74b13811445c39c73f778b6de49b67b59093b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587556"
---
# <a name="pidtagipmsubtreeentryid-canonical-property"></a><span data-ttu-id="0c46c-103">PidTagIpmSubtreeEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="0c46c-103">PidTagIpmSubtreeEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="0c46c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0c46c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0c46c-105">包含消息存储库文件夹树中的人际邮件 (IPM) 文件夹子树的根的项标识符。</span><span class="sxs-lookup"><span data-stu-id="0c46c-105">Contains the entry identifier of the root of the interpersonal message (IPM) folder subtree in the message store's folder tree.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0c46c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0c46c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0c46c-107">PR_IPM_SUBTREE_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="0c46c-107">PR_IPM_SUBTREE_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="0c46c-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="0c46c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0c46c-109">0x35E0</span><span class="sxs-lookup"><span data-stu-id="0c46c-109">0x35E0</span></span>  <br/> |
|<span data-ttu-id="0c46c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0c46c-110">Data type:</span></span>  <br/> |<span data-ttu-id="0c46c-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="0c46c-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="0c46c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0c46c-112">Area:</span></span>  <br/> |<span data-ttu-id="0c46c-113">Folder</span><span class="sxs-lookup"><span data-stu-id="0c46c-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0c46c-114">注解</span><span class="sxs-lookup"><span data-stu-id="0c46c-114">Remarks</span></span>

<span data-ttu-id="0c46c-115">此属性表示 IPM 层次结构的根。</span><span class="sxs-lookup"><span data-stu-id="0c46c-115">This property represents the root of the IPM hierarchy.</span></span> <span data-ttu-id="0c46c-116">IPM 客户端不应显示不支持此属性表示的文件夹的子文件夹的任何文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c46c-116">IPM clients should not display any folders that are not subfolders of the folder represented by this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0c46c-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="0c46c-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0c46c-118">头文件</span><span class="sxs-lookup"><span data-stu-id="0c46c-118">Header files</span></span>

<span data-ttu-id="0c46c-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0c46c-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="0c46c-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0c46c-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="0c46c-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0c46c-121">Mapitags.h</span></span>
  
> <span data-ttu-id="0c46c-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0c46c-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0c46c-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c46c-123">See also</span></span>



[<span data-ttu-id="0c46c-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0c46c-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0c46c-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0c46c-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0c46c-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0c46c-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0c46c-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0c46c-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

