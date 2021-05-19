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
# <a name="pidtagadditionalrenentryidsex-canonical-property"></a><span data-ttu-id="38800-103">PidTagAdditionalRenEntryIdsEx 规范属性</span><span class="sxs-lookup"><span data-stu-id="38800-103">PidTagAdditionalRenEntryIdsEx Canonical Property</span></span>

  
  
<span data-ttu-id="38800-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38800-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38800-105">包含存储对象的特殊文件夹条目的 ID。</span><span class="sxs-lookup"><span data-stu-id="38800-105">Contains special folder entry IDs for a store object.</span></span> <span data-ttu-id="38800-106">此多值属性中的每个条目都可以映射到一个或多个条目，即条目与其关联的条目 ID 之间具有一对多关系。</span><span class="sxs-lookup"><span data-stu-id="38800-106">Each entry in this multi-valued property can be mapped to one or more entry IDs, that is, there is a one-to-many relationship between an entry and its associated entry IDs.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="38800-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="38800-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="38800-108">PR_ADDITIONAL_REN_ENTRYIDS_EX</span><span class="sxs-lookup"><span data-stu-id="38800-108">PR_ADDITIONAL_REN_ENTRYIDS_EX</span></span>  <br/> |
|<span data-ttu-id="38800-109">标识符:</span><span class="sxs-lookup"><span data-stu-id="38800-109">Identifier:</span></span>  <br/> |<span data-ttu-id="38800-110">0x36D9</span><span class="sxs-lookup"><span data-stu-id="38800-110">0x36D9</span></span>  <br/> |
|<span data-ttu-id="38800-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="38800-111">Data type:</span></span>  <br/> |<span data-ttu-id="38800-112">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="38800-112">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="38800-113">区域：</span><span class="sxs-lookup"><span data-stu-id="38800-113">Area:</span></span>  <br/> |<span data-ttu-id="38800-114">Outlook应用程序</span><span class="sxs-lookup"><span data-stu-id="38800-114">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="38800-115">备注</span><span class="sxs-lookup"><span data-stu-id="38800-115">Remarks</span></span>

<span data-ttu-id="38800-116">如果使用此属性，则它包含一个块数组，该数组指定文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="38800-116">If this property is used, it contains an array of blocks that specifies the entry IDs for the folders.</span></span> <span data-ttu-id="38800-117">块遵循以下四个表指定的格式。</span><span class="sxs-lookup"><span data-stu-id="38800-117">The blocks follow the format specified by the following four tables.</span></span>
  
<span data-ttu-id="38800-118">**PersistData 块**</span><span class="sxs-lookup"><span data-stu-id="38800-118">**PersistData Block**</span></span>

|<span data-ttu-id="38800-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="38800-119">**Name**</span></span>|<span data-ttu-id="38800-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="38800-120">**Type**</span></span>|<span data-ttu-id="38800-121">**大小**</span><span class="sxs-lookup"><span data-stu-id="38800-121">**Size**</span></span>|<span data-ttu-id="38800-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="38800-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38800-123">**PersistID**</span><span class="sxs-lookup"><span data-stu-id="38800-123">**PersistID**</span></span> <br/> |<span data-ttu-id="38800-124">WORD</span><span class="sxs-lookup"><span data-stu-id="38800-124">WORD</span></span>  <br/> |<span data-ttu-id="38800-125">2</span><span class="sxs-lookup"><span data-stu-id="38800-125">2</span></span>  <br/> |<span data-ttu-id="38800-126">此 **PersistData** 项的类型标识符值。</span><span class="sxs-lookup"><span data-stu-id="38800-126">Type identifier value for this **PersistData** entry.</span></span> <span data-ttu-id="38800-127">有关有效值的列表，请参阅"PersistBlockType 值"表。</span><span class="sxs-lookup"><span data-stu-id="38800-127">See the "PersistBlockType Values" table for the list of valid values.</span></span>  <br/> |
|<span data-ttu-id="38800-128">**DataElementsSize**</span><span class="sxs-lookup"><span data-stu-id="38800-128">**DataElementsSize**</span></span> <br/> |<span data-ttu-id="38800-129">WORD</span><span class="sxs-lookup"><span data-stu-id="38800-129">WORD</span></span>  <br/> |<span data-ttu-id="38800-130">2</span><span class="sxs-lookup"><span data-stu-id="38800-130">2</span></span>  <br/> |<span data-ttu-id="38800-131">**DataElements 字段的大小（以字节** 为单位）。</span><span class="sxs-lookup"><span data-stu-id="38800-131">Size, in bytes, of the **DataElements** field.</span></span>  <br/> |
|<span data-ttu-id="38800-132">**DataElements**</span><span class="sxs-lookup"><span data-stu-id="38800-132">**DataElements**</span></span> <br/> |<span data-ttu-id="38800-133">**PersistElement 块** 数组</span><span class="sxs-lookup"><span data-stu-id="38800-133">array of **PersistElement** blocks</span></span>  <br/> |<span data-ttu-id="38800-134">变量</span><span class="sxs-lookup"><span data-stu-id="38800-134">variable</span></span>  <br/> |<span data-ttu-id="38800-135">指示存储区 **存在多少个 PersistElement** 条目。</span><span class="sxs-lookup"><span data-stu-id="38800-135">Indicates how many **PersistElement** entries exist for the store.</span></span> <span data-ttu-id="38800-136">有关此结构的格式，请参阅"PersistElement Block"表。</span><span class="sxs-lookup"><span data-stu-id="38800-136">See the "PersistElement Block" table for the format of this structure.</span></span>  <br/> |
   
