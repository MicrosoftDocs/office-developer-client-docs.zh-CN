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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390413"
---
# <a name="pidtagadditionalrenentryidsex-canonical-property"></a><span data-ttu-id="fd2fd-103">PidTagAdditionalRenEntryIdsEx 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd2fd-103">PidTagAdditionalRenEntryIdsEx Canonical Property</span></span>

  
  
<span data-ttu-id="fd2fd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd2fd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fd2fd-105">包含一个 store 对象的特殊文件夹条目 Id。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-105">Contains special folder entry IDs for a store object.</span></span> <span data-ttu-id="fd2fd-106">此多值属性中的每个条目可以映射到一个或多个条目 Id，即，没有条目和其相关联的条目 Id-一对多关系。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-106">Each entry in this multi-valued property can be mapped to one or more entry IDs, that is, there is a one-to-many relationship between an entry and its associated entry IDs.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fd2fd-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fd2fd-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="fd2fd-108">PR_ADDITIONAL_REN_ENTRYIDS_EX</span><span class="sxs-lookup"><span data-stu-id="fd2fd-108">PR_ADDITIONAL_REN_ENTRYIDS_EX</span></span>  <br/> |
|<span data-ttu-id="fd2fd-109">标识符：</span><span class="sxs-lookup"><span data-stu-id="fd2fd-109">Identifier:</span></span>  <br/> |<span data-ttu-id="fd2fd-110">0x36D9</span><span class="sxs-lookup"><span data-stu-id="fd2fd-110">0x36D9</span></span>  <br/> |
|<span data-ttu-id="fd2fd-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fd2fd-111">Data type:</span></span>  <br/> |<span data-ttu-id="fd2fd-112">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="fd2fd-112">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="fd2fd-113">区域：</span><span class="sxs-lookup"><span data-stu-id="fd2fd-113">Area:</span></span>  <br/> |<span data-ttu-id="fd2fd-114">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="fd2fd-114">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fd2fd-115">说明</span><span class="sxs-lookup"><span data-stu-id="fd2fd-115">Remarks</span></span>

<span data-ttu-id="fd2fd-116">如果使用此属性，则它包含指定条目 Id 的文件夹的块的数组。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-116">If this property is used, it contains an array of blocks that specifies the entry IDs for the folders.</span></span> <span data-ttu-id="fd2fd-117">块按照指定以下四个表的格式。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-117">The blocks follow the format specified by the following four tables.</span></span>
  
<span data-ttu-id="fd2fd-118">**PersistData 块**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-118">**PersistData Block**</span></span>

|<span data-ttu-id="fd2fd-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-119">**Name**</span></span>|<span data-ttu-id="fd2fd-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-120">**Type**</span></span>|<span data-ttu-id="fd2fd-121">**Size**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-121">**Size**</span></span>|<span data-ttu-id="fd2fd-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd2fd-123">**PersistID**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-123">**PersistID**</span></span> <br/> |<span data-ttu-id="fd2fd-124">WORD</span><span class="sxs-lookup"><span data-stu-id="fd2fd-124">WORD</span></span>  <br/> |<span data-ttu-id="fd2fd-125">2</span><span class="sxs-lookup"><span data-stu-id="fd2fd-125">2</span></span>  <br/> |<span data-ttu-id="fd2fd-126">键入此**PersistData**条目标识符值。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-126">Type identifier value for this **PersistData** entry.</span></span> <span data-ttu-id="fd2fd-127">请参阅有效的值列表中的"PersistBlockType 值"表。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-127">See the "PersistBlockType Values" table for the list of valid values.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-128">**DataElementsSize**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-128">**DataElementsSize**</span></span> <br/> |<span data-ttu-id="fd2fd-129">WORD</span><span class="sxs-lookup"><span data-stu-id="fd2fd-129">WORD</span></span>  <br/> |<span data-ttu-id="fd2fd-130">2</span><span class="sxs-lookup"><span data-stu-id="fd2fd-130">2</span></span>  <br/> |<span data-ttu-id="fd2fd-131">大小 （以字节为单位， **DataElements**字段）。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-131">Size, in bytes, of the **DataElements** field.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-132">**DataElements**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-132">**DataElements**</span></span> <br/> |<span data-ttu-id="fd2fd-133">**PersistElement**块的数组</span><span class="sxs-lookup"><span data-stu-id="fd2fd-133">array of **PersistElement** blocks</span></span>  <br/> |<span data-ttu-id="fd2fd-134">变量</span><span class="sxs-lookup"><span data-stu-id="fd2fd-134">variable</span></span>  <br/> |<span data-ttu-id="fd2fd-135">指示存储存在多少**PersistElement**条目。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-135">Indicates how many **PersistElement** entries exist for the store.</span></span> <span data-ttu-id="fd2fd-136">请参阅此结构的格式的"PersistElement 块"表。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-136">See the "PersistElement Block" table for the format of this structure.</span></span>  <br/> |
   
