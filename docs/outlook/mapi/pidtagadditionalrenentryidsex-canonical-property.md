---
title: PidTagAdditionalRenEntryIdsEx 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAdditionalRenEntryIdsEx
api_type:
- HeaderDef
ms.assetid: b5e896e7-c0c6-4ad1-bf91-9daba3a1e4d4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 57ab68d4c53693c769a4aadf8737f57ef5e73fcd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335201"
---
# <a name="pidtagadditionalrenentryidsex-canonical-property"></a><span data-ttu-id="07dac-103">PidTagAdditionalRenEntryIdsEx 规范属性</span><span class="sxs-lookup"><span data-stu-id="07dac-103">PidTagAdditionalRenEntryIdsEx Canonical Property</span></span>

  
  
<span data-ttu-id="07dac-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="07dac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="07dac-105">包含 store 对象的特殊文件夹条目 id。</span><span class="sxs-lookup"><span data-stu-id="07dac-105">Contains special folder entry IDs for a store object.</span></span> <span data-ttu-id="07dac-106">此多值属性中的每个条目都可以映射到一个或多个条目 id, 也就是说, 条目与其关联的条目 id 之间存在一对多关系。</span><span class="sxs-lookup"><span data-stu-id="07dac-106">Each entry in this multi-valued property can be mapped to one or more entry IDs, that is, there is a one-to-many relationship between an entry and its associated entry IDs.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="07dac-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="07dac-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="07dac-108">PR_ADDITIONAL_REN_ENTRYIDS_EX</span><span class="sxs-lookup"><span data-stu-id="07dac-108">PR_ADDITIONAL_REN_ENTRYIDS_EX</span></span>  <br/> |
|<span data-ttu-id="07dac-109">标识符:</span><span class="sxs-lookup"><span data-stu-id="07dac-109">Identifier:</span></span>  <br/> |<span data-ttu-id="07dac-110">0x36D9</span><span class="sxs-lookup"><span data-stu-id="07dac-110">0x36D9</span></span>  <br/> |
|<span data-ttu-id="07dac-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="07dac-111">Data type:</span></span>  <br/> |<span data-ttu-id="07dac-112">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="07dac-112">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="07dac-113">区域：</span><span class="sxs-lookup"><span data-stu-id="07dac-113">Area:</span></span>  <br/> |<span data-ttu-id="07dac-114">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="07dac-114">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="07dac-115">注解</span><span class="sxs-lookup"><span data-stu-id="07dac-115">Remarks</span></span>

<span data-ttu-id="07dac-116">如果使用此属性, 则它包含指定文件夹的条目 id 的一组块。</span><span class="sxs-lookup"><span data-stu-id="07dac-116">If this property is used, it contains an array of blocks that specifies the entry IDs for the folders.</span></span> <span data-ttu-id="07dac-117">这些块遵循以下四个表指定的格式。</span><span class="sxs-lookup"><span data-stu-id="07dac-117">The blocks follow the format specified by the following four tables.</span></span>
  
<span data-ttu-id="07dac-118">**PersistData 块**</span><span class="sxs-lookup"><span data-stu-id="07dac-118">**PersistData Block**</span></span>

