---
title: IExchangeModifyTable IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IExchangeModifyTable
api_type:
- COM
ms.assetid: 45a73c7b-5855-4b70-866b-facb41cb3c32
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 333e1d5cacc069ee1faef01426a1c0a60ef07f8e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418104"
---
# <a name="iexchangemodifytable--iunknown"></a><span data-ttu-id="b9e48-103">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b9e48-103">IExchangeModifyTable : IUnknown</span></span>

  
  
<span data-ttu-id="b9e48-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9e48-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b9e48-105">支持对 microsoft exchange server 表对象的访问, 特别是系统访问控制列表 (SACL) 表对象和 microsoft exchange server 文件夹中的 rule 表对象。</span><span class="sxs-lookup"><span data-stu-id="b9e48-105">Supports access to Microsoft Exchange Server table objects, specifically system access control list (SACL) table objects and rule table objects on Microsoft Exchange Server folders.</span></span> <span data-ttu-id="b9e48-106">此接口类似于[IMAPITable: IUnknown](imapitableiunknown.md)接口, 但它添加了对用于控制 sacl 和规则的 Microsoft Exchange 服务器特定结构的支持。</span><span class="sxs-lookup"><span data-stu-id="b9e48-106">This interface resembles the [IMAPITable : IUnknown](imapitableiunknown.md) interface, but it adds support for Microsoft Exchange Server-specific structures that are used to control SACLs and rules.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b9e48-107">公开者:</span><span class="sxs-lookup"><span data-stu-id="b9e48-107">Exposed by:</span></span>  <br/> |<span data-ttu-id="b9e48-108">无</span><span class="sxs-lookup"><span data-stu-id="b9e48-108">None</span></span>  <br/> |
|<span data-ttu-id="b9e48-109">实现者：</span><span class="sxs-lookup"><span data-stu-id="b9e48-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="b9e48-110">Server 表对象</span><span class="sxs-lookup"><span data-stu-id="b9e48-110">Server table objects</span></span>  <br/> |
|<span data-ttu-id="b9e48-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="b9e48-111">Called by:</span></span>  <br/> |<span data-ttu-id="b9e48-112">MAPI 和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="b9e48-112">MAPI and client applications</span></span>  <br/> |
|<span data-ttu-id="b9e48-113">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="b9e48-113">Interface identifier:</span></span>  <br/> |<span data-ttu-id="b9e48-114">IID_IExchangeModifyTable</span><span class="sxs-lookup"><span data-stu-id="b9e48-114">IID_IExchangeModifyTable</span></span>  <br/> |
|<span data-ttu-id="b9e48-115">指针类型:</span><span class="sxs-lookup"><span data-stu-id="b9e48-115">Pointer type:</span></span>  <br/> |<span data-ttu-id="b9e48-116">LPEXCHANGEMODIFYTABLE</span><span class="sxs-lookup"><span data-stu-id="b9e48-116">LPEXCHANGEMODIFYTABLE</span></span>  <br/> |
|<span data-ttu-id="b9e48-117">事务模型:</span><span class="sxs-lookup"><span data-stu-id="b9e48-117">Transaction model:</span></span>  <br/> |<span data-ttu-id="b9e48-118">事务</span><span class="sxs-lookup"><span data-stu-id="b9e48-118">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="b9e48-119">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="b9e48-119">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="b9e48-120">GetLastError</span><span class="sxs-lookup"><span data-stu-id="b9e48-120">GetLastError</span></span>](iexchangemodifytable-getlasterror.md) <br/> |<span data-ttu-id="b9e48-121">返回有关在 table 对象中发生的最后一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="b9e48-121">Returns information about the last error that occurred in a table object.</span></span>  <br/> |
|[<span data-ttu-id="b9e48-122">GetTable</span><span class="sxs-lookup"><span data-stu-id="b9e48-122">GetTable</span></span>](iexchangemodifytable-gettable.md) <br/> |<span data-ttu-id="b9e48-123">返回指向 MAPI 表对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b9e48-123">Returns a pointer to an interface for a MAPI table object.</span></span>  <br/> |
|[<span data-ttu-id="b9e48-124">ModifyTable</span><span class="sxs-lookup"><span data-stu-id="b9e48-124">ModifyTable</span></span>](iexchangemodifytable-modifytable.md) <br/> |<span data-ttu-id="b9e48-125">更新 MAPI 表对象。</span><span class="sxs-lookup"><span data-stu-id="b9e48-125">Updates a MAPI table object.</span></span>  <br/> |
   