<span data-ttu-id="fd2fd-137">**PersistBlockType 值**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-137">**PersistBlockType Values**</span></span>

|<span data-ttu-id="fd2fd-138">**名称**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-138">**Name**</span></span>|<span data-ttu-id="fd2fd-139">**值**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-139">**Value**</span></span>|<span data-ttu-id="fd2fd-140">**说明**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-140">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd2fd-141">PERSIST_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="fd2fd-141">PERSIST_SENTINEL</span></span>  <br/> |<span data-ttu-id="fd2fd-142">0x0000</span><span class="sxs-lookup"><span data-stu-id="fd2fd-142">0x0000</span></span>  <br/> |<span data-ttu-id="fd2fd-143">指示将处理没有更多的**PersistData**块。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-143">Indicates that no more **PersistData** blocks will be processed.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-144">RSF_PID_RSS_SUBSCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd2fd-144">RSF_PID_RSS_SUBSCRIPTION</span></span>  <br/> |<span data-ttu-id="fd2fd-145">0x8001</span><span class="sxs-lookup"><span data-stu-id="fd2fd-145">0x8001</span></span>  <br/> |<span data-ttu-id="fd2fd-146">指示此块包含数据的 RSS 订阅文件夹。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-146">Indicates that this block contains data for the RSS Subscriptions folder.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-147">RSF_PID_SEND_AND_TRACK</span><span class="sxs-lookup"><span data-stu-id="fd2fd-147">RSF_PID_SEND_AND_TRACK</span></span>  <br/> |<span data-ttu-id="fd2fd-148">0x8002</span><span class="sxs-lookup"><span data-stu-id="fd2fd-148">0x8002</span></span>  <br/> |<span data-ttu-id="fd2fd-149">指示此块包含跟踪邮件处理文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-149">Indicates that this block contains data for the Tracked Mail Processing folder.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-150">RSF_PID_TODO_SEARCH</span><span class="sxs-lookup"><span data-stu-id="fd2fd-150">RSF_PID_TODO_SEARCH</span></span>  <br/> |<span data-ttu-id="fd2fd-151">0x8004</span><span class="sxs-lookup"><span data-stu-id="fd2fd-151">0x8004</span></span>  <br/> |<span data-ttu-id="fd2fd-152">指示此块包含待办事项搜索文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-152">Indicates that this block contains data for the To-Do Search folder.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-153">RSF_PID_CONV_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="fd2fd-153">RSF_PID_CONV_ACTIONS</span></span>  <br/> |<span data-ttu-id="fd2fd-154">0x8006</span><span class="sxs-lookup"><span data-stu-id="fd2fd-154">0x8006</span></span>  <br/> |<span data-ttu-id="fd2fd-155">指示此块包含数据的对话操作设置文件夹。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-155">Indicates that this block contains data for the Conversation Action Settings folder.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-156">RSF_PID_COMBINED_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="fd2fd-156">RSF_PID_COMBINED_ACTIONS</span></span>  <br/> |<span data-ttu-id="fd2fd-157">0x8007</span><span class="sxs-lookup"><span data-stu-id="fd2fd-157">0x8007</span></span>  <br/> |<span data-ttu-id="fd2fd-158">保留此值。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-158">This value is reserved.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-159">RSF_PID_SUGGESTED_CONTACTS</span><span class="sxs-lookup"><span data-stu-id="fd2fd-159">RSF_PID_SUGGESTED_CONTACTS</span></span>  <br/> |<span data-ttu-id="fd2fd-160">0x8008</span><span class="sxs-lookup"><span data-stu-id="fd2fd-160">0x8008</span></span>  <br/> |<span data-ttu-id="fd2fd-161">指示此块包含建议的联系人文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-161">Indicates that this block contains data for the Suggested Contacts folder.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-162">RSF_PID_CONTACT_SEARCH</span><span class="sxs-lookup"><span data-stu-id="fd2fd-162">RSF_PID_CONTACT_SEARCH</span></span>  <br/> |<span data-ttu-id="fd2fd-163">0x8009</span><span class="sxs-lookup"><span data-stu-id="fd2fd-163">0x8009</span></span>  <br/> |<span data-ttu-id="fd2fd-164">指示此块包含联系人搜索文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-164">Indicates that this block contains data for the Contacts Search folder.</span></span>  <br/> <span data-ttu-id="fd2fd-165">仅由 Outlook。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-165">Used only by Outlook.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-166">RSF_PID_BUDDYLIST_PDLS</span><span class="sxs-lookup"><span data-stu-id="fd2fd-166">RSF_PID_BUDDYLIST_PDLS</span></span>  <br/> |<span data-ttu-id="fd2fd-167">0x800A</span><span class="sxs-lookup"><span data-stu-id="fd2fd-167">0x800A</span></span>  <br/> |<span data-ttu-id="fd2fd-168">指示此块包含数据的即时消息 (IM) 联系人列表的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-168">Indicates that this block contains data for the Instant Messaging (IM) Contact Lists folder.</span></span> <span data-ttu-id="fd2fd-169">引用文件夹包含个人通讯组列表 (PDLs) 表示 IM 联系人列表中的每个组。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-169">The referenced folder contains Personal Distribution Lists (PDLs) representing each group within the IM Contact list.</span></span>  <br/> <span data-ttu-id="fd2fd-170">Outlook 和 Exchange 使用。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-170">Used by both Outlook and Exchange.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-171">RSF_PID_BUDDYLIST_CONTACTS</span><span class="sxs-lookup"><span data-stu-id="fd2fd-171">RSF_PID_BUDDYLIST_CONTACTS</span></span>  <br/> |<span data-ttu-id="fd2fd-172">0x800B</span><span class="sxs-lookup"><span data-stu-id="fd2fd-172">0x800B</span></span>  <br/> |<span data-ttu-id="fd2fd-173">指示此块包含数据的 IM 联系人文件夹。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-173">Indicates that this block contains data for the IM Contacts folder.</span></span> <span data-ttu-id="fd2fd-174">引用文件夹包含单个联系人的 IM 联系人列表组引用。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-174">The referenced folder contains the individual contacts referenced by the IM Contact List groups.</span></span>  <br/> <span data-ttu-id="fd2fd-175">Outlook 和 Exchange 使用。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-175">Used by both Outlook and Exchange.</span></span>  <br/> |
   
