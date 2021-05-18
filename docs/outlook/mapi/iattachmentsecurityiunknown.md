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
ms.openlocfilehash: a8464c8265ebc1754f7909be5413620e7f76db5f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411412"
---
# <a name="iattachmentsecurity--iunknown"></a><span data-ttu-id="b66a3-103">IAttachmentSecurity : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b66a3-103">IAttachmentSecurity : IUnknown</span></span>

  
  
<span data-ttu-id="b66a3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b66a3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b66a3-105">允许Microsoft Outlook 2010和Microsoft Outlook 2013解决方案，以查明附件是否被视为不安全且被阻止查看和编制索引。</span><span class="sxs-lookup"><span data-stu-id="b66a3-105">Allows Microsoft Outlook 2010 and Microsoft Outlook 2013 solutions to find out if an attachment is considered unsafe and blocked for viewing and indexing.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b66a3-106">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="b66a3-106">Interface identifier:</span></span>  <br/> |<span data-ttu-id="b66a3-107">IID_IAttachmentSecurity</span><span class="sxs-lookup"><span data-stu-id="b66a3-107">IID_IAttachmentSecurity</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="b66a3-108">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="b66a3-108">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="b66a3-109">IAttachmentSecurity::IsAttachmentBlocked</span><span class="sxs-lookup"><span data-stu-id="b66a3-109">IAttachmentSecurity::IsAttachmentBlocked</span></span>](iattachmentsecurity-isattachmentblocked.md) <br/> |<span data-ttu-id="b66a3-110">检查指定的附件是否被 2010 Outlook 2013 Outlook 2013 阻止查看和编制索引。</span><span class="sxs-lookup"><span data-stu-id="b66a3-110">Checks if a specified attachment is blocked by Outlook 2010 or Outlook 2013 for viewing and indexing.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b66a3-111">备注</span><span class="sxs-lookup"><span data-stu-id="b66a3-111">Remarks</span></span>

<span data-ttu-id="b66a3-112">Outlook 2010 Outlook 2013 解决方案可以查询此接口以查看附件是否被阻止。</span><span class="sxs-lookup"><span data-stu-id="b66a3-112">Outlook 2010 and Outlook 2013 solutions can query this interface to see if an attachment is blocked.</span></span> <span data-ttu-id="b66a3-113">Outlook 2010 或 Outlook 2013 阻止的附件因 Outlook 2010 或 Outlook 2013 的配置方式以及管理员应用的策略而异。</span><span class="sxs-lookup"><span data-stu-id="b66a3-113">The attachments that are blocked by Outlook 2010 or Outlook 2013 vary depending on how Outlook 2010 or Outlook 2013 has been configured and the policies that an administrator has applied.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b66a3-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b66a3-114">See also</span></span>



[<span data-ttu-id="b66a3-115">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="b66a3-115">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="b66a3-116">验证附件被阻止</span><span class="sxs-lookup"><span data-stu-id="b66a3-116">Verify an Attachment is Blocked</span></span>](how-to-verify-an-attachment-is-blocked.md)