|<span data-ttu-id="07dac-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="07dac-119">**Name**</span></span>|<span data-ttu-id="07dac-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="07dac-120">**Type**</span></span>|<span data-ttu-id="07dac-121">**Size**</span><span class="sxs-lookup"><span data-stu-id="07dac-121">**Size**</span></span>|<span data-ttu-id="07dac-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="07dac-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07dac-123">**PersistID**</span><span class="sxs-lookup"><span data-stu-id="07dac-123">**PersistID**</span></span> <br/> |<span data-ttu-id="07dac-124">WORD</span><span class="sxs-lookup"><span data-stu-id="07dac-124">WORD</span></span>  <br/> |<span data-ttu-id="07dac-125">双面</span><span class="sxs-lookup"><span data-stu-id="07dac-125">2</span></span>  <br/> |<span data-ttu-id="07dac-126">此**PersistData**条目的类型标识符值。</span><span class="sxs-lookup"><span data-stu-id="07dac-126">Type identifier value for this **PersistData** entry.</span></span> <span data-ttu-id="07dac-127">有关有效值的列表, 请参阅 "PersistBlockType Values" 表。</span><span class="sxs-lookup"><span data-stu-id="07dac-127">See the "PersistBlockType Values" table for the list of valid values.</span></span>  <br/> |
|<span data-ttu-id="07dac-128">**DataElementsSize**</span><span class="sxs-lookup"><span data-stu-id="07dac-128">**DataElementsSize**</span></span> <br/> |<span data-ttu-id="07dac-129">WORD</span><span class="sxs-lookup"><span data-stu-id="07dac-129">WORD</span></span>  <br/> |<span data-ttu-id="07dac-130">双面</span><span class="sxs-lookup"><span data-stu-id="07dac-130">2</span></span>  <br/> |<span data-ttu-id="07dac-131">**DataElements**字段的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="07dac-131">Size, in bytes, of the **DataElements** field.</span></span>  <br/> |
|<span data-ttu-id="07dac-132">**DataElements**</span><span class="sxs-lookup"><span data-stu-id="07dac-132">**DataElements**</span></span> <br/> |<span data-ttu-id="07dac-133">**PersistElement**块的数组</span><span class="sxs-lookup"><span data-stu-id="07dac-133">array of **PersistElement** blocks</span></span>  <br/> |<span data-ttu-id="07dac-134">变量</span><span class="sxs-lookup"><span data-stu-id="07dac-134">variable</span></span>  <br/> |<span data-ttu-id="07dac-135">指示存储区中存在的**PersistElement**条目的数量。</span><span class="sxs-lookup"><span data-stu-id="07dac-135">Indicates how many **PersistElement** entries exist for the store.</span></span> <span data-ttu-id="07dac-136">有关此结构的格式, 请参阅 "PersistElement Block" 表。</span><span class="sxs-lookup"><span data-stu-id="07dac-136">See the "PersistElement Block" table for the format of this structure.</span></span>  <br/> |
   
<span data-ttu-id="07dac-137">**PersistBlockType 值**</span><span class="sxs-lookup"><span data-stu-id="07dac-137">**PersistBlockType Values**</span></span>