|<span data-ttu-id="b9e48-126">**用于修改规则表的属性**</span><span class="sxs-lookup"><span data-stu-id="b9e48-126">**Properties used to modify a rules table**</span></span>|<span data-ttu-id="b9e48-127">**访问**</span><span class="sxs-lookup"><span data-stu-id="b9e48-127">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9e48-128">**PR_RULE_ACTIONS**([PidTagRuleActions](pidtagruleactions-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-128">**PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-129">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-129">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-130">**PR_RULE_CONDITION**([PidTagRuleCondition](pidtagrulecondition-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-130">**PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-131">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-131">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-132">**PR_RULE_ID**([PidTagRuleId](pidtagruleid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-132">**PR_RULE_ID** ([PidTagRuleId](pidtagruleid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-133">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-133">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-134">**PR_RULE_LEVEL**([PidTagRuleLevel](pidtagrulelevel-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-134">**PR_RULE_LEVEL** ([PidTagRuleLevel](pidtagrulelevel-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-135">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-135">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-136">**PR_RULE_NAME**([PidTagRuleName](pidtagrulename-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-136">**PR_RULE_NAME** ([PidTagRuleName](pidtagrulename-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-137">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-137">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-138">**PR_RULE_PROVIDER**([PidTagRuleProvider](pidtagruleprovider-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-138">**PR_RULE_PROVIDER** ([PidTagRuleProvider](pidtagruleprovider-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-139">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-139">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-140">**PR_RULE_PROVIDER_DATA**([PidTagRuleProviderData](pidtagruleproviderdata-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-140">**PR_RULE_PROVIDER_DATA** ([PidTagRuleProviderData](pidtagruleproviderdata-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-141">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-141">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-142">**PR_RULE_SEQUENCE**([PidTagRuleSequence](pidtagrulesequence-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-142">**PR_RULE_SEQUENCE** ([PidTagRuleSequence](pidtagrulesequence-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-143">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-143">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-144">**PR_RULE_STATE**([PidTagRuleState](pidtagrulestate-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-144">**PR_RULE_STATE** ([PidTagRuleState](pidtagrulestate-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-145">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-145">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-146">**PR_RULE_USER_FLAGS**([PidTagRuleUserFlags](pidtagruleuserflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-146">**PR_RULE_USER_FLAGS** ([PidTagRuleUserFlags](pidtagruleuserflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-147">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-147">Read-only</span></span>  <br/> |
   
|<span data-ttu-id="b9e48-148">**用于修改 SACL 表的属性**</span><span class="sxs-lookup"><span data-stu-id="b9e48-148">**Properties used to modify a SACL table**</span></span>|<span data-ttu-id="b9e48-149">**访问**</span><span class="sxs-lookup"><span data-stu-id="b9e48-149">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9e48-150">**PR_MEMBER_ENTRYID**([PidTagMemberEntryId](pidtagmemberentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-150">**PR_MEMBER_ENTRYID** ([PidTagMemberEntryId](pidtagmemberentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-151">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-151">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-152">**PR_MEMBER_ID**([PidTagMemberId](pidtagmemberid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-152">**PR_MEMBER_ID** ([PidTagMemberId](pidtagmemberid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-153">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-153">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-154">**PR_MEMBER_NAME**([PidTagMemberName](pidtagmembername-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-154">**PR_MEMBER_NAME** ([PidTagMemberName](pidtagmembername-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-155">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-155">Read-only</span></span>  <br/> |
|<span data-ttu-id="b9e48-156">**PR_MEMBER_RIGHTS**([PidTagMemberRights](pidtagmemberrights-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b9e48-156">**PR_MEMBER_RIGHTS** ([PidTagMemberRights](pidtagmemberrights-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b9e48-157">只读</span><span class="sxs-lookup"><span data-stu-id="b9e48-157">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b9e48-158">说明</span><span class="sxs-lookup"><span data-stu-id="b9e48-158">Remarks</span></span>

<span data-ttu-id="b9e48-159">若要获取**IExchangeModifyTable**接口, 请在 folder 对象上的 PT_OBJECT 类型的属性上调用 MAPI [IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b9e48-159">To obtain the **IExchangeModifyTable** interface, call the MAPI [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method on a property of type PT_OBJECT on a folder object.</span></span> <span data-ttu-id="b9e48-160">调用**OpenProperty**方法时, 请在_lpiid_参数中传递值**IID_IExchangeModifyTable** 。</span><span class="sxs-lookup"><span data-stu-id="b9e48-160">When you call the **OpenProperty** method, pass the value **IID_IExchangeModifyTable** in the  _lpiid_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b9e48-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9e48-161">See also</span></span>



[<span data-ttu-id="b9e48-162">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="b9e48-162">MAPI Interfaces</span></span>](mapi-interfaces.md)

