---
title: IAttach IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAttach
api_type:
- COM
ms.assetid: f47e20e1-2a30-4c9e-8ca6-e8c5e72f44a1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ce9c8b189991e4102fcc9d17b88747d4ce55efec
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570910"
---
# <a name="iattach--imapiprop"></a><span data-ttu-id="41c81-103">IAttach : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="41c81-103">IAttach : IMAPIProp</span></span>

  
  
<span data-ttu-id="41c81-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="41c81-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="41c81-105">维护并提供对属性的邮件中的附件的访问。</span><span class="sxs-lookup"><span data-stu-id="41c81-105">Maintains and provides access to the properties of attachments in messages.</span></span> <span data-ttu-id="41c81-106">**IAttach**接口都有其自己的方法都不唯一。</span><span class="sxs-lookup"><span data-stu-id="41c81-106">The **IAttach** interface has no unique methods of its own.</span></span> <span data-ttu-id="41c81-107">有关如何使用附件的详细信息，请参阅[MAPI 附件](mapi-attachments.md)和[附件表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="41c81-107">For more information about how to use attachments, see [MAPI Attachments](mapi-attachments.md) and [Attachment Tables](attachment-tables.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="41c81-108">头文件：</span><span class="sxs-lookup"><span data-stu-id="41c81-108">Header file:</span></span>  <br/> |<span data-ttu-id="41c81-109">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="41c81-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="41c81-110">由公开：</span><span class="sxs-lookup"><span data-stu-id="41c81-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="41c81-111">Attachment 对象</span><span class="sxs-lookup"><span data-stu-id="41c81-111">Attachment objects</span></span>  <br/> |
|<span data-ttu-id="41c81-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="41c81-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="41c81-113">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="41c81-113">Message store providers</span></span>  <br/> |
|<span data-ttu-id="41c81-114">调用：</span><span class="sxs-lookup"><span data-stu-id="41c81-114">Called by:</span></span>  <br/> |<span data-ttu-id="41c81-115">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="41c81-115">Client applications</span></span>  <br/> |
|<span data-ttu-id="41c81-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="41c81-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="41c81-117">IID_IAttachment</span><span class="sxs-lookup"><span data-stu-id="41c81-117">IID_IAttachment</span></span>  <br/> |
|<span data-ttu-id="41c81-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="41c81-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="41c81-119">LPATTACH</span><span class="sxs-lookup"><span data-stu-id="41c81-119">LPATTACH</span></span>  <br/> |
|<span data-ttu-id="41c81-120">事务模型：</span><span class="sxs-lookup"><span data-stu-id="41c81-120">Transaction model:</span></span>  <br/> |<span data-ttu-id="41c81-121">事务处理</span><span class="sxs-lookup"><span data-stu-id="41c81-121">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="41c81-122">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="41c81-122">Vtable order</span></span>

<span data-ttu-id="41c81-123">此接口不具有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="41c81-123">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="41c81-124">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="41c81-124">**Required properties**</span></span>|<span data-ttu-id="41c81-125">**Access**</span><span class="sxs-lookup"><span data-stu-id="41c81-125">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="41c81-126">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41c81-126">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41c81-127">只读</span><span class="sxs-lookup"><span data-stu-id="41c81-127">Read-only</span></span>  <br/> |
|<span data-ttu-id="41c81-128">**PR_ATTACH_METHOD**([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41c81-128">**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41c81-129">读/写</span><span class="sxs-lookup"><span data-stu-id="41c81-129">Read/write</span></span>  <br/> |
|<span data-ttu-id="41c81-130">**PR_RENDERING_POSITION**([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41c81-130">**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41c81-131">读/写</span><span class="sxs-lookup"><span data-stu-id="41c81-131">Read/write</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="41c81-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41c81-132">See also</span></span>



[<span data-ttu-id="41c81-133">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="41c81-133">MAPI Interfaces</span></span>](mapi-interfaces.md)