<span data-ttu-id="fd2fd-176">如果**PersistBlockType**值不是所定义此处， **PersistData**块被忽略，直到处理 PERSIST_SENTINEL **PersistID**或达到流末尾继续处理。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-176">If the **PersistBlockType** value is not one of the ones defined here, the **PersistData** block is ignored and processing is continued until either a PERSIST_SENTINEL **PersistID** is processed or the end of the stream is reached.</span></span> 
  
<span data-ttu-id="fd2fd-177">**PersistElementBlock**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-177">**PersistElementBlock**</span></span>

|<span data-ttu-id="fd2fd-178">**名称**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-178">**Name**</span></span>|<span data-ttu-id="fd2fd-179">**类型**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-179">**Type**</span></span>|<span data-ttu-id="fd2fd-180">**Size**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-180">**Size**</span></span>|<span data-ttu-id="fd2fd-181">**说明**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-181">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd2fd-182">**ElementID**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-182">**ElementID**</span></span> <br/> |<span data-ttu-id="fd2fd-183">WORD</span><span class="sxs-lookup"><span data-stu-id="fd2fd-183">WORD</span></span>  <br/> |<span data-ttu-id="fd2fd-184">2</span><span class="sxs-lookup"><span data-stu-id="fd2fd-184">2</span></span>  <br/> |<span data-ttu-id="fd2fd-185">指定此**PersistElement**块的类型标识符值。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-185">Specifies the type identifier value for this **PersistElement** block.</span></span> <span data-ttu-id="fd2fd-186">请参阅有效的值的列表的"PersistElementType 值"表。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-186">See the "PersistElementType Values" table for a list of valid values.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-187">**ElementDataSize**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-187">**ElementDataSize**</span></span> <br/> |<span data-ttu-id="fd2fd-188">WORD</span><span class="sxs-lookup"><span data-stu-id="fd2fd-188">WORD</span></span>  <br/> |<span data-ttu-id="fd2fd-189">2</span><span class="sxs-lookup"><span data-stu-id="fd2fd-189">2</span></span>  <br/> |<span data-ttu-id="fd2fd-190">指定的大小，以字节为单位， **ElementData**字段。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-190">Specifies the size, in bytes, of the **ElementData** field.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-191">**ElementData**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-191">**ElementData**</span></span> <br/> |<span data-ttu-id="fd2fd-192">二进制数据的数组</span><span class="sxs-lookup"><span data-stu-id="fd2fd-192">array of binary data</span></span>  <br/> |<span data-ttu-id="fd2fd-193">变量</span><span class="sxs-lookup"><span data-stu-id="fd2fd-193">variable</span></span>  <br/> |<span data-ttu-id="fd2fd-194">包含数据的此**PersistID** + **ElementID**对。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-194">Contains the data for this **PersistID** + **ElementID** pair.</span></span>  <br/> |
   