|<span data-ttu-id="07dac-138">**名称**</span><span class="sxs-lookup"><span data-stu-id="07dac-138">**Name**</span></span>|<span data-ttu-id="07dac-139">**Value**</span><span class="sxs-lookup"><span data-stu-id="07dac-139">**Value**</span></span>|<span data-ttu-id="07dac-140">**说明**</span><span class="sxs-lookup"><span data-stu-id="07dac-140">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07dac-141">PERSIST_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="07dac-141">PERSIST_SENTINEL</span></span>  <br/> |<span data-ttu-id="07dac-142">0x0000</span><span class="sxs-lookup"><span data-stu-id="07dac-142">0x0000</span></span>  <br/> |<span data-ttu-id="07dac-143">指示将不会处理更多的**PersistData**块。</span><span class="sxs-lookup"><span data-stu-id="07dac-143">Indicates that no more **PersistData** blocks will be processed.</span></span>  <br/> |
|<span data-ttu-id="07dac-144">RSF_PID_RSS_SUBSCRIPTION</span><span class="sxs-lookup"><span data-stu-id="07dac-144">RSF_PID_RSS_SUBSCRIPTION</span></span>  <br/> |<span data-ttu-id="07dac-145">0x8001</span><span class="sxs-lookup"><span data-stu-id="07dac-145">0x8001</span></span>  <br/> |<span data-ttu-id="07dac-146">指示此块包含 "RSS 订阅" 文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="07dac-146">Indicates that this block contains data for the RSS Subscriptions folder.</span></span>  <br/> |
|<span data-ttu-id="07dac-147">RSF_PID_SEND_AND_TRACK</span><span class="sxs-lookup"><span data-stu-id="07dac-147">RSF_PID_SEND_AND_TRACK</span></span>  <br/> |<span data-ttu-id="07dac-148">0x8002</span><span class="sxs-lookup"><span data-stu-id="07dac-148">0x8002</span></span>  <br/> |<span data-ttu-id="07dac-149">指示此块包含所跟踪的邮件处理文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="07dac-149">Indicates that this block contains data for the Tracked Mail Processing folder.</span></span>  <br/> |
|<span data-ttu-id="07dac-150">RSF_PID_TODO_SEARCH</span><span class="sxs-lookup"><span data-stu-id="07dac-150">RSF_PID_TODO_SEARCH</span></span>  <br/> |<span data-ttu-id="07dac-151">0x8004</span><span class="sxs-lookup"><span data-stu-id="07dac-151">0x8004</span></span>  <br/> |<span data-ttu-id="07dac-152">指示此块包含待办搜索文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="07dac-152">Indicates that this block contains data for the To-Do Search folder.</span></span>  <br/> |
|<span data-ttu-id="07dac-153">RSF_PID_CONV_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="07dac-153">RSF_PID_CONV_ACTIONS</span></span>  <br/> |<span data-ttu-id="07dac-154">0x8006</span><span class="sxs-lookup"><span data-stu-id="07dac-154">0x8006</span></span>  <br/> |<span data-ttu-id="07dac-155">指示此块包含对话动作设置文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="07dac-155">Indicates that this block contains data for the Conversation Action Settings folder.</span></span>  <br/> |
|<span data-ttu-id="07dac-156">RSF_PID_COMBINED_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="07dac-156">RSF_PID_COMBINED_ACTIONS</span></span>  <br/> |<span data-ttu-id="07dac-157">0x8007</span><span class="sxs-lookup"><span data-stu-id="07dac-157">0x8007</span></span>  <br/> |<span data-ttu-id="07dac-158">此值为保留值。</span><span class="sxs-lookup"><span data-stu-id="07dac-158">This value is reserved.</span></span>  <br/> |
|<span data-ttu-id="07dac-159">RSF_PID_SUGGESTED_CONTACTS</span><span class="sxs-lookup"><span data-stu-id="07dac-159">RSF_PID_SUGGESTED_CONTACTS</span></span>  <br/> |<span data-ttu-id="07dac-160">0x8008</span><span class="sxs-lookup"><span data-stu-id="07dac-160">0x8008</span></span>  <br/> |<span data-ttu-id="07dac-161">指示此块包含建议的 "联系人" 文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="07dac-161">Indicates that this block contains data for the Suggested Contacts folder.</span></span>  <br/> |
|<span data-ttu-id="07dac-162">RSF_PID_CONTACT_SEARCH</span><span class="sxs-lookup"><span data-stu-id="07dac-162">RSF_PID_CONTACT_SEARCH</span></span>  <br/> |<span data-ttu-id="07dac-163">0x8009</span><span class="sxs-lookup"><span data-stu-id="07dac-163">0x8009</span></span>  <br/> |<span data-ttu-id="07dac-164">指示此块包含联系人搜索文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="07dac-164">Indicates that this block contains data for the Contacts Search folder.</span></span>  <br/> <span data-ttu-id="07dac-165">仅供 Outlook 使用。</span><span class="sxs-lookup"><span data-stu-id="07dac-165">Used only by Outlook.</span></span>  <br/> |
|<span data-ttu-id="07dac-166">RSF_PID_BUDDYLIST_PDLS</span><span class="sxs-lookup"><span data-stu-id="07dac-166">RSF_PID_BUDDYLIST_PDLS</span></span>  <br/> |<span data-ttu-id="07dac-167">0x800A</span><span class="sxs-lookup"><span data-stu-id="07dac-167">0x800A</span></span>  <br/> |<span data-ttu-id="07dac-168">指示此块包含 "即时消息 (IM) 联系人列表" 文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="07dac-168">Indicates that this block contains data for the Instant Messaging (IM) Contact Lists folder.</span></span> <span data-ttu-id="07dac-169">引用的文件夹包含表示 IM 联系人列表中的每个组的个人通讯组列表 (PDLs)。</span><span class="sxs-lookup"><span data-stu-id="07dac-169">The referenced folder contains Personal Distribution Lists (PDLs) representing each group within the IM Contact list.</span></span>  <br/> <span data-ttu-id="07dac-170">由 Outlook 和 Exchange 使用。</span><span class="sxs-lookup"><span data-stu-id="07dac-170">Used by both Outlook and Exchange.</span></span>  <br/> |
|<span data-ttu-id="07dac-171">RSF_PID_BUDDYLIST_CONTACTS</span><span class="sxs-lookup"><span data-stu-id="07dac-171">RSF_PID_BUDDYLIST_CONTACTS</span></span>  <br/> |<span data-ttu-id="07dac-172">0x800B</span><span class="sxs-lookup"><span data-stu-id="07dac-172">0x800B</span></span>  <br/> |<span data-ttu-id="07dac-173">指示此块包含 IM 联系人文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="07dac-173">Indicates that this block contains data for the IM Contacts folder.</span></span> <span data-ttu-id="07dac-174">引用的文件夹包含 IM 联系人列表组所引用的各个联系人。</span><span class="sxs-lookup"><span data-stu-id="07dac-174">The referenced folder contains the individual contacts referenced by the IM Contact List groups.</span></span>  <br/> <span data-ttu-id="07dac-175">由 Outlook 和 Exchange 使用。</span><span class="sxs-lookup"><span data-stu-id="07dac-175">Used by both Outlook and Exchange.</span></span>  <br/> |
   