<span data-ttu-id="38800-137">**PersistBlockType 值**</span><span class="sxs-lookup"><span data-stu-id="38800-137">**PersistBlockType Values**</span></span>

|<span data-ttu-id="38800-138">**名称**</span><span class="sxs-lookup"><span data-stu-id="38800-138">**Name**</span></span>|<span data-ttu-id="38800-139">**值**</span><span class="sxs-lookup"><span data-stu-id="38800-139">**Value**</span></span>|<span data-ttu-id="38800-140">**说明**</span><span class="sxs-lookup"><span data-stu-id="38800-140">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="38800-141">PERSIST_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="38800-141">PERSIST_SENTINEL</span></span>  <br/> |<span data-ttu-id="38800-142">0x0000</span><span class="sxs-lookup"><span data-stu-id="38800-142">0x0000</span></span>  <br/> |<span data-ttu-id="38800-143">指示不再处理 **PersistData** 块。</span><span class="sxs-lookup"><span data-stu-id="38800-143">Indicates that no more **PersistData** blocks will be processed.</span></span>  <br/> |
|<span data-ttu-id="38800-144">RSF_PID_RSS_SUBSCRIPTION</span><span class="sxs-lookup"><span data-stu-id="38800-144">RSF_PID_RSS_SUBSCRIPTION</span></span>  <br/> |<span data-ttu-id="38800-145">0x8001</span><span class="sxs-lookup"><span data-stu-id="38800-145">0x8001</span></span>  <br/> |<span data-ttu-id="38800-146">指示此块包含 RSS 订阅文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="38800-146">Indicates that this block contains data for the RSS Subscriptions folder.</span></span>  <br/> |
|<span data-ttu-id="38800-147">RSF_PID_SEND_AND_TRACK</span><span class="sxs-lookup"><span data-stu-id="38800-147">RSF_PID_SEND_AND_TRACK</span></span>  <br/> |<span data-ttu-id="38800-148">0x8002</span><span class="sxs-lookup"><span data-stu-id="38800-148">0x8002</span></span>  <br/> |<span data-ttu-id="38800-149">指示此块包含"跟踪的邮件处理"文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="38800-149">Indicates that this block contains data for the Tracked Mail Processing folder.</span></span>  <br/> |
|<span data-ttu-id="38800-150">RSF_PID_TODO_SEARCH</span><span class="sxs-lookup"><span data-stu-id="38800-150">RSF_PID_TODO_SEARCH</span></span>  <br/> |<span data-ttu-id="38800-151">0x8004</span><span class="sxs-lookup"><span data-stu-id="38800-151">0x8004</span></span>  <br/> |<span data-ttu-id="38800-152">指示此块包含搜索文件夹To-Do数据。</span><span class="sxs-lookup"><span data-stu-id="38800-152">Indicates that this block contains data for the To-Do Search folder.</span></span>  <br/> |
|<span data-ttu-id="38800-153">RSF_PID_CONV_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="38800-153">RSF_PID_CONV_ACTIONS</span></span>  <br/> |<span data-ttu-id="38800-154">0x8006</span><span class="sxs-lookup"><span data-stu-id="38800-154">0x8006</span></span>  <br/> |<span data-ttu-id="38800-155">指示此块包含对话操作文件夹设置数据。</span><span class="sxs-lookup"><span data-stu-id="38800-155">Indicates that this block contains data for the Conversation Action Settings folder.</span></span>  <br/> |
|<span data-ttu-id="38800-156">RSF_PID_COMBINED_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="38800-156">RSF_PID_COMBINED_ACTIONS</span></span>  <br/> |<span data-ttu-id="38800-157">0x8007</span><span class="sxs-lookup"><span data-stu-id="38800-157">0x8007</span></span>  <br/> |<span data-ttu-id="38800-158">保留此值。</span><span class="sxs-lookup"><span data-stu-id="38800-158">This value is reserved.</span></span>  <br/> |
|<span data-ttu-id="38800-159">RSF_PID_SUGGESTED_CONTACTS</span><span class="sxs-lookup"><span data-stu-id="38800-159">RSF_PID_SUGGESTED_CONTACTS</span></span>  <br/> |<span data-ttu-id="38800-160">0x8008</span><span class="sxs-lookup"><span data-stu-id="38800-160">0x8008</span></span>  <br/> |<span data-ttu-id="38800-161">指示此块包含"建议的联系人"文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="38800-161">Indicates that this block contains data for the Suggested Contacts folder.</span></span>  <br/> |
|<span data-ttu-id="38800-162">RSF_PID_CONTACT_SEARCH</span><span class="sxs-lookup"><span data-stu-id="38800-162">RSF_PID_CONTACT_SEARCH</span></span>  <br/> |<span data-ttu-id="38800-163">0x8009</span><span class="sxs-lookup"><span data-stu-id="38800-163">0x8009</span></span>  <br/> |<span data-ttu-id="38800-164">指示此块包含"联系人搜索"文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="38800-164">Indicates that this block contains data for the Contacts Search folder.</span></span>  <br/> <span data-ttu-id="38800-165">仅由 Outlook。</span><span class="sxs-lookup"><span data-stu-id="38800-165">Used only by Outlook.</span></span>  <br/> |
|<span data-ttu-id="38800-166">RSF_PID_BUDDYLIST_PDLS</span><span class="sxs-lookup"><span data-stu-id="38800-166">RSF_PID_BUDDYLIST_PDLS</span></span>  <br/> |<span data-ttu-id="38800-167">0x800A</span><span class="sxs-lookup"><span data-stu-id="38800-167">0x800A</span></span>  <br/> |<span data-ttu-id="38800-168">指示此块包含即时消息和即时消息 (IM) 文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="38800-168">Indicates that this block contains data for the Instant Messaging (IM) Contact Lists folder.</span></span> <span data-ttu-id="38800-169">引用的文件夹包含代表 IM 联系人列表 (组) 组的个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="38800-169">The referenced folder contains Personal Distribution Lists (PDLs) representing each group within the IM Contact list.</span></span>  <br/> <span data-ttu-id="38800-170">由 Outlook 和 Exchange。</span><span class="sxs-lookup"><span data-stu-id="38800-170">Used by both Outlook and Exchange.</span></span>  <br/> |
|<span data-ttu-id="38800-171">RSF_PID_BUDDYLIST_CONTACTS</span><span class="sxs-lookup"><span data-stu-id="38800-171">RSF_PID_BUDDYLIST_CONTACTS</span></span>  <br/> |<span data-ttu-id="38800-172">0x800B</span><span class="sxs-lookup"><span data-stu-id="38800-172">0x800B</span></span>  <br/> |<span data-ttu-id="38800-173">指示此块包含"IM 联系人"文件夹的数据。</span><span class="sxs-lookup"><span data-stu-id="38800-173">Indicates that this block contains data for the IM Contacts folder.</span></span> <span data-ttu-id="38800-174">引用的文件夹包含 IM 联系人列表组引用的单个联系人。</span><span class="sxs-lookup"><span data-stu-id="38800-174">The referenced folder contains the individual contacts referenced by the IM Contact List groups.</span></span>  <br/> <span data-ttu-id="38800-175">由 Outlook 和 Exchange。</span><span class="sxs-lookup"><span data-stu-id="38800-175">Used by both Outlook and Exchange.</span></span>  <br/> |
   
