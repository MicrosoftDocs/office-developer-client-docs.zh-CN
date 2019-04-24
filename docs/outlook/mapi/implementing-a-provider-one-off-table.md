---
title: 实现提供程序一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b0dcbfe-6bed-4fb8-a906-009f1d009055
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 023686702b76b5b29acf4304fcfdb3377e8cfcff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332863"
---
# <a name="implementing-a-provider-one-off-table"></a><span data-ttu-id="748b6-103">实现提供程序一次性表</span><span class="sxs-lookup"><span data-stu-id="748b6-103">Implementing a Provider One-Off Table</span></span>

  
  
<span data-ttu-id="748b6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="748b6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="748b6-105">当客户端应用程序的用户向传出的邮件中添加收件人时, MAPI 将调用提供程序的[IABLogon:: GetOneOffTable](iablogon-getoneofftable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="748b6-105">MAPI calls your provider's [IABLogon::GetOneOffTable](iablogon-getoneofftable.md) method when the user of a client application adds a recipient to an outgoing message.</span></span> <span data-ttu-id="748b6-106">通常情况下, 请求的地址类型对您的邮件系统是唯一的。</span><span class="sxs-lookup"><span data-stu-id="748b6-106">Typically, the types of addresses requested are unique to your messaging system.</span></span> <span data-ttu-id="748b6-107">如果您的提供商支持收件人创建, 则必须提供一个一次性表格, 以显示每种类型的受支持收件人地址的模板。</span><span class="sxs-lookup"><span data-stu-id="748b6-107">If your provider supports recipient creation, it must supply a one-off table that exposes templates for every type of supported recipient address.</span></span> <span data-ttu-id="748b6-108">如果您的提供商不支持收件人创建, 请从**GetOneOffTable**调用返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="748b6-108">If your provider does not support recipient creation, return MAPI_E_NO_SUPPORT from the **GetOneOffTable** call.</span></span> 
  
<span data-ttu-id="748b6-109">MAPI 通常会使提供程序的一次性表在会话生存期间处于打开状态, 仅当客户端调用子系统或通讯簿的[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法时, 才会释放此表。</span><span class="sxs-lookup"><span data-stu-id="748b6-109">MAPI will typically keep your provider's one-off table open for the lifetime of the session, releasing it only when a client calls either the subsystem's or address book's [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> <span data-ttu-id="748b6-110">此表上的通知的 MAPI 寄存器, 以便在添加或删除模板时, 可以向用户反映这些更改。</span><span class="sxs-lookup"><span data-stu-id="748b6-110">MAPI registers for notifications on this table so that if templates are added or deleted, these changes can be reflected to the user.</span></span> 
  
 <span data-ttu-id="748b6-111">**实现 IABLogon:: GetOneOffTable**</span><span class="sxs-lookup"><span data-stu-id="748b6-111">**To implement IABLogon::GetOneOffTable**</span></span>
  
1. <span data-ttu-id="748b6-112">检查 flags 参数的值_ulFlags_。</span><span class="sxs-lookup"><span data-stu-id="748b6-112">Check the value of the flags parameter,  _ulFlags_.</span></span> <span data-ttu-id="748b6-113">如果设置了 MAPI_UNICODE 标志, 并且您的提供程序不支持 UNICODE, 则失败并返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="748b6-113">If the MAPI_UNICODE flag is set and your provider does not support Unicode, fail and return MAPI_E_BAD_CHARWIDTH.</span></span> 
    
2. <span data-ttu-id="748b6-114">检查是否已创建提供商的一次性表。</span><span class="sxs-lookup"><span data-stu-id="748b6-114">Check if your provider's one-off table has already been created.</span></span> <span data-ttu-id="748b6-115">由于一次性表通常是静态的, 因此提供程序永远不需要经过一次创建过程。</span><span class="sxs-lookup"><span data-stu-id="748b6-115">Because one-off tables are typically static, your provider never has to go through the creation process more than once.</span></span> <span data-ttu-id="748b6-116">如果表已存在, 则返回指向它的指针。</span><span class="sxs-lookup"><span data-stu-id="748b6-116">If a table already exists, return a pointer to it.</span></span> 
    
3. <span data-ttu-id="748b6-117">如果尚不存在一个一次性表, 请调用**CreateTable**以创建一个。</span><span class="sxs-lookup"><span data-stu-id="748b6-117">If a one-off table does not yet exist, call **CreateTable** to create one.</span></span> 
    
4. <span data-ttu-id="748b6-118">为表格行中的列设置以下属性:</span><span class="sxs-lookup"><span data-stu-id="748b6-118">Set the following properties for the columns in your table rows:</span></span>
    
  - <span data-ttu-id="748b6-119">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 到模板可以创建的收件人类型的名称。</span><span class="sxs-lookup"><span data-stu-id="748b6-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) to the name of the type of recipient that the template can create.</span></span> 
    
  - <span data-ttu-id="748b6-120">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md)) 到一次性模板的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="748b6-120">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) to the entry identifier for the one-off template.</span></span>
    
  - <span data-ttu-id="748b6-121">**PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md)), 用于指示一次性表格显示中的层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="748b6-121">**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) to indicate the hierarchy level in the one-off table display.</span></span>
    
  - <span data-ttu-id="748b6-122">**PR_SELECTABLE**([PidTagSelectable](pidtagselectable-canonical-property.md)) 设置为 TRUE, 以指示该行是否表示模板, 否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="748b6-122">**PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) to TRUE to indicate if the row represents a template and FALSE otherwise.</span></span>
    
  - <span data-ttu-id="748b6-123">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 到模板创建的地址的类型。</span><span class="sxs-lookup"><span data-stu-id="748b6-123">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) to the type of address created by the template.</span></span>
    
  - <span data-ttu-id="748b6-124">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 到 DT_MAILUSER 或另一个指示模板的显示类型的值。</span><span class="sxs-lookup"><span data-stu-id="748b6-124">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) to DT_MAILUSER or another value that indicates the type of display for the template.</span></span>
    
  - <span data-ttu-id="748b6-125">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 到一个唯一的二进制值。</span><span class="sxs-lookup"><span data-stu-id="748b6-125">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) to a unique binary value.</span></span> 
    
5. <span data-ttu-id="748b6-126">调用[ITableData:: HrModifyRow](itabledata-hrmodifyrow.md)以直接修改表。</span><span class="sxs-lookup"><span data-stu-id="748b6-126">Call [ITableData::HrModifyRow](itabledata-hrmodifyrow.md) to modify the table directly.</span></span> 
    
6. <span data-ttu-id="748b6-127">调用[ITableData:: HrGetView](itabledata-hrgetview.md)以创建**IMAPITable**接口实现以返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="748b6-127">Call [ITableData::HrGetView](itabledata-hrgetview.md) to create an **IMAPITable** interface implementation to return to the caller.</span></span> 
    