<span data-ttu-id="07dac-176">如果**PersistBlockType**值不是在此处定义的值之一, 则将忽略**PersistData**块, 并继续处理, 直到处理 PERSIST_SENTINEL **PersistID**或到达流的末尾。</span><span class="sxs-lookup"><span data-stu-id="07dac-176">If the **PersistBlockType** value is not one of the ones defined here, the **PersistData** block is ignored and processing is continued until either a PERSIST_SENTINEL **PersistID** is processed or the end of the stream is reached.</span></span> 
  
<span data-ttu-id="07dac-177">**PersistElementBlock**</span><span class="sxs-lookup"><span data-stu-id="07dac-177">**PersistElementBlock**</span></span>

|<span data-ttu-id="07dac-178">**Name**</span><span class="sxs-lookup"><span data-stu-id="07dac-178">**Name**</span></span>|<span data-ttu-id="07dac-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="07dac-179">**Type**</span></span>|<span data-ttu-id="07dac-180">**Size**</span><span class="sxs-lookup"><span data-stu-id="07dac-180">**Size**</span></span>|<span data-ttu-id="07dac-181">**Description**</span><span class="sxs-lookup"><span data-stu-id="07dac-181">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07dac-182">**ElementID**</span><span class="sxs-lookup"><span data-stu-id="07dac-182">**ElementID**</span></span> <br/> |<span data-ttu-id="07dac-183">WORD</span><span class="sxs-lookup"><span data-stu-id="07dac-183">WORD</span></span>  <br/> |<span data-ttu-id="07dac-184">双面</span><span class="sxs-lookup"><span data-stu-id="07dac-184">2</span></span>  <br/> |<span data-ttu-id="07dac-185">指定此**PersistElement**块的类型标识符值。</span><span class="sxs-lookup"><span data-stu-id="07dac-185">Specifies the type identifier value for this **PersistElement** block.</span></span> <span data-ttu-id="07dac-186">有关有效值的列表, 请参阅 "PersistElementType Values" 表。</span><span class="sxs-lookup"><span data-stu-id="07dac-186">See the "PersistElementType Values" table for a list of valid values.</span></span>  <br/> |
|<span data-ttu-id="07dac-187">**ElementDataSize**</span><span class="sxs-lookup"><span data-stu-id="07dac-187">**ElementDataSize**</span></span> <br/> |<span data-ttu-id="07dac-188">WORD</span><span class="sxs-lookup"><span data-stu-id="07dac-188">WORD</span></span>  <br/> |<span data-ttu-id="07dac-189">双面</span><span class="sxs-lookup"><span data-stu-id="07dac-189">2</span></span>  <br/> |<span data-ttu-id="07dac-190">指定**ElementData**字段的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="07dac-190">Specifies the size, in bytes, of the **ElementData** field.</span></span>  <br/> |
|<span data-ttu-id="07dac-191">**ElementData**</span><span class="sxs-lookup"><span data-stu-id="07dac-191">**ElementData**</span></span> <br/> |<span data-ttu-id="07dac-192">二进制数据数组</span><span class="sxs-lookup"><span data-stu-id="07dac-192">array of binary data</span></span>  <br/> |<span data-ttu-id="07dac-193">变量</span><span class="sxs-lookup"><span data-stu-id="07dac-193">variable</span></span>  <br/> |<span data-ttu-id="07dac-194">包含此**PersistID** + **ElementID**对的数据。</span><span class="sxs-lookup"><span data-stu-id="07dac-194">Contains the data for this **PersistID** + **ElementID** pair.</span></span>  <br/> |
   
<span data-ttu-id="07dac-195">**PersistElementType 值**</span><span class="sxs-lookup"><span data-stu-id="07dac-195">**PersistElementType Values**</span></span>

