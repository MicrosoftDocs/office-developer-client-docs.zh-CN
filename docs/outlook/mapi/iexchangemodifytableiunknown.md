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
ms.openlocfilehash: 51a83e1e28534cc237419d9c4ae475c1d719c5de
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565072"
---
# <a name="iexchangemodifytable--iunknown"></a><span data-ttu-id="1cc34-103">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1cc34-103">IExchangeModifyTable : IUnknown</span></span>

  
  
<span data-ttu-id="1cc34-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1cc34-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1cc34-105">支持对 Microsoft Exchange Server table 对象的访问，特别是系统访问控制列表 (SACL) table 对象和规则对 Microsoft Exchange Server 文件夹的 table 对象。</span><span class="sxs-lookup"><span data-stu-id="1cc34-105">Supports access to Microsoft Exchange Server table objects, specifically system access control list (SACL) table objects and rule table objects on Microsoft Exchange Server folders.</span></span> <span data-ttu-id="1cc34-106">此接口类似于[IMAPITable: IUnknown](imapitableiunknown.md)界面，但它添加支持用于控制 Sacl 和规则的特定于 Microsoft Exchange 服务器的结构。</span><span class="sxs-lookup"><span data-stu-id="1cc34-106">This interface resembles the [IMAPITable : IUnknown](imapitableiunknown.md) interface, but it adds support for Microsoft Exchange Server-specific structures that are used to control SACLs and rules.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1cc34-107">由公开：</span><span class="sxs-lookup"><span data-stu-id="1cc34-107">Exposed by:</span></span>  <br/> |<span data-ttu-id="1cc34-108">无</span><span class="sxs-lookup"><span data-stu-id="1cc34-108">None</span></span>  <br/> |
|<span data-ttu-id="1cc34-109">通过实现：</span><span class="sxs-lookup"><span data-stu-id="1cc34-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="1cc34-110">服务器 table 对象</span><span class="sxs-lookup"><span data-stu-id="1cc34-110">Server table objects</span></span>  <br/> |
|<span data-ttu-id="1cc34-111">调用：</span><span class="sxs-lookup"><span data-stu-id="1cc34-111">Called by:</span></span>  <br/> |<span data-ttu-id="1cc34-112">MAPI 和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="1cc34-112">MAPI and client applications</span></span>  <br/> |
|<span data-ttu-id="1cc34-113">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="1cc34-113">Interface identifier:</span></span>  <br/> |<span data-ttu-id="1cc34-114">IID_IExchangeModifyTable</span><span class="sxs-lookup"><span data-stu-id="1cc34-114">IID_IExchangeModifyTable</span></span>  <br/> |
|<span data-ttu-id="1cc34-115">指针类型：</span><span class="sxs-lookup"><span data-stu-id="1cc34-115">Pointer type:</span></span>  <br/> |<span data-ttu-id="1cc34-116">LPEXCHANGEMODIFYTABLE</span><span class="sxs-lookup"><span data-stu-id="1cc34-116">LPEXCHANGEMODIFYTABLE</span></span>  <br/> |
|<span data-ttu-id="1cc34-117">事务模型：</span><span class="sxs-lookup"><span data-stu-id="1cc34-117">Transaction model:</span></span>  <br/> |<span data-ttu-id="1cc34-118">事务处理</span><span class="sxs-lookup"><span data-stu-id="1cc34-118">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="1cc34-119">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="1cc34-119">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="1cc34-120">时出错</span><span class="sxs-lookup"><span data-stu-id="1cc34-120">GetLastError</span></span>](iexchangemodifytable-getlasterror.md) <br/> |<span data-ttu-id="1cc34-121">返回一个 table 对象中上次发生的错误有关的信息。</span><span class="sxs-lookup"><span data-stu-id="1cc34-121">Returns information about the last error that occurred in a table object.</span></span>  <br/> |
|[<span data-ttu-id="1cc34-122">GetTable</span><span class="sxs-lookup"><span data-stu-id="1cc34-122">GetTable</span></span>](iexchangemodifytable-gettable.md) <br/> |<span data-ttu-id="1cc34-123">返回一个 MAPI table 对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="1cc34-123">Returns a pointer to an interface for a MAPI table object.</span></span>  <br/> |
|[<span data-ttu-id="1cc34-124">ModifyTable</span><span class="sxs-lookup"><span data-stu-id="1cc34-124">ModifyTable</span></span>](iexchangemodifytable-modifytable.md) <br/> |<span data-ttu-id="1cc34-125">更新 MAPI table 对象。</span><span class="sxs-lookup"><span data-stu-id="1cc34-125">Updates a MAPI table object.</span></span>  <br/> |
   
