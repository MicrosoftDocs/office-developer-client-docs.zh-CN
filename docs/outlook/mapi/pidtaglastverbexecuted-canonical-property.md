---
title: PidTagLastVerbExecuted 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLastVerbExecuted
api_type:
- HeaderDef
ms.assetid: 502f0261-697f-41bf-8530-75e1d0f503e5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9abd4eb955428595ebe41ab9b2c661303ee2779a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279613"
---
# <a name="pidtaglastverbexecuted-canonical-property"></a><span data-ttu-id="d9692-103">PidTagLastVerbExecuted 规范属性</span><span class="sxs-lookup"><span data-stu-id="d9692-103">PidTagLastVerbExecuted Canonical Property</span></span>

  
  
<span data-ttu-id="d9692-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9692-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9692-105">包含执行的最后一个动作。</span><span class="sxs-lookup"><span data-stu-id="d9692-105">Contains the last verb executed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d9692-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d9692-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d9692-107">PR_LAST_VERB_EXECUTED</span><span class="sxs-lookup"><span data-stu-id="d9692-107">PR_LAST_VERB_EXECUTED</span></span>  <br/> |
|<span data-ttu-id="d9692-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d9692-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d9692-109">0x1081</span><span class="sxs-lookup"><span data-stu-id="d9692-109">0x1081</span></span>  <br/> |
|<span data-ttu-id="d9692-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d9692-110">Data type:</span></span>  <br/> |<span data-ttu-id="d9692-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="d9692-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="d9692-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d9692-112">Area:</span></span>  <br/> |<span data-ttu-id="d9692-113">历史记录</span><span class="sxs-lookup"><span data-stu-id="d9692-113">History</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d9692-114">备注</span><span class="sxs-lookup"><span data-stu-id="d9692-114">Remarks</span></span>

<span data-ttu-id="d9692-115">此属性可以具有以下值之一：</span><span class="sxs-lookup"><span data-stu-id="d9692-115">This property can have one the following values:</span></span>
  
