---
title: 实现提供程序One-Off表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b0dcbfe-6bed-4fb8-a906-009f1d009055
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 023686702b76b5b29acf4304fcfdb3377e8cfcff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436291"
---
# <a name="implementing-a-provider-one-off-table"></a><span data-ttu-id="63a47-103">实现提供程序One-Off表</span><span class="sxs-lookup"><span data-stu-id="63a47-103">Implementing a Provider One-Off Table</span></span>

  
  
<span data-ttu-id="63a47-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="63a47-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="63a47-105">当客户端应用程序的用户向传出邮件添加收件人时，MAPI 将调用提供程序的 [IABLogon：：GetOneOffTable](iablogon-getoneofftable.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="63a47-105">MAPI calls your provider's [IABLogon::GetOneOffTable](iablogon-getoneofftable.md) method when the user of a client application adds a recipient to an outgoing message.</span></span> <span data-ttu-id="63a47-106">通常，请求的地址类型对邮件系统是唯一的。</span><span class="sxs-lookup"><span data-stu-id="63a47-106">Typically, the types of addresses requested are unique to your messaging system.</span></span> <span data-ttu-id="63a47-107">如果您的提供程序支持收件人创建，则它必须提供一个一次表，用于公开每种类型的受支持收件人地址的模板。</span><span class="sxs-lookup"><span data-stu-id="63a47-107">If your provider supports recipient creation, it must supply a one-off table that exposes templates for every type of supported recipient address.</span></span> <span data-ttu-id="63a47-108">如果您的提供程序不支持创建收件人，请从 **GetOneOffTable** MAPI_E_NO_SUPPORT返回一个收件人。</span><span class="sxs-lookup"><span data-stu-id="63a47-108">If your provider does not support recipient creation, return MAPI_E_NO_SUPPORT from the **GetOneOffTable** call.</span></span> 
  
<span data-ttu-id="63a47-109">MAPI 通常会在会话的生存期内保持提供程序的一对一表为打开状态，仅在客户端调用子系统或通讯簿的 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法时释放它。</span><span class="sxs-lookup"><span data-stu-id="63a47-109">MAPI will typically keep your provider's one-off table open for the lifetime of the session, releasing it only when a client calls either the subsystem's or address book's [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> <span data-ttu-id="63a47-110">MAPI 在此表上注册通知，以便添加或删除模板时，这些更改可以反映给用户。</span><span class="sxs-lookup"><span data-stu-id="63a47-110">MAPI registers for notifications on this table so that if templates are added or deleted, these changes can be reflected to the user.</span></span> 
  
 <span data-ttu-id="63a47-111">**实现 IABLogon：：GetOneOffTable**</span><span class="sxs-lookup"><span data-stu-id="63a47-111">**To implement IABLogon::GetOneOffTable**</span></span>
  
1. <span data-ttu-id="63a47-112">检查 flags 参数  _ulFlags 的值_。</span><span class="sxs-lookup"><span data-stu-id="63a47-112">Check the value of the flags parameter,  _ulFlags_.</span></span> <span data-ttu-id="63a47-113">如果已MAPI_UNICODE，并且您的提供程序不支持 Unicode，则失败并返回MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="63a47-113">If the MAPI_UNICODE flag is set and your provider does not support Unicode, fail and return MAPI_E_BAD_CHARWIDTH.</span></span> 
    
2. <span data-ttu-id="63a47-114">检查是否已创建提供程序的一对一表。</span><span class="sxs-lookup"><span data-stu-id="63a47-114">Check if your provider's one-off table has already been created.</span></span> <span data-ttu-id="63a47-115">由于一键式表通常是静态的，因此提供程序绝不会多次完成创建过程。</span><span class="sxs-lookup"><span data-stu-id="63a47-115">Because one-off tables are typically static, your provider never has to go through the creation process more than once.</span></span> <span data-ttu-id="63a47-116">如果表已存在，则返回指向它的指针。</span><span class="sxs-lookup"><span data-stu-id="63a47-116">If a table already exists, return a pointer to it.</span></span> 
    
3. <span data-ttu-id="63a47-117">如果一对一表尚不存在，请调用 **CreateTable** 创建一个。</span><span class="sxs-lookup"><span data-stu-id="63a47-117">If a one-off table does not yet exist, call **CreateTable** to create one.</span></span> 
    
4. <span data-ttu-id="63a47-118">为表行中的列设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="63a47-118">Set the following properties for the columns in your table rows:</span></span>
    
  - <span data-ttu-id="63a47-119">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 模板可以创建的收件人类型的名称。</span><span class="sxs-lookup"><span data-stu-id="63a47-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) to the name of the type of recipient that the template can create.</span></span> 
    
  - <span data-ttu-id="63a47-120">**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) 一次模板的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="63a47-120">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) to the entry identifier for the one-off template.</span></span>
    
  - <span data-ttu-id="63a47-121">**PR_DEPTH (** [PidTagDepth](pidtagdepth-canonical-property.md)) 来指示一次表显示中的层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="63a47-121">**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) to indicate the hierarchy level in the one-off table display.</span></span>
    
  - <span data-ttu-id="63a47-122">**PR_SELECTABLE (** [PidTagSelectable](pidtagselectable-canonical-property.md)) 为 TRUE，以指示该行是否表示模板，否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="63a47-122">**PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) to TRUE to indicate if the row represents a template and FALSE otherwise.</span></span>
    
  - <span data-ttu-id="63a47-123">**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 模板创建的地址类型。</span><span class="sxs-lookup"><span data-stu-id="63a47-123">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) to the type of address created by the template.</span></span>
    
  - <span data-ttu-id="63a47-124">**PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) DT_MAILUSER或指示模板的显示类型的其他值。</span><span class="sxs-lookup"><span data-stu-id="63a47-124">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) to DT_MAILUSER or another value that indicates the type of display for the template.</span></span>
    
  - <span data-ttu-id="63a47-125">**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 一个唯一的二进制值。</span><span class="sxs-lookup"><span data-stu-id="63a47-125">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) to a unique binary value.</span></span> 
    
5. <span data-ttu-id="63a47-126">调用 [ITableData：：HrModifyRow](itabledata-hrmodifyrow.md) 以直接修改表。</span><span class="sxs-lookup"><span data-stu-id="63a47-126">Call [ITableData::HrModifyRow](itabledata-hrmodifyrow.md) to modify the table directly.</span></span> 
    
6. <span data-ttu-id="63a47-127">调用 [ITableData：：HrGetView](itabledata-hrgetview.md) 以创建 **IMAPITable** 接口实现以返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="63a47-127">Call [ITableData::HrGetView](itabledata-hrgetview.md) to create an **IMAPITable** interface implementation to return to the caller.</span></span> 
    

