---
title: 实现提供程序一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b0dcbfe-6bed-4fb8-a906-009f1d009055
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 99146f93dcf634be6766f5c6fcc0d1c610b84d4d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775792"
---
# <a name="implementing-a-provider-one-off-table"></a><span data-ttu-id="62837-103">实现提供程序一次性表</span><span class="sxs-lookup"><span data-stu-id="62837-103">Implementing a Provider One-Off Table</span></span>

  
  
<span data-ttu-id="62837-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="62837-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="62837-105">MAPI 客户端应用程序的用户将收件人添加到的传出邮件时调用提供商的[IABLogon::GetOneOffTable](iablogon-getoneofftable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="62837-105">MAPI calls your provider's [IABLogon::GetOneOffTable](iablogon-getoneofftable.md) method when the user of a client application adds a recipient to an outgoing message.</span></span> <span data-ttu-id="62837-106">通常情况下，请求的地址的类型是唯一的邮件系统。</span><span class="sxs-lookup"><span data-stu-id="62837-106">Typically, the types of addresses requested are unique to your messaging system.</span></span> <span data-ttu-id="62837-107">如果您的提供商支持收件人的创建，它必须提供一个一次性表，用于公开每种类型的受支持的收件人地址的模板。</span><span class="sxs-lookup"><span data-stu-id="62837-107">If your provider supports recipient creation, it must supply a one-off table that exposes templates for every type of supported recipient address.</span></span> <span data-ttu-id="62837-108">如果您的提供程序不支持收件人的创建，返回 MAPI_E_NO_SUPPORT 从**GetOneOffTable**呼叫。</span><span class="sxs-lookup"><span data-stu-id="62837-108">If your provider does not support recipient creation, return MAPI_E_NO_SUPPORT from the **GetOneOffTable** call.</span></span> 
  
<span data-ttu-id="62837-109">MAPI 通常将您的提供商一次性表保持打开状态的生存期内会话，仅当在客户端调用子系统的时释放其或通讯簿的[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。</span><span class="sxs-lookup"><span data-stu-id="62837-109">MAPI will typically keep your provider's one-off table open for the lifetime of the session, releasing it only when a client calls either the subsystem's or address book's [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> <span data-ttu-id="62837-110">MAPI 注册此表中的通知，以便如果添加或删除模板时，可以向用户反映这些更改。</span><span class="sxs-lookup"><span data-stu-id="62837-110">MAPI registers for notifications on this table so that if templates are added or deleted, these changes can be reflected to the user.</span></span> 
  
 <span data-ttu-id="62837-111">**若要实现 IABLogon::GetOneOffTable**</span><span class="sxs-lookup"><span data-stu-id="62837-111">**To implement IABLogon::GetOneOffTable**</span></span>
  
1. <span data-ttu-id="62837-112">检查的 flags 参数， _ulFlags_值。</span><span class="sxs-lookup"><span data-stu-id="62837-112">Check the value of the flags parameter,  _ulFlags_.</span></span> <span data-ttu-id="62837-113">如果设置了 MAPI_UNICODE 标志，并且您的提供程序不支持 Unicode，失败并返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="62837-113">If the MAPI_UNICODE flag is set and your provider does not support Unicode, fail and return MAPI_E_BAD_CHARWIDTH.</span></span> 
    
2. <span data-ttu-id="62837-114">检查是否已创建提供商的一次性表。</span><span class="sxs-lookup"><span data-stu-id="62837-114">Check if your provider's one-off table has already been created.</span></span> <span data-ttu-id="62837-115">一次性表是通常静态的因为您的提供商从来多次通过创建过程。</span><span class="sxs-lookup"><span data-stu-id="62837-115">Because one-off tables are typically static, your provider never has to go through the creation process more than once.</span></span> <span data-ttu-id="62837-116">如果表格已存在，向其返回一个指针。</span><span class="sxs-lookup"><span data-stu-id="62837-116">If a table already exists, return a pointer to it.</span></span> 
    
3. <span data-ttu-id="62837-117">如果尚不存在一次性表，调用**CreateTable**创建一个。</span><span class="sxs-lookup"><span data-stu-id="62837-117">If a one-off table does not yet exist, call **CreateTable** to create one.</span></span> 
    
4. <span data-ttu-id="62837-118">设置表格行中的列的以下属性：</span><span class="sxs-lookup"><span data-stu-id="62837-118">Set the following properties for the columns in your table rows:</span></span>
    
  - <span data-ttu-id="62837-119">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 模板可以创建的收件人的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="62837-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) to the name of the type of recipient that the template can create.</span></span> 
    
  - <span data-ttu-id="62837-120">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md)) 到一次性模板的项标识符。</span><span class="sxs-lookup"><span data-stu-id="62837-120">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) to the entry identifier for the one-off template.</span></span>
    
  - <span data-ttu-id="62837-121">**PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md)) 指示显示一次性表中的层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="62837-121">**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) to indicate the hierarchy level in the one-off table display.</span></span>
    
  - <span data-ttu-id="62837-122">**PR_SELECTABLE**([PidTagSelectable](pidtagselectable-canonical-property.md)) 为 TRUE 以指示是否该行表示模板和 FALSE 否则。</span><span class="sxs-lookup"><span data-stu-id="62837-122">**PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) to TRUE to indicate if the row represents a template and FALSE otherwise.</span></span>
    
  - <span data-ttu-id="62837-123">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 到由模板创建的地址的类型。</span><span class="sxs-lookup"><span data-stu-id="62837-123">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) to the type of address created by the template.</span></span>
    
  - <span data-ttu-id="62837-124">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 到 DT_MAILUSER 或另一个值，该值指示显示模板的类型。</span><span class="sxs-lookup"><span data-stu-id="62837-124">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) to DT_MAILUSER or another value that indicates the type of display for the template.</span></span>
    
  - <span data-ttu-id="62837-125">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 为唯一的二进制值。</span><span class="sxs-lookup"><span data-stu-id="62837-125">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) to a unique binary value.</span></span> 
    
5. <span data-ttu-id="62837-126">调用[ITableData::HrModifyRow](itabledata-hrmodifyrow.md)直接修改表格。</span><span class="sxs-lookup"><span data-stu-id="62837-126">Call [ITableData::HrModifyRow](itabledata-hrmodifyrow.md) to modify the table directly.</span></span> 
    
6. <span data-ttu-id="62837-127">调用[ITableData::HrGetView](itabledata-hrgetview.md)创建**IMAPITable**接口实现，以返回到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="62837-127">Call [ITableData::HrGetView](itabledata-hrgetview.md) to create an **IMAPITable** interface implementation to return to the caller.</span></span> 
    