|<span data-ttu-id="07dac-196">**名称**</span><span class="sxs-lookup"><span data-stu-id="07dac-196">**Name**</span></span>|<span data-ttu-id="07dac-197">**值**</span><span class="sxs-lookup"><span data-stu-id="07dac-197">**Value**</span></span>|<span data-ttu-id="07dac-198">**ElementDataSize 的值**</span><span class="sxs-lookup"><span data-stu-id="07dac-198">**Value of ElementDataSize**</span></span>|<span data-ttu-id="07dac-199">**Description**</span><span class="sxs-lookup"><span data-stu-id="07dac-199">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07dac-200">RSF_ELID_HEADER</span><span class="sxs-lookup"><span data-stu-id="07dac-200">RSF_ELID_HEADER</span></span>  <br/> |<span data-ttu-id="07dac-201">0x0002</span><span class="sxs-lookup"><span data-stu-id="07dac-201">0x0002</span></span>  <br/> |<span data-ttu-id="07dac-202">0x0004</span><span class="sxs-lookup"><span data-stu-id="07dac-202">0x0004</span></span>  <br/> |<span data-ttu-id="07dac-203">指示此块的**ElementData**字段包含 DWORD 标头值。</span><span class="sxs-lookup"><span data-stu-id="07dac-203">Indicates that this block's **ElementData** field contains a DWORD Header value.</span></span> <span data-ttu-id="07dac-204">此值的解释方式取决于块的**PersistID**类型。</span><span class="sxs-lookup"><span data-stu-id="07dac-204">How this value is interpreted depends on the block's **PersistID** type.</span></span>  <br/> <span data-ttu-id="07dac-205">对于[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb.aspx)中指定的所有**PersistID**类型, 此值为零。</span><span class="sxs-lookup"><span data-stu-id="07dac-205">For all **PersistID** types specified in [[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb.aspx), this value is zero.</span></span>  <br/> |
|<span data-ttu-id="07dac-206">RSF_ELID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="07dac-206">RSF_ELID_ENTRYID</span></span>  <br/> |<span data-ttu-id="07dac-207">0x0001</span><span class="sxs-lookup"><span data-stu-id="07dac-207">0x0001</span></span>  <br/> |<span data-ttu-id="07dac-208">变量</span><span class="sxs-lookup"><span data-stu-id="07dac-208">variable</span></span>  <br/> |<span data-ttu-id="07dac-209">指示此块包含**PersistID**指定的文件夹的**EntryID** 。</span><span class="sxs-lookup"><span data-stu-id="07dac-209">Indicates that this block contains the **EntryID** of the folder specified by **PersistID**.</span></span>  <br/> |
|<span data-ttu-id="07dac-210">ELEMENT_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="07dac-210">ELEMENT_SENTINEL</span></span>  <br/> |<span data-ttu-id="07dac-211">0x0000</span><span class="sxs-lookup"><span data-stu-id="07dac-211">0x0000</span></span>  <br/> |<span data-ttu-id="07dac-212">0x0000</span><span class="sxs-lookup"><span data-stu-id="07dac-212">0x0000</span></span>  <br/> |<span data-ttu-id="07dac-213">指示将不会处理更多的**PersistElement**块。</span><span class="sxs-lookup"><span data-stu-id="07dac-213">Indicates that no more **PersistElement** blocks will be processed.</span></span>  <br/> |
   
<span data-ttu-id="07dac-214">如果**PersistElementType**值不是在此处定义的值之一, 则将忽略**PersistElement**块, 并继续处理, 直到处理 ELEMENT_SENTINEL **ElementID**或到达流的末尾。</span><span class="sxs-lookup"><span data-stu-id="07dac-214">If the **PersistElementType** value is not one of the ones defined here, the **PersistElement** block is ignored and processing is continued until either an ELEMENT_SENTINEL **ElementID** is processed or the end of the stream is reached.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="07dac-215">相关资源</span><span class="sxs-lookup"><span data-stu-id="07dac-215">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="07dac-216">协议规范</span><span class="sxs-lookup"><span data-stu-id="07dac-216">Protocol specifications</span></span>

<span data-ttu-id="07dac-217">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="07dac-217">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="07dac-218">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="07dac-218">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="07dac-219">[[毫秒-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="07dac-219">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="07dac-220">启用对允许/阻止列表的处理以及确定垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="07dac-220">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
<span data-ttu-id="07dac-221">[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="07dac-221">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="07dac-222">指定用于创建和定位邮箱中的特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="07dac-222">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="07dac-223">[[毫秒-OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="07dac-223">[[MS-OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="07dac-224">标识和标记旨在欺骗收件人的电子邮件, 以将敏感信息 (如密码和其他个人信息) 泄漏到非信任源。</span><span class="sxs-lookup"><span data-stu-id="07dac-224">Identifies and marks email messages that are designed to trick recipients into divulging sensitive information (such as passwords and other personal information) to a non-trustworthy source.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="07dac-225">头文件</span><span class="sxs-lookup"><span data-stu-id="07dac-225">Header files</span></span>

<span data-ttu-id="07dac-226">Mapitags</span><span class="sxs-lookup"><span data-stu-id="07dac-226">Mapitags.h</span></span>
  
> <span data-ttu-id="07dac-227">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="07dac-227">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="07dac-228">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="07dac-228">Mapidefs.h</span></span>
  
> <span data-ttu-id="07dac-229">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="07dac-229">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="07dac-230">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07dac-230">See also</span></span>



[<span data-ttu-id="07dac-231">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="07dac-231">MAPI Property Overview</span></span>](mapi-property-overview.md)
  
[<span data-ttu-id="07dac-232">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="07dac-232">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="07dac-233">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="07dac-233">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="07dac-234">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="07dac-234">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

