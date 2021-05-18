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
ms.openlocfilehash: 2ef3bc973e12bd5630cc00b3c512b748d4a16e86
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409088"
---
# <a name="iattach--imapiprop"></a><span data-ttu-id="21d6a-103">IAttach : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="21d6a-103">IAttach : IMAPIProp</span></span>

  
  
<span data-ttu-id="21d6a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="21d6a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="21d6a-105">维护和提供对邮件中附件属性的访问权限。</span><span class="sxs-lookup"><span data-stu-id="21d6a-105">Maintains and provides access to the properties of attachments in messages.</span></span> <span data-ttu-id="21d6a-106">**IAttach** 接口没有其自己的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="21d6a-106">The **IAttach** interface has no unique methods of its own.</span></span> <span data-ttu-id="21d6a-107">有关如何使用附件的信息，请参阅[MAPI Attachments](mapi-attachments.md) and [Attachment Tables。](attachment-tables.md)</span><span class="sxs-lookup"><span data-stu-id="21d6a-107">For more information about how to use attachments, see [MAPI Attachments](mapi-attachments.md) and [Attachment Tables](attachment-tables.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="21d6a-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="21d6a-108">Header file:</span></span>  <br/> |<span data-ttu-id="21d6a-109">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="21d6a-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="21d6a-110">公开者：</span><span class="sxs-lookup"><span data-stu-id="21d6a-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="21d6a-111">Attachment 对象</span><span class="sxs-lookup"><span data-stu-id="21d6a-111">Attachment objects</span></span>  <br/> |
|<span data-ttu-id="21d6a-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="21d6a-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="21d6a-113">邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="21d6a-113">Message store providers</span></span>  <br/> |
|<span data-ttu-id="21d6a-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="21d6a-114">Called by:</span></span>  <br/> |<span data-ttu-id="21d6a-115">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="21d6a-115">Client applications</span></span>  <br/> |
|<span data-ttu-id="21d6a-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="21d6a-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="21d6a-117">IID_IAttachment</span><span class="sxs-lookup"><span data-stu-id="21d6a-117">IID_IAttachment</span></span>  <br/> |
|<span data-ttu-id="21d6a-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="21d6a-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="21d6a-119">LPATTACH</span><span class="sxs-lookup"><span data-stu-id="21d6a-119">LPATTACH</span></span>  <br/> |
|<span data-ttu-id="21d6a-120">事务模型：</span><span class="sxs-lookup"><span data-stu-id="21d6a-120">Transaction model:</span></span>  <br/> |<span data-ttu-id="21d6a-121">Transacted</span><span class="sxs-lookup"><span data-stu-id="21d6a-121">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="21d6a-122">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="21d6a-122">Vtable order</span></span>

<span data-ttu-id="21d6a-123">此接口没有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="21d6a-123">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="21d6a-124">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="21d6a-124">**Required properties**</span></span>|<span data-ttu-id="21d6a-125">**Access**</span><span class="sxs-lookup"><span data-stu-id="21d6a-125">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="21d6a-126">**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="21d6a-126">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="21d6a-127">只读</span><span class="sxs-lookup"><span data-stu-id="21d6a-127">Read-only</span></span>  <br/> |
|<span data-ttu-id="21d6a-128">**PR_ATTACH_METHOD (** [PidTagAttachMethod)](pidtagattachmethod-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="21d6a-128">**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="21d6a-129">读/写</span><span class="sxs-lookup"><span data-stu-id="21d6a-129">Read/write</span></span>  <br/> |
|<span data-ttu-id="21d6a-130">**PR_RENDERING_POSITION (** [PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="21d6a-130">**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="21d6a-131">读/写</span><span class="sxs-lookup"><span data-stu-id="21d6a-131">Read/write</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="21d6a-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21d6a-132">See also</span></span>



[<span data-ttu-id="21d6a-133">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="21d6a-133">MAPI Interfaces</span></span>](mapi-interfaces.md)