<span data-ttu-id="38800-176">如果 **PersistBlockType** 值不是此处定义的值之一，将忽略 **PersistData** 块，并继续进行处理，直到处理完 PERSIST_SENTINEL **PersistID** 或到达流的末尾。</span><span class="sxs-lookup"><span data-stu-id="38800-176">If the **PersistBlockType** value is not one of the ones defined here, the **PersistData** block is ignored and processing is continued until either a PERSIST_SENTINEL **PersistID** is processed or the end of the stream is reached.</span></span> 
  
<span data-ttu-id="38800-177">**PersistElementBlock**</span><span class="sxs-lookup"><span data-stu-id="38800-177">**PersistElementBlock**</span></span>

|<span data-ttu-id="38800-178">**名称**</span><span class="sxs-lookup"><span data-stu-id="38800-178">**Name**</span></span>|<span data-ttu-id="38800-179">**类型**</span><span class="sxs-lookup"><span data-stu-id="38800-179">**Type**</span></span>|<span data-ttu-id="38800-180">**大小**</span><span class="sxs-lookup"><span data-stu-id="38800-180">**Size**</span></span>|<span data-ttu-id="38800-181">**说明**</span><span class="sxs-lookup"><span data-stu-id="38800-181">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38800-182">**ElementID**</span><span class="sxs-lookup"><span data-stu-id="38800-182">**ElementID**</span></span> <br/> |<span data-ttu-id="38800-183">WORD</span><span class="sxs-lookup"><span data-stu-id="38800-183">WORD</span></span>  <br/> |<span data-ttu-id="38800-184">2</span><span class="sxs-lookup"><span data-stu-id="38800-184">2</span></span>  <br/> |<span data-ttu-id="38800-185">指定此 **PersistElement** 块的类型标识符值。</span><span class="sxs-lookup"><span data-stu-id="38800-185">Specifies the type identifier value for this **PersistElement** block.</span></span> <span data-ttu-id="38800-186">有关有效值的列表，请参阅"PersistElementType 值"表。</span><span class="sxs-lookup"><span data-stu-id="38800-186">See the "PersistElementType Values" table for a list of valid values.</span></span>  <br/> |
|<span data-ttu-id="38800-187">**ElementDataSize**</span><span class="sxs-lookup"><span data-stu-id="38800-187">**ElementDataSize**</span></span> <br/> |<span data-ttu-id="38800-188">WORD</span><span class="sxs-lookup"><span data-stu-id="38800-188">WORD</span></span>  <br/> |<span data-ttu-id="38800-189">2</span><span class="sxs-lookup"><span data-stu-id="38800-189">2</span></span>  <br/> |<span data-ttu-id="38800-190">指定 **ElementData** 字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="38800-190">Specifies the size, in bytes, of the **ElementData** field.</span></span>  <br/> |
|<span data-ttu-id="38800-191">**ElementData**</span><span class="sxs-lookup"><span data-stu-id="38800-191">**ElementData**</span></span> <br/> |<span data-ttu-id="38800-192">二进制数据数组</span><span class="sxs-lookup"><span data-stu-id="38800-192">array of binary data</span></span>  <br/> |<span data-ttu-id="38800-193">变量</span><span class="sxs-lookup"><span data-stu-id="38800-193">variable</span></span>  <br/> |<span data-ttu-id="38800-194">包含此 **PersistID**  +  **ElementID 对** 的数据。</span><span class="sxs-lookup"><span data-stu-id="38800-194">Contains the data for this **PersistID** + **ElementID** pair.</span></span>  <br/> |
   
