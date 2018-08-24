---
title: IAttachmentSecurity IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAttachmentSecurity
api_type:
- COM
ms.assetid: 69609f73-5884-9e2b-ab78-a2e0ece3a1d1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f182610f9cf4874cc18c409960e1f8b23f853d4f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574823"
---
# <a name="iattachmentsecurity--iunknown"></a><span data-ttu-id="dc64f-103">IAttachmentSecurity : IUnknown</span><span class="sxs-lookup"><span data-stu-id="dc64f-103">IAttachmentSecurity : IUnknown</span></span>

  
  
<span data-ttu-id="dc64f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dc64f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dc64f-105">允许 Microsoft Outlook 2010 和 Microsoft Outlook 2013 的解决方案，以找出是否附件被视为不安全的和阻止的查看和编制索引。</span><span class="sxs-lookup"><span data-stu-id="dc64f-105">Allows Microsoft Outlook 2010 and Microsoft Outlook 2013 solutions to find out if an attachment is considered unsafe and blocked for viewing and indexing.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dc64f-106">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="dc64f-106">Interface identifier:</span></span>  <br/> |<span data-ttu-id="dc64f-107">IID_IAttachmentSecurity</span><span class="sxs-lookup"><span data-stu-id="dc64f-107">IID_IAttachmentSecurity</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="dc64f-108">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="dc64f-108">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="dc64f-109">IAttachmentSecurity::IsAttachmentBlocked</span><span class="sxs-lookup"><span data-stu-id="dc64f-109">IAttachmentSecurity::IsAttachmentBlocked</span></span>](iattachmentsecurity-isattachmentblocked.md) <br/> |<span data-ttu-id="dc64f-110">检查是否指定的附件阻止通过 Outlook 2010 或 Outlook 2013 的查看和编制索引。</span><span class="sxs-lookup"><span data-stu-id="dc64f-110">Checks if a specified attachment is blocked by Outlook 2010 or Outlook 2013 for viewing and indexing.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dc64f-111">注解</span><span class="sxs-lookup"><span data-stu-id="dc64f-111">Remarks</span></span>

<span data-ttu-id="dc64f-112">Outlook 2010 和 Outlook 2013 解决方案可以查询以确定是否阻止附件此接口。</span><span class="sxs-lookup"><span data-stu-id="dc64f-112">Outlook 2010 and Outlook 2013 solutions can query this interface to see if an attachment is blocked.</span></span> <span data-ttu-id="dc64f-113">Outlook 2010 或 Outlook 2013 被阻止的附件取决于已如何配置 Outlook 2010 或 Outlook 2013 和管理员已应用策略。</span><span class="sxs-lookup"><span data-stu-id="dc64f-113">The attachments that are blocked by Outlook 2010 or Outlook 2013 vary depending on how Outlook 2010 or Outlook 2013 has been configured and the policies that an administrator has applied.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc64f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc64f-114">See also</span></span>



[<span data-ttu-id="dc64f-115">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="dc64f-115">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="dc64f-116">验证附件是否已遭阻止</span><span class="sxs-lookup"><span data-stu-id="dc64f-116">Verify an Attachment is Blocked</span></span>](how-to-verify-an-attachment-is-blocked.md)