|<span data-ttu-id="1cc34-126">**用于修改规则表属性**</span><span class="sxs-lookup"><span data-stu-id="1cc34-126">**Properties used to modify a rules table**</span></span>|<span data-ttu-id="1cc34-127">**Access**</span><span class="sxs-lookup"><span data-stu-id="1cc34-127">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1cc34-128">**PR_RULE_ACTIONS**([PidTagRuleActions](pidtagruleactions-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-128">**PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-129">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-129">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-130">**PR_RULE_CONDITION**([PidTagRuleCondition](pidtagrulecondition-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-130">**PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-131">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-131">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-132">**PR_RULE_ID**([PidTagRuleId](pidtagruleid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-132">**PR_RULE_ID** ([PidTagRuleId](pidtagruleid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-133">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-133">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-134">**PR_RULE_LEVEL**([PidTagRuleLevel](pidtagrulelevel-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-134">**PR_RULE_LEVEL** ([PidTagRuleLevel](pidtagrulelevel-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-135">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-135">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-136">**PR_RULE_NAME**([PidTagRuleName](pidtagrulename-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-136">**PR_RULE_NAME** ([PidTagRuleName](pidtagrulename-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-137">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-137">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-138">**PR_RULE_PROVIDER**([PidTagRuleProvider](pidtagruleprovider-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-138">**PR_RULE_PROVIDER** ([PidTagRuleProvider](pidtagruleprovider-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-139">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-139">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-140">**PR_RULE_PROVIDER_DATA**([PidTagRuleProviderData](pidtagruleproviderdata-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-140">**PR_RULE_PROVIDER_DATA** ([PidTagRuleProviderData](pidtagruleproviderdata-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-141">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-141">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-142">**PR_RULE_SEQUENCE**([PidTagRuleSequence](pidtagrulesequence-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-142">**PR_RULE_SEQUENCE** ([PidTagRuleSequence](pidtagrulesequence-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-143">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-143">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-144">**PR_RULE_STATE**([PidTagRuleState](pidtagrulestate-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-144">**PR_RULE_STATE** ([PidTagRuleState](pidtagrulestate-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-145">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-145">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-146">**PR_RULE_USER_FLAGS**([PidTagRuleUserFlags](pidtagruleuserflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-146">**PR_RULE_USER_FLAGS** ([PidTagRuleUserFlags](pidtagruleuserflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-147">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-147">Read-only</span></span>  <br/> |
   
|<span data-ttu-id="1cc34-148">**用于修改 SACL 表属性**</span><span class="sxs-lookup"><span data-stu-id="1cc34-148">**Properties used to modify a SACL table**</span></span>|<span data-ttu-id="1cc34-149">**Access**</span><span class="sxs-lookup"><span data-stu-id="1cc34-149">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1cc34-150">**PR_MEMBER_ENTRYID**([PidTagMemberEntryId](pidtagmemberentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-150">**PR_MEMBER_ENTRYID** ([PidTagMemberEntryId](pidtagmemberentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-151">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-151">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-152">**PR_MEMBER_ID**([PidTagMemberId](pidtagmemberid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-152">**PR_MEMBER_ID** ([PidTagMemberId](pidtagmemberid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-153">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-153">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-154">**PR_MEMBER_NAME**([PidTagMemberName](pidtagmembername-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-154">**PR_MEMBER_NAME** ([PidTagMemberName](pidtagmembername-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-155">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-155">Read-only</span></span>  <br/> |
|<span data-ttu-id="1cc34-156">**PR_MEMBER_RIGHTS**([PidTagMemberRights](pidtagmemberrights-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1cc34-156">**PR_MEMBER_RIGHTS** ([PidTagMemberRights](pidtagmemberrights-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1cc34-157">只读</span><span class="sxs-lookup"><span data-stu-id="1cc34-157">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1cc34-158">注解</span><span class="sxs-lookup"><span data-stu-id="1cc34-158">Remarks</span></span>

<span data-ttu-id="1cc34-159">若要获得**IExchangeModifyTable**接口，调用类型 PT_OBJECT 上一个 folder 对象的属性上的 MAPI [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1cc34-159">To obtain the **IExchangeModifyTable** interface, call the MAPI [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method on a property of type PT_OBJECT on a folder object.</span></span> <span data-ttu-id="1cc34-160">当调用**OpenProperty**方法时，将传递_lpiid_参数中的值**IID_IExchangeModifyTable** 。</span><span class="sxs-lookup"><span data-stu-id="1cc34-160">When you call the **OpenProperty** method, pass the value **IID_IExchangeModifyTable** in the  _lpiid_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1cc34-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cc34-161">See also</span></span>



[<span data-ttu-id="1cc34-162">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="1cc34-162">MAPI Interfaces</span></span>](mapi-interfaces.md)