|<span data-ttu-id="d9692-116">**Verb**</span><span class="sxs-lookup"><span data-stu-id="d9692-116">**Verb**</span></span>|<span data-ttu-id="d9692-117">**属性值**</span><span class="sxs-lookup"><span data-stu-id="d9692-117">**Property value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d9692-118">文章</span><span class="sxs-lookup"><span data-stu-id="d9692-118">Post</span></span>  <br/> |<span data-ttu-id="d9692-119">0x00000001</span><span class="sxs-lookup"><span data-stu-id="d9692-119">0x00000001</span></span>  <br/> |
|<span data-ttu-id="d9692-120">其他</span><span class="sxs-lookup"><span data-stu-id="d9692-120">Other</span></span>  <br/> |<span data-ttu-id="d9692-121">0x00000003</span><span class="sxs-lookup"><span data-stu-id="d9692-121">0x00000003</span></span>  <br/> |
|<span data-ttu-id="d9692-122">阅读邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-122">Read mail</span></span>  <br/> |<span data-ttu-id="d9692-123">0x00000100</span><span class="sxs-lookup"><span data-stu-id="d9692-123">0x00000100</span></span>  <br/> |
|<span data-ttu-id="d9692-124">未读邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-124">Unread mail</span></span>  <br/> |<span data-ttu-id="d9692-125">0x00000101</span><span class="sxs-lookup"><span data-stu-id="d9692-125">0x00000101</span></span>  <br/> |
|<span data-ttu-id="d9692-126">提交的邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-126">Submitted mail</span></span>  <br/> |<span data-ttu-id="d9692-127">0x00000102</span><span class="sxs-lookup"><span data-stu-id="d9692-127">0x00000102</span></span>  <br/> |
|<span data-ttu-id="d9692-128">未发送的邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-128">Unsent mail</span></span>  <br/> |<span data-ttu-id="d9692-129">0x00000103</span><span class="sxs-lookup"><span data-stu-id="d9692-129">0x00000103</span></span>  <br/> |
|<span data-ttu-id="d9692-130">回执邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-130">Receipt mail</span></span>  <br/> |<span data-ttu-id="d9692-131">0x00000104</span><span class="sxs-lookup"><span data-stu-id="d9692-131">0x00000104</span></span>  <br/> |
|<span data-ttu-id="d9692-132">答复的邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-132">Replied mail</span></span>  <br/> |<span data-ttu-id="d9692-133">0x00000105</span><span class="sxs-lookup"><span data-stu-id="d9692-133">0x00000105</span></span>  <br/> |
|<span data-ttu-id="d9692-134">转发的邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-134">Forwarded mail</span></span>  <br/> |<span data-ttu-id="d9692-135">0x00000106</span><span class="sxs-lookup"><span data-stu-id="d9692-135">0x00000106</span></span>  <br/> |
|<span data-ttu-id="d9692-136">远程邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-136">Remote mail</span></span>  <br/> |<span data-ttu-id="d9692-137">0x00000107</span><span class="sxs-lookup"><span data-stu-id="d9692-137">0x00000107</span></span>  <br/> |
|<span data-ttu-id="d9692-138">送达回执</span><span class="sxs-lookup"><span data-stu-id="d9692-138">Delivery Receipt</span></span>  <br/> |<span data-ttu-id="d9692-139">0x00000108</span><span class="sxs-lookup"><span data-stu-id="d9692-139">0x00000108</span></span>  <br/> |
|<span data-ttu-id="d9692-140">已读回执</span><span class="sxs-lookup"><span data-stu-id="d9692-140">Read Receipt</span></span>  <br/> |<span data-ttu-id="d9692-141">0x00000109</span><span class="sxs-lookup"><span data-stu-id="d9692-141">0x00000109</span></span>  <br/> |
|<span data-ttu-id="d9692-142">未送达回执</span><span class="sxs-lookup"><span data-stu-id="d9692-142">Nondelivery Receipt</span></span>  <br/> |<span data-ttu-id="d9692-143">0x0000010A</span><span class="sxs-lookup"><span data-stu-id="d9692-143">0x0000010A</span></span>  <br/> |
|<span data-ttu-id="d9692-144">未读回执</span><span class="sxs-lookup"><span data-stu-id="d9692-144">Nonread Receipt</span></span>  <br/> |<span data-ttu-id="d9692-145">0x0000010B</span><span class="sxs-lookup"><span data-stu-id="d9692-145">0x0000010B</span></span>  <br/> |
|<span data-ttu-id="d9692-146">Recall_S邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-146">Recall_S mail</span></span>  <br/> |<span data-ttu-id="d9692-147">0x0000010C</span><span class="sxs-lookup"><span data-stu-id="d9692-147">0x0000010C</span></span>  <br/> |
|<span data-ttu-id="d9692-148">Recall_F邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-148">Recall_F mail</span></span>  <br/> |<span data-ttu-id="d9692-149">0x0000010D</span><span class="sxs-lookup"><span data-stu-id="d9692-149">0x0000010D</span></span>  <br/> |
|<span data-ttu-id="d9692-150">跟踪邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-150">Tracking mail</span></span>  <br/> |<span data-ttu-id="d9692-151">0x0000010E</span><span class="sxs-lookup"><span data-stu-id="d9692-151">0x0000010E</span></span>  <br/> |
|<span data-ttu-id="d9692-152">外出Office邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-152">Out of Office mail</span></span>  <br/> |<span data-ttu-id="d9692-153">0x0000011B</span><span class="sxs-lookup"><span data-stu-id="d9692-153">0x0000011B</span></span>  <br/> |
|<span data-ttu-id="d9692-154">撤回邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-154">Recall mail</span></span>  <br/> |<span data-ttu-id="d9692-155">0x0000011C</span><span class="sxs-lookup"><span data-stu-id="d9692-155">0x0000011C</span></span>  <br/> |
|<span data-ttu-id="d9692-156">跟踪的邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-156">Tracked mail</span></span>  <br/> |<span data-ttu-id="d9692-157">0x00000139</span><span class="sxs-lookup"><span data-stu-id="d9692-157">0x00000139</span></span>  <br/> |
|<span data-ttu-id="d9692-158">联系人</span><span class="sxs-lookup"><span data-stu-id="d9692-158">Contact</span></span>  <br/> |<span data-ttu-id="d9692-159">0x00000200</span><span class="sxs-lookup"><span data-stu-id="d9692-159">0x00000200</span></span>  <br/> |
|<span data-ttu-id="d9692-160">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="d9692-160">Distribution List</span></span>  <br/> |<span data-ttu-id="d9692-161">0x00000201</span><span class="sxs-lookup"><span data-stu-id="d9692-161">0x00000201</span></span>  <br/> |
|<span data-ttu-id="d9692-162">粘滞便笺，蓝色</span><span class="sxs-lookup"><span data-stu-id="d9692-162">Sticky Note, Blue</span></span>  <br/> |<span data-ttu-id="d9692-163">0x00000300</span><span class="sxs-lookup"><span data-stu-id="d9692-163">0x00000300</span></span>  <br/> |
|<span data-ttu-id="d9692-164">粘滞便笺，绿色</span><span class="sxs-lookup"><span data-stu-id="d9692-164">Sticky Note, Green</span></span>  <br/> |<span data-ttu-id="d9692-165">0x00000301</span><span class="sxs-lookup"><span data-stu-id="d9692-165">0x00000301</span></span>  <br/> |
|<span data-ttu-id="d9692-166">粘滞便笺，粉色</span><span class="sxs-lookup"><span data-stu-id="d9692-166">Sticky Note, Pink</span></span>  <br/> |<span data-ttu-id="d9692-167">0x00000302</span><span class="sxs-lookup"><span data-stu-id="d9692-167">0x00000302</span></span>  <br/> |
|<span data-ttu-id="d9692-168">粘滞便笺，黄色</span><span class="sxs-lookup"><span data-stu-id="d9692-168">Sticky Note, Yellow</span></span>  <br/> |<span data-ttu-id="d9692-169">0x00000303</span><span class="sxs-lookup"><span data-stu-id="d9692-169">0x00000303</span></span>  <br/> |
|<span data-ttu-id="d9692-170">粘滞便笺，白色</span><span class="sxs-lookup"><span data-stu-id="d9692-170">Sticky Note, White</span></span>  <br/> |<span data-ttu-id="d9692-171">0x00000304</span><span class="sxs-lookup"><span data-stu-id="d9692-171">0x00000304</span></span>  <br/> |
|<span data-ttu-id="d9692-172">单实例约会</span><span class="sxs-lookup"><span data-stu-id="d9692-172">Single Instance Appointment</span></span>  <br/> |<span data-ttu-id="d9692-173">0x00000400</span><span class="sxs-lookup"><span data-stu-id="d9692-173">0x00000400</span></span>  <br/> |
|<span data-ttu-id="d9692-174">定期约会</span><span class="sxs-lookup"><span data-stu-id="d9692-174">Recurring Appointment</span></span>  <br/> |<span data-ttu-id="d9692-175">0x00000401</span><span class="sxs-lookup"><span data-stu-id="d9692-175">0x00000401</span></span>  <br/> |
|<span data-ttu-id="d9692-176">单实例会议</span><span class="sxs-lookup"><span data-stu-id="d9692-176">Single Instance Meeting</span></span>  <br/> |<span data-ttu-id="d9692-177">0x00000402</span><span class="sxs-lookup"><span data-stu-id="d9692-177">0x00000402</span></span>  <br/> |
|<span data-ttu-id="d9692-178">定期会议</span><span class="sxs-lookup"><span data-stu-id="d9692-178">Recurring Meeting</span></span>  <br/> |<span data-ttu-id="d9692-179">0x00000403</span><span class="sxs-lookup"><span data-stu-id="d9692-179">0x00000403</span></span>  <br/> |
|<span data-ttu-id="d9692-180">会议请求/完整更新</span><span class="sxs-lookup"><span data-stu-id="d9692-180">Meeting Request / Full Update</span></span>  <br/> |<span data-ttu-id="d9692-181">0x00000404</span><span class="sxs-lookup"><span data-stu-id="d9692-181">0x00000404</span></span>  <br/> |
|<span data-ttu-id="d9692-182">接受</span><span class="sxs-lookup"><span data-stu-id="d9692-182">Accept</span></span>  <br/> |<span data-ttu-id="d9692-183">0x00000405</span><span class="sxs-lookup"><span data-stu-id="d9692-183">0x00000405</span></span>  <br/> |
|<span data-ttu-id="d9692-184">拒绝</span><span class="sxs-lookup"><span data-stu-id="d9692-184">Decline</span></span>  <br/> |<span data-ttu-id="d9692-185">0x00000406</span><span class="sxs-lookup"><span data-stu-id="d9692-185">0x00000406</span></span>  <br/> |
|<span data-ttu-id="d9692-186">暂时接受</span><span class="sxs-lookup"><span data-stu-id="d9692-186">Tentatively Accept</span></span>  <br/> |<span data-ttu-id="d9692-187">0x00000407</span><span class="sxs-lookup"><span data-stu-id="d9692-187">0x00000407</span></span>  <br/> |
|<span data-ttu-id="d9692-188">Cancelation</span><span class="sxs-lookup"><span data-stu-id="d9692-188">Cancelation</span></span>  <br/> |<span data-ttu-id="d9692-189">0x00000408</span><span class="sxs-lookup"><span data-stu-id="d9692-189">0x00000408</span></span>  <br/> |
|<span data-ttu-id="d9692-190">信息更新</span><span class="sxs-lookup"><span data-stu-id="d9692-190">Informational Update</span></span>  <br/> |<span data-ttu-id="d9692-191">0x00000409</span><span class="sxs-lookup"><span data-stu-id="d9692-191">0x00000409</span></span>  <br/> |
|<span data-ttu-id="d9692-192">任务/任务更新</span><span class="sxs-lookup"><span data-stu-id="d9692-192">Task/Task Update</span></span>  <br/> |<span data-ttu-id="d9692-193">0x00000500</span><span class="sxs-lookup"><span data-stu-id="d9692-193">0x00000500</span></span>  <br/> |
|<span data-ttu-id="d9692-194">未分配定期任务</span><span class="sxs-lookup"><span data-stu-id="d9692-194">Unassigned Recurring Task</span></span>  <br/> |<span data-ttu-id="d9692-195">0x00000501</span><span class="sxs-lookup"><span data-stu-id="d9692-195">0x00000501</span></span>  <br/> |
|<span data-ttu-id="d9692-196">被分派人的任务</span><span class="sxs-lookup"><span data-stu-id="d9692-196">Assignee's Task</span></span>  <br/> |<span data-ttu-id="d9692-197">0x00000502</span><span class="sxs-lookup"><span data-stu-id="d9692-197">0x00000502</span></span>  <br/> |
|<span data-ttu-id="d9692-198">分配者的任务</span><span class="sxs-lookup"><span data-stu-id="d9692-198">Assigner's Task</span></span>  <br/> |<span data-ttu-id="d9692-199">0x00000503</span><span class="sxs-lookup"><span data-stu-id="d9692-199">0x00000503</span></span>  <br/> |
|<span data-ttu-id="d9692-200">任务要求</span><span class="sxs-lookup"><span data-stu-id="d9692-200">Task Request</span></span>  <br/> |<span data-ttu-id="d9692-201">0x00000504</span><span class="sxs-lookup"><span data-stu-id="d9692-201">0x00000504</span></span>  <br/> |
|<span data-ttu-id="d9692-202">任务接受</span><span class="sxs-lookup"><span data-stu-id="d9692-202">Task Acceptance</span></span>  <br/> |<span data-ttu-id="d9692-203">0x00000505</span><span class="sxs-lookup"><span data-stu-id="d9692-203">0x00000505</span></span>  <br/> |
|<span data-ttu-id="d9692-204">任务拒绝</span><span class="sxs-lookup"><span data-stu-id="d9692-204">Task Rejection</span></span>  <br/> |<span data-ttu-id="d9692-205">0x00000506</span><span class="sxs-lookup"><span data-stu-id="d9692-205">0x00000506</span></span>  <br/> |
|<span data-ttu-id="d9692-206">日记对话</span><span class="sxs-lookup"><span data-stu-id="d9692-206">Journal Conversation</span></span>  <br/> |<span data-ttu-id="d9692-207">0x00000601</span><span class="sxs-lookup"><span data-stu-id="d9692-207">0x00000601</span></span>  <br/> |
|<span data-ttu-id="d9692-208">日记电子邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-208">Journal Email Message</span></span>  <br/> |<span data-ttu-id="d9692-209">0x00000602</span><span class="sxs-lookup"><span data-stu-id="d9692-209">0x00000602</span></span>  <br/> |
|<span data-ttu-id="d9692-210">日记会议请求</span><span class="sxs-lookup"><span data-stu-id="d9692-210">Journal Meeting request</span></span>  <br/> |<span data-ttu-id="d9692-211">0x00000603</span><span class="sxs-lookup"><span data-stu-id="d9692-211">0x00000603</span></span>  <br/> |
|<span data-ttu-id="d9692-212">日记会议响应</span><span class="sxs-lookup"><span data-stu-id="d9692-212">Journal Meeting response</span></span>  <br/> |<span data-ttu-id="d9692-213">0x00000604</span><span class="sxs-lookup"><span data-stu-id="d9692-213">0x00000604</span></span>  <br/> |
|<span data-ttu-id="d9692-214">日记任务请求</span><span class="sxs-lookup"><span data-stu-id="d9692-214">Journal Task request</span></span>  <br/> |<span data-ttu-id="d9692-215">0x00000606</span><span class="sxs-lookup"><span data-stu-id="d9692-215">0x00000606</span></span>  <br/> |
|<span data-ttu-id="d9692-216">日记任务响应</span><span class="sxs-lookup"><span data-stu-id="d9692-216">Journal Task response</span></span>  <br/> |<span data-ttu-id="d9692-217">0x00000607</span><span class="sxs-lookup"><span data-stu-id="d9692-217">0x00000607</span></span>  <br/> |
|<span data-ttu-id="d9692-218">日记注释</span><span class="sxs-lookup"><span data-stu-id="d9692-218">Journal Note</span></span>  <br/> |<span data-ttu-id="d9692-219">0x00000608</span><span class="sxs-lookup"><span data-stu-id="d9692-219">0x00000608</span></span>  <br/> |
|<span data-ttu-id="d9692-220">日记传真</span><span class="sxs-lookup"><span data-stu-id="d9692-220">Journal Fax</span></span>  <br/> |<span data-ttu-id="d9692-221">0x00000609</span><span class="sxs-lookup"><span data-stu-id="d9692-221">0x00000609</span></span>  <br/> |
|<span data-ttu-id="d9692-222">日记电话呼叫</span><span class="sxs-lookup"><span data-stu-id="d9692-222">Journal Phone call</span></span>  <br/> |<span data-ttu-id="d9692-223">0x0000060A</span><span class="sxs-lookup"><span data-stu-id="d9692-223">0x0000060A</span></span>  <br/> |
|<span data-ttu-id="d9692-224">日记任务</span><span class="sxs-lookup"><span data-stu-id="d9692-224">Journal Task</span></span>  <br/> |<span data-ttu-id="d9692-225">0x0000060B</span><span class="sxs-lookup"><span data-stu-id="d9692-225">0x0000060B</span></span>  <br/> |
|<span data-ttu-id="d9692-226">日记信函</span><span class="sxs-lookup"><span data-stu-id="d9692-226">Journal Letter</span></span>  <br/> |<span data-ttu-id="d9692-227">0x0000060C</span><span class="sxs-lookup"><span data-stu-id="d9692-227">0x0000060C</span></span>  <br/> |
|<span data-ttu-id="d9692-228">Journal Microsoft Office Word</span><span class="sxs-lookup"><span data-stu-id="d9692-228">Journal Microsoft Office Word</span></span>  <br/> |<span data-ttu-id="d9692-229">0x0000060D</span><span class="sxs-lookup"><span data-stu-id="d9692-229">0x0000060D</span></span>  <br/> |
|<span data-ttu-id="d9692-230">日记Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="d9692-230">Journal Microsoft Office Excel</span></span>  <br/> |<span data-ttu-id="d9692-231">0x0000060E</span><span class="sxs-lookup"><span data-stu-id="d9692-231">0x0000060E</span></span>  <br/> |
|<span data-ttu-id="d9692-232">日记Microsoft Office PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9692-232">Journal Microsoft Office PowerPoint</span></span>  <br/> |<span data-ttu-id="d9692-233">0x0000060F</span><span class="sxs-lookup"><span data-stu-id="d9692-233">0x0000060F</span></span>  <br/> |
|<span data-ttu-id="d9692-234">Journal Microsoft Office Access</span><span class="sxs-lookup"><span data-stu-id="d9692-234">Journal Microsoft Office Access</span></span>  <br/> |<span data-ttu-id="d9692-235">0x00000610</span><span class="sxs-lookup"><span data-stu-id="d9692-235">0x00000610</span></span>  <br/> |
|<span data-ttu-id="d9692-236">日记文档</span><span class="sxs-lookup"><span data-stu-id="d9692-236">Journal Document</span></span>  <br/> |<span data-ttu-id="d9692-237">0x00000612</span><span class="sxs-lookup"><span data-stu-id="d9692-237">0x00000612</span></span>  <br/> |
|<span data-ttu-id="d9692-238">日记会议</span><span class="sxs-lookup"><span data-stu-id="d9692-238">Journal Meeting</span></span>  <br/> |<span data-ttu-id="d9692-239">0x00000613</span><span class="sxs-lookup"><span data-stu-id="d9692-239">0x00000613</span></span>  <br/> |
|<span data-ttu-id="d9692-240">日记会议取消</span><span class="sxs-lookup"><span data-stu-id="d9692-240">Journal Meeting cancellation</span></span>  <br/> |<span data-ttu-id="d9692-241">0x00000614</span><span class="sxs-lookup"><span data-stu-id="d9692-241">0x00000614</span></span>  <br/> |
|<span data-ttu-id="d9692-242">日记远程会话</span><span class="sxs-lookup"><span data-stu-id="d9692-242">Journal Remote session</span></span>  <br/> |<span data-ttu-id="d9692-243">0x00000615</span><span class="sxs-lookup"><span data-stu-id="d9692-243">0x00000615</span></span>  <br/> |
|<span data-ttu-id="d9692-244">新邮件</span><span class="sxs-lookup"><span data-stu-id="d9692-244">New mail</span></span>  <br/> |<span data-ttu-id="d9692-245">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="d9692-245">0xFFFFFFFF</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="d9692-246">相关资源</span><span class="sxs-lookup"><span data-stu-id="d9692-246">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d9692-247">协议规范</span><span class="sxs-lookup"><span data-stu-id="d9692-247">Protocol specifications</span></span>

<span data-ttu-id="d9692-248">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d9692-248">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d9692-249">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="d9692-249">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d9692-250">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d9692-250">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> 
### <a name="header-files"></a><span data-ttu-id="d9692-251">头文件</span><span class="sxs-lookup"><span data-stu-id="d9692-251">Header files</span></span>

<span data-ttu-id="d9692-252">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d9692-252">Mapidefs.h</span></span>
  
> <span data-ttu-id="d9692-253">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d9692-253">Provides data type definitions.</span></span>
    
<span data-ttu-id="d9692-254">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d9692-254">Mapitags.h</span></span>
  
> <span data-ttu-id="d9692-255">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d9692-255">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d9692-256">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9692-256">See also</span></span>



[<span data-ttu-id="d9692-257">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d9692-257">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d9692-258">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d9692-258">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d9692-259">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d9692-259">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d9692-260">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d9692-260">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