<span data-ttu-id="38800-195">**PersistElementType 值**</span><span class="sxs-lookup"><span data-stu-id="38800-195">**PersistElementType Values**</span></span>

|<span data-ttu-id="38800-196">**名称**</span><span class="sxs-lookup"><span data-stu-id="38800-196">**Name**</span></span>|<span data-ttu-id="38800-197">**值**</span><span class="sxs-lookup"><span data-stu-id="38800-197">**Value**</span></span>|<span data-ttu-id="38800-198">**ElementDataSize 的值**</span><span class="sxs-lookup"><span data-stu-id="38800-198">**Value of ElementDataSize**</span></span>|<span data-ttu-id="38800-199">**说明**</span><span class="sxs-lookup"><span data-stu-id="38800-199">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38800-200">RSF_ELID_HEADER</span><span class="sxs-lookup"><span data-stu-id="38800-200">RSF_ELID_HEADER</span></span>  <br/> |<span data-ttu-id="38800-201">0x0002</span><span class="sxs-lookup"><span data-stu-id="38800-201">0x0002</span></span>  <br/> |<span data-ttu-id="38800-202">0x0004</span><span class="sxs-lookup"><span data-stu-id="38800-202">0x0004</span></span>  <br/> |<span data-ttu-id="38800-203">指示此块的 **ElementData** 字段包含 DWORD 标头值。</span><span class="sxs-lookup"><span data-stu-id="38800-203">Indicates that this block's **ElementData** field contains a DWORD Header value.</span></span> <span data-ttu-id="38800-204">如何解释此值取决于块的 **PersistID** 类型。</span><span class="sxs-lookup"><span data-stu-id="38800-204">How this value is interpreted depends on the block's **PersistID** type.</span></span>  <br/> <span data-ttu-id="38800-205">对于 [[MS-OXOSFLD] 中](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb.aspx)指定的所有 **PersistID** 类型，此值为零。</span><span class="sxs-lookup"><span data-stu-id="38800-205">For all **PersistID** types specified in [[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb.aspx), this value is zero.</span></span>  <br/> |
|<span data-ttu-id="38800-206">RSF_ELID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="38800-206">RSF_ELID_ENTRYID</span></span>  <br/> |<span data-ttu-id="38800-207">0x0001</span><span class="sxs-lookup"><span data-stu-id="38800-207">0x0001</span></span>  <br/> |<span data-ttu-id="38800-208">变量</span><span class="sxs-lookup"><span data-stu-id="38800-208">variable</span></span>  <br/> |<span data-ttu-id="38800-209">指示此块包含 **由 PersistID** 指定的文件夹的 **EntryID。**</span><span class="sxs-lookup"><span data-stu-id="38800-209">Indicates that this block contains the **EntryID** of the folder specified by **PersistID**.</span></span>  <br/> |
|<span data-ttu-id="38800-210">ELEMENT_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="38800-210">ELEMENT_SENTINEL</span></span>  <br/> |<span data-ttu-id="38800-211">0x0000</span><span class="sxs-lookup"><span data-stu-id="38800-211">0x0000</span></span>  <br/> |<span data-ttu-id="38800-212">0x0000</span><span class="sxs-lookup"><span data-stu-id="38800-212">0x0000</span></span>  <br/> |<span data-ttu-id="38800-213">指示不再处理 **PersistElement** 块。</span><span class="sxs-lookup"><span data-stu-id="38800-213">Indicates that no more **PersistElement** blocks will be processed.</span></span>  <br/> |
   