<span data-ttu-id="fd2fd-195">**PersistElementType 值**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-195">**PersistElementType Values**</span></span>

|<span data-ttu-id="fd2fd-196">**名称**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-196">**Name**</span></span>|<span data-ttu-id="fd2fd-197">**值**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-197">**Value**</span></span>|<span data-ttu-id="fd2fd-198">**ElementDataSize 的值**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-198">**Value of ElementDataSize**</span></span>|<span data-ttu-id="fd2fd-199">**说明**</span><span class="sxs-lookup"><span data-stu-id="fd2fd-199">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd2fd-200">RSF_ELID_HEADER</span><span class="sxs-lookup"><span data-stu-id="fd2fd-200">RSF_ELID_HEADER</span></span>  <br/> |<span data-ttu-id="fd2fd-201">0x0002</span><span class="sxs-lookup"><span data-stu-id="fd2fd-201">0x0002</span></span>  <br/> |<span data-ttu-id="fd2fd-202">0x0004</span><span class="sxs-lookup"><span data-stu-id="fd2fd-202">0x0004</span></span>  <br/> |<span data-ttu-id="fd2fd-203">指示此块**ElementData**字段包含 DWORD 标头值。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-203">Indicates that this block's **ElementData** field contains a DWORD Header value.</span></span> <span data-ttu-id="fd2fd-204">如何解释此值取决于的块**PersistID**类型。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-204">How this value is interpreted depends on the block's **PersistID** type.</span></span>  <br/> <span data-ttu-id="fd2fd-205">对于[[MS OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb.aspx)中指定的所有**PersistID**类型，此值为零。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-205">For all **PersistID** types specified in [[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb.aspx), this value is zero.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-206">RSF_ELID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="fd2fd-206">RSF_ELID_ENTRYID</span></span>  <br/> |<span data-ttu-id="fd2fd-207">0x0001</span><span class="sxs-lookup"><span data-stu-id="fd2fd-207">0x0001</span></span>  <br/> |<span data-ttu-id="fd2fd-208">变量</span><span class="sxs-lookup"><span data-stu-id="fd2fd-208">variable</span></span>  <br/> |<span data-ttu-id="fd2fd-209">指示此块包含**PersistID**指定的文件夹的**EntryID** 。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-209">Indicates that this block contains the **EntryID** of the folder specified by **PersistID**.</span></span>  <br/> |
|<span data-ttu-id="fd2fd-210">ELEMENT_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="fd2fd-210">ELEMENT_SENTINEL</span></span>  <br/> |<span data-ttu-id="fd2fd-211">0x0000</span><span class="sxs-lookup"><span data-stu-id="fd2fd-211">0x0000</span></span>  <br/> |<span data-ttu-id="fd2fd-212">0x0000</span><span class="sxs-lookup"><span data-stu-id="fd2fd-212">0x0000</span></span>  <br/> |<span data-ttu-id="fd2fd-213">指示将处理没有更多的**PersistElement**块。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-213">Indicates that no more **PersistElement** blocks will be processed.</span></span>  <br/> |
   
<span data-ttu-id="fd2fd-214">如果**PersistElementType**值不是所定义此处， **PersistElement**块被忽略，直到处理 ELEMENT_SENTINEL **ElementID**或达到流末尾继续处理。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-214">If the **PersistElementType** value is not one of the ones defined here, the **PersistElement** block is ignored and processing is continued until either an ELEMENT_SENTINEL **ElementID** is processed or the end of the stream is reached.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="fd2fd-215">相关资源</span><span class="sxs-lookup"><span data-stu-id="fd2fd-215">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fd2fd-216">协议规范</span><span class="sxs-lookup"><span data-stu-id="fd2fd-216">Protocol specifications</span></span>

<span data-ttu-id="fd2fd-217">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fd2fd-217">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fd2fd-218">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-218">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fd2fd-219">[[MS OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fd2fd-219">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fd2fd-220">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-220">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
<span data-ttu-id="fd2fd-221">[[MS OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fd2fd-221">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fd2fd-222">指定的属性和用于创建和邮箱中查找的特殊文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-222">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="fd2fd-223">[[MS OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fd2fd-223">[[MS-OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fd2fd-224">标识，并将标记旨在到非可靠来源欺骗透露敏感信息 （如密码和其他个人信息） 的收件人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-224">Identifies and marks email messages that are designed to trick recipients into divulging sensitive information (such as passwords and other personal information) to a non-trustworthy source.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fd2fd-225">头文件</span><span class="sxs-lookup"><span data-stu-id="fd2fd-225">Header files</span></span>

<span data-ttu-id="fd2fd-226">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fd2fd-226">Mapitags.h</span></span>
  
> <span data-ttu-id="fd2fd-227">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-227">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="fd2fd-228">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fd2fd-228">Mapidefs.h</span></span>
  
> <span data-ttu-id="fd2fd-229">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fd2fd-229">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fd2fd-230">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd2fd-230">See also</span></span>



[<span data-ttu-id="fd2fd-231">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="fd2fd-231">MAPI Property Overview</span></span>](mapi-property-overview.md)
  
[<span data-ttu-id="fd2fd-232">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd2fd-232">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fd2fd-233">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fd2fd-233">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fd2fd-234">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fd2fd-234">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