<span data-ttu-id="38800-214">如果 **PersistElementType** 值不是此处定义的值之一，将忽略 **PersistElement** 块，并继续进行处理，直到处理 ELEMENT_SENTINEL **ElementID** 或到达流的末尾。</span><span class="sxs-lookup"><span data-stu-id="38800-214">If the **PersistElementType** value is not one of the ones defined here, the **PersistElement** block is ignored and processing is continued until either an ELEMENT_SENTINEL **ElementID** is processed or the end of the stream is reached.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="38800-215">相关资源</span><span class="sxs-lookup"><span data-stu-id="38800-215">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="38800-216">协议规范</span><span class="sxs-lookup"><span data-stu-id="38800-216">Protocol specifications</span></span>

<span data-ttu-id="38800-217">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38800-217">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38800-218">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="38800-218">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="38800-219">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38800-219">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38800-220">允许/阻止列表的处理和垃圾邮件的确定。</span><span class="sxs-lookup"><span data-stu-id="38800-220">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
<span data-ttu-id="38800-221">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38800-221">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38800-222">指定用于创建和定位邮箱中特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="38800-222">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="38800-223">[[MS-OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38800-223">[[MS-OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38800-224">标识并标记旨在欺骗收件人将敏感信息泄露 (例如密码和其他个人信息) 到不可信来源的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="38800-224">Identifies and marks email messages that are designed to trick recipients into divulging sensitive information (such as passwords and other personal information) to a non-trustworthy source.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="38800-225">头文件</span><span class="sxs-lookup"><span data-stu-id="38800-225">Header files</span></span>

<span data-ttu-id="38800-226">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="38800-226">Mapitags.h</span></span>
  
> <span data-ttu-id="38800-227">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="38800-227">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="38800-228">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="38800-228">Mapidefs.h</span></span>
  
> <span data-ttu-id="38800-229">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="38800-229">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="38800-230">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38800-230">See also</span></span>



[<span data-ttu-id="38800-231">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="38800-231">MAPI Property Overview</span></span>](mapi-property-overview.md)
  
[<span data-ttu-id="38800-232">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="38800-232">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="38800-233">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="38800-233">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="38800-234">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="38800-234">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

