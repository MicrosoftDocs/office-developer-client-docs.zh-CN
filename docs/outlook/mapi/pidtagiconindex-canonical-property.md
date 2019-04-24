---
title: PidTagIconIndex 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIconIndex
api_type:
- HeaderDef
ms.assetid: 35bb0d6d-41d4-47d6-b161-be3721894201
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 35d9d0a50539f8aab2d26730dd4e4544c2535e60
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346618"
---
# <a name="pidtagiconindex-canonical-property"></a><span data-ttu-id="f3e21-103">PidTagIconIndex 规范属性</span><span class="sxs-lookup"><span data-stu-id="f3e21-103">PidTagIconIndex Canonical Property</span></span>

  
  
<span data-ttu-id="f3e21-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3e21-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3e21-105">包含一个数字, 用于指示在显示一组电子邮件对象时要使用哪个图标。</span><span class="sxs-lookup"><span data-stu-id="f3e21-105">Contains a number that indicates which icon to use when you display a group of email objects.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f3e21-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f3e21-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f3e21-107">PR_ICON_INDEX</span><span class="sxs-lookup"><span data-stu-id="f3e21-107">PR_ICON_INDEX</span></span>  <br/> |
|<span data-ttu-id="f3e21-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f3e21-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f3e21-109">0x1080</span><span class="sxs-lookup"><span data-stu-id="f3e21-109">0x1080</span></span>  <br/> |
|<span data-ttu-id="f3e21-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f3e21-110">Data type:</span></span>  <br/> |<span data-ttu-id="f3e21-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f3e21-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f3e21-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f3e21-112">Area:</span></span>  <br/> |<span data-ttu-id="f3e21-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f3e21-114">注解</span><span class="sxs-lookup"><span data-stu-id="f3e21-114">Remarks</span></span>

<span data-ttu-id="f3e21-115">此属性 (如果存在) 是对客户端的提示。</span><span class="sxs-lookup"><span data-stu-id="f3e21-115">This property, if it exists, is a hint to the client.</span></span> <span data-ttu-id="f3e21-116">客户端可能会忽略此属性的值。</span><span class="sxs-lookup"><span data-stu-id="f3e21-116">The client may ignore the value of this property.</span></span> 
  
|<span data-ttu-id="f3e21-117">**邮件项目状态**</span><span class="sxs-lookup"><span data-stu-id="f3e21-117">**Mail item state**</span></span>|<span data-ttu-id="f3e21-118">**图标索引**</span><span class="sxs-lookup"><span data-stu-id="f3e21-118">**Icon Index**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f3e21-119">新邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-119">New mail</span></span>  <br/> |<span data-ttu-id="f3e21-120">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="f3e21-120">0xFFFFFFFF</span></span>  <br/> |
|<span data-ttu-id="f3e21-121">帖子</span><span class="sxs-lookup"><span data-stu-id="f3e21-121">Post</span></span>  <br/> |<span data-ttu-id="f3e21-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="f3e21-122">0x00000001</span></span>  <br/> |
|<span data-ttu-id="f3e21-123">其他</span><span class="sxs-lookup"><span data-stu-id="f3e21-123">Other</span></span>  <br/> |<span data-ttu-id="f3e21-124">0x00000003</span><span class="sxs-lookup"><span data-stu-id="f3e21-124">0x00000003</span></span>  <br/> |
|<span data-ttu-id="f3e21-125">阅读邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-125">Read mail</span></span>  <br/> |<span data-ttu-id="f3e21-126">0x00000100</span><span class="sxs-lookup"><span data-stu-id="f3e21-126">0x00000100</span></span>  <br/> |
|<span data-ttu-id="f3e21-127">未读邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-127">Unread mail</span></span>  <br/> |<span data-ttu-id="f3e21-128">0x00000101</span><span class="sxs-lookup"><span data-stu-id="f3e21-128">0x00000101</span></span>  <br/> |
|<span data-ttu-id="f3e21-129">提交的邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-129">Submitted mail</span></span>  <br/> |<span data-ttu-id="f3e21-130">0x00000102</span><span class="sxs-lookup"><span data-stu-id="f3e21-130">0x00000102</span></span>  <br/> |
|<span data-ttu-id="f3e21-131">未发送邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-131">Unsent mail</span></span>  <br/> |<span data-ttu-id="f3e21-132">0x00000103</span><span class="sxs-lookup"><span data-stu-id="f3e21-132">0x00000103</span></span>  <br/> |
|<span data-ttu-id="f3e21-133">回执邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-133">Receipt mail</span></span>  <br/> |<span data-ttu-id="f3e21-134">0x00000104</span><span class="sxs-lookup"><span data-stu-id="f3e21-134">0x00000104</span></span>  <br/> |
|<span data-ttu-id="f3e21-135">已答复邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-135">Replied mail</span></span>  <br/> |<span data-ttu-id="f3e21-136">0x00000105</span><span class="sxs-lookup"><span data-stu-id="f3e21-136">0x00000105</span></span>  <br/> |
|<span data-ttu-id="f3e21-137">转发邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-137">Forwarded mail</span></span>  <br/> |<span data-ttu-id="f3e21-138">0x00000106</span><span class="sxs-lookup"><span data-stu-id="f3e21-138">0x00000106</span></span>  <br/> |
|<span data-ttu-id="f3e21-139">远程邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-139">Remote mail</span></span>  <br/> |<span data-ttu-id="f3e21-140">0x00000107</span><span class="sxs-lookup"><span data-stu-id="f3e21-140">0x00000107</span></span>  <br/> |
|<span data-ttu-id="f3e21-141">传递邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-141">Delivery mail</span></span>  <br/> |<span data-ttu-id="f3e21-142">0x00000108</span><span class="sxs-lookup"><span data-stu-id="f3e21-142">0x00000108</span></span>  <br/> |
|<span data-ttu-id="f3e21-143">阅读邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-143">Read mail</span></span>  <br/> |<span data-ttu-id="f3e21-144">0x00000109</span><span class="sxs-lookup"><span data-stu-id="f3e21-144">0x00000109</span></span>  <br/> |
|<span data-ttu-id="f3e21-145">Nondelivery 邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-145">Nondelivery mail</span></span>  <br/> |<span data-ttu-id="f3e21-146">0x0000010A</span><span class="sxs-lookup"><span data-stu-id="f3e21-146">0x0000010A</span></span>  <br/> |
|<span data-ttu-id="f3e21-147">未读邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-147">Nonread mail</span></span>  <br/> |<span data-ttu-id="f3e21-148">0x0000010B</span><span class="sxs-lookup"><span data-stu-id="f3e21-148">0x0000010B</span></span>  <br/> |
|<span data-ttu-id="f3e21-149">Recall_S 邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-149">Recall_S mail</span></span>  <br/> |<span data-ttu-id="f3e21-150">0x0000010C</span><span class="sxs-lookup"><span data-stu-id="f3e21-150">0x0000010C</span></span>  <br/> |
|<span data-ttu-id="f3e21-151">Recall_F 邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-151">Recall_F mail</span></span>  <br/> |<span data-ttu-id="f3e21-152">0x0000010D</span><span class="sxs-lookup"><span data-stu-id="f3e21-152">0x0000010D</span></span>  <br/> |
|<span data-ttu-id="f3e21-153">跟踪邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-153">Tracking mail</span></span>  <br/> |<span data-ttu-id="f3e21-154">0x0000010E</span><span class="sxs-lookup"><span data-stu-id="f3e21-154">0x0000010E</span></span>  <br/> |
|<span data-ttu-id="f3e21-155">外出邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-155">Out of office mail</span></span>  <br/> |<span data-ttu-id="f3e21-156">0x0000011B</span><span class="sxs-lookup"><span data-stu-id="f3e21-156">0x0000011B</span></span>  <br/> |
|<span data-ttu-id="f3e21-157">撤回邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-157">Recall mail</span></span>  <br/> |<span data-ttu-id="f3e21-158">0x0000011C</span><span class="sxs-lookup"><span data-stu-id="f3e21-158">0x0000011C</span></span>  <br/> |
|<span data-ttu-id="f3e21-159">跟踪的邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-159">Tracked mail</span></span>  <br/> |<span data-ttu-id="f3e21-160">0x00000130</span><span class="sxs-lookup"><span data-stu-id="f3e21-160">0x00000130</span></span>  <br/> |
|<span data-ttu-id="f3e21-161">Contact</span><span class="sxs-lookup"><span data-stu-id="f3e21-161">Contact</span></span>  <br/> |<span data-ttu-id="f3e21-162">0x00000200</span><span class="sxs-lookup"><span data-stu-id="f3e21-162">0x00000200</span></span>  <br/> |
|<span data-ttu-id="f3e21-163">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="f3e21-163">Distribution list</span></span>  <br/> |<span data-ttu-id="f3e21-164">0x00000202</span><span class="sxs-lookup"><span data-stu-id="f3e21-164">0x00000202</span></span>  <br/> |
|<span data-ttu-id="f3e21-165">粘滞便笺蓝色</span><span class="sxs-lookup"><span data-stu-id="f3e21-165">Sticky note blue</span></span>  <br/> |<span data-ttu-id="f3e21-166">0x00000300</span><span class="sxs-lookup"><span data-stu-id="f3e21-166">0x00000300</span></span>  <br/> |
|<span data-ttu-id="f3e21-167">绿色便笺</span><span class="sxs-lookup"><span data-stu-id="f3e21-167">Sticky note green</span></span>  <br/> |<span data-ttu-id="f3e21-168">0x00000301</span><span class="sxs-lookup"><span data-stu-id="f3e21-168">0x00000301</span></span>  <br/> |
|<span data-ttu-id="f3e21-169">粘滞便笺粉红色</span><span class="sxs-lookup"><span data-stu-id="f3e21-169">Sticky note pink</span></span>  <br/> |<span data-ttu-id="f3e21-170">0x00000302</span><span class="sxs-lookup"><span data-stu-id="f3e21-170">0x00000302</span></span>  <br/> |
|<span data-ttu-id="f3e21-171">粘滞便笺黄色</span><span class="sxs-lookup"><span data-stu-id="f3e21-171">Sticky note yellow</span></span>  <br/> |<span data-ttu-id="f3e21-172">0x00000303</span><span class="sxs-lookup"><span data-stu-id="f3e21-172">0x00000303</span></span>  <br/> |
|<span data-ttu-id="f3e21-173">粘滞便笺白色</span><span class="sxs-lookup"><span data-stu-id="f3e21-173">Sticky note white</span></span>  <br/> |<span data-ttu-id="f3e21-174">0x00000304</span><span class="sxs-lookup"><span data-stu-id="f3e21-174">0x00000304</span></span>  <br/> |
|<span data-ttu-id="f3e21-175">单个实例约会</span><span class="sxs-lookup"><span data-stu-id="f3e21-175">Single instance appointment</span></span>  <br/> |<span data-ttu-id="f3e21-176">0x00000400</span><span class="sxs-lookup"><span data-stu-id="f3e21-176">0x00000400</span></span>  <br/> |
|<span data-ttu-id="f3e21-177">定期约会</span><span class="sxs-lookup"><span data-stu-id="f3e21-177">Recurring appointment</span></span>  <br/> |<span data-ttu-id="f3e21-178">0x00000401</span><span class="sxs-lookup"><span data-stu-id="f3e21-178">0x00000401</span></span>  <br/> |
|<span data-ttu-id="f3e21-179">单实例会议</span><span class="sxs-lookup"><span data-stu-id="f3e21-179">Single instance meeting</span></span>  <br/> |<span data-ttu-id="f3e21-180">0x00000402</span><span class="sxs-lookup"><span data-stu-id="f3e21-180">0x00000402</span></span>  <br/> |
|<span data-ttu-id="f3e21-181">定期会议</span><span class="sxs-lookup"><span data-stu-id="f3e21-181">Recurring meeting</span></span>  <br/> |<span data-ttu-id="f3e21-182">0x00000403</span><span class="sxs-lookup"><span data-stu-id="f3e21-182">0x00000403</span></span>  <br/> |
|<span data-ttu-id="f3e21-183">会议请求</span><span class="sxs-lookup"><span data-stu-id="f3e21-183">Meeting request</span></span>  <br/> |<span data-ttu-id="f3e21-184">0x00000404</span><span class="sxs-lookup"><span data-stu-id="f3e21-184">0x00000404</span></span>  <br/> |
|<span data-ttu-id="f3e21-185">接受</span><span class="sxs-lookup"><span data-stu-id="f3e21-185">Accept</span></span>  <br/> |<span data-ttu-id="f3e21-186">0x00000405</span><span class="sxs-lookup"><span data-stu-id="f3e21-186">0x00000405</span></span>  <br/> |
|<span data-ttu-id="f3e21-187">拒绝</span><span class="sxs-lookup"><span data-stu-id="f3e21-187">Decline</span></span>  <br/> |<span data-ttu-id="f3e21-188">0x00000406</span><span class="sxs-lookup"><span data-stu-id="f3e21-188">0x00000406</span></span>  <br/> |
|<span data-ttu-id="f3e21-189">Tentativly</span><span class="sxs-lookup"><span data-stu-id="f3e21-189">Tentativly</span></span>  <br/> |<span data-ttu-id="f3e21-190">0x00000407</span><span class="sxs-lookup"><span data-stu-id="f3e21-190">0x00000407</span></span>  <br/> |
|<span data-ttu-id="f3e21-191">取消</span><span class="sxs-lookup"><span data-stu-id="f3e21-191">Cancellation</span></span>  <br/> |<span data-ttu-id="f3e21-192">0x00000408</span><span class="sxs-lookup"><span data-stu-id="f3e21-192">0x00000408</span></span>  <br/> |
|<span data-ttu-id="f3e21-193">信息更新</span><span class="sxs-lookup"><span data-stu-id="f3e21-193">Informational update</span></span>  <br/> |<span data-ttu-id="f3e21-194">0x00000409</span><span class="sxs-lookup"><span data-stu-id="f3e21-194">0x00000409</span></span>  <br/> |
|<span data-ttu-id="f3e21-195">任务/任务</span><span class="sxs-lookup"><span data-stu-id="f3e21-195">Task/task</span></span>  <br/> |<span data-ttu-id="f3e21-196">0x00000500</span><span class="sxs-lookup"><span data-stu-id="f3e21-196">0x00000500</span></span>  <br/> |
|<span data-ttu-id="f3e21-197">未分配的定期任务</span><span class="sxs-lookup"><span data-stu-id="f3e21-197">Unassigned recurring task</span></span>  <br/> |<span data-ttu-id="f3e21-198">0x00000501</span><span class="sxs-lookup"><span data-stu-id="f3e21-198">0x00000501</span></span>  <br/> |
|<span data-ttu-id="f3e21-199">受托人的任务</span><span class="sxs-lookup"><span data-stu-id="f3e21-199">Assignee's task</span></span>  <br/> |<span data-ttu-id="f3e21-200">0x00000502</span><span class="sxs-lookup"><span data-stu-id="f3e21-200">0x00000502</span></span>  <br/> |
|<span data-ttu-id="f3e21-201">Assigner 的任务</span><span class="sxs-lookup"><span data-stu-id="f3e21-201">Assigner's task</span></span>  <br/> |<span data-ttu-id="f3e21-202">0x00000503</span><span class="sxs-lookup"><span data-stu-id="f3e21-202">0x00000503</span></span>  <br/> |
|<span data-ttu-id="f3e21-203">任务请求</span><span class="sxs-lookup"><span data-stu-id="f3e21-203">Task request</span></span>  <br/> |<span data-ttu-id="f3e21-204">0x00000504</span><span class="sxs-lookup"><span data-stu-id="f3e21-204">0x00000504</span></span>  <br/> |
|<span data-ttu-id="f3e21-205">任务接受</span><span class="sxs-lookup"><span data-stu-id="f3e21-205">Task acceptance</span></span>  <br/> |<span data-ttu-id="f3e21-206">0x00000505</span><span class="sxs-lookup"><span data-stu-id="f3e21-206">0x00000505</span></span>  <br/> |
|<span data-ttu-id="f3e21-207">任务拒绝</span><span class="sxs-lookup"><span data-stu-id="f3e21-207">Task rejection</span></span>  <br/> |<span data-ttu-id="f3e21-208">0x00000506</span><span class="sxs-lookup"><span data-stu-id="f3e21-208">0x00000506</span></span>  <br/> |
|<span data-ttu-id="f3e21-209">日记对话</span><span class="sxs-lookup"><span data-stu-id="f3e21-209">Journal conversation</span></span>  <br/> |<span data-ttu-id="f3e21-210">0x00000601</span><span class="sxs-lookup"><span data-stu-id="f3e21-210">0x00000601</span></span>  <br/> |
|<span data-ttu-id="f3e21-211">日记电子邮件</span><span class="sxs-lookup"><span data-stu-id="f3e21-211">Journal email message</span></span>  <br/> |<span data-ttu-id="f3e21-212">0x00000602</span><span class="sxs-lookup"><span data-stu-id="f3e21-212">0x00000602</span></span>  <br/> |
|<span data-ttu-id="f3e21-213">日记会议请求</span><span class="sxs-lookup"><span data-stu-id="f3e21-213">Journal meeting request</span></span>  <br/> |<span data-ttu-id="f3e21-214">0x00000603</span><span class="sxs-lookup"><span data-stu-id="f3e21-214">0x00000603</span></span>  <br/> |
|<span data-ttu-id="f3e21-215">日记会议响应</span><span class="sxs-lookup"><span data-stu-id="f3e21-215">Journal meeting response</span></span>  <br/> |<span data-ttu-id="f3e21-216">0x00000604</span><span class="sxs-lookup"><span data-stu-id="f3e21-216">0x00000604</span></span>  <br/> |
|<span data-ttu-id="f3e21-217">日记任务请求</span><span class="sxs-lookup"><span data-stu-id="f3e21-217">Journal task request</span></span>  <br/> |<span data-ttu-id="f3e21-218">0x00000606</span><span class="sxs-lookup"><span data-stu-id="f3e21-218">0x00000606</span></span>  <br/> |
|<span data-ttu-id="f3e21-219">日记任务响应</span><span class="sxs-lookup"><span data-stu-id="f3e21-219">Journal task response</span></span>  <br/> |<span data-ttu-id="f3e21-220">0x00000607</span><span class="sxs-lookup"><span data-stu-id="f3e21-220">0x00000607</span></span>  <br/> |
|<span data-ttu-id="f3e21-221">日记便笺</span><span class="sxs-lookup"><span data-stu-id="f3e21-221">Journal note</span></span>  <br/> |<span data-ttu-id="f3e21-222">0x00000608</span><span class="sxs-lookup"><span data-stu-id="f3e21-222">0x00000608</span></span>  <br/> |
|<span data-ttu-id="f3e21-223">日记传真</span><span class="sxs-lookup"><span data-stu-id="f3e21-223">Journal fax</span></span>  <br/> |<span data-ttu-id="f3e21-224">0x00000609</span><span class="sxs-lookup"><span data-stu-id="f3e21-224">0x00000609</span></span>  <br/> |
|<span data-ttu-id="f3e21-225">日记电话呼叫</span><span class="sxs-lookup"><span data-stu-id="f3e21-225">Journal phone call</span></span>  <br/> |<span data-ttu-id="f3e21-226">0x0000060A</span><span class="sxs-lookup"><span data-stu-id="f3e21-226">0x0000060A</span></span>  <br/> |
|<span data-ttu-id="f3e21-227">日记字母</span><span class="sxs-lookup"><span data-stu-id="f3e21-227">Journal letter</span></span>  <br/> |<span data-ttu-id="f3e21-228">0x0000060C</span><span class="sxs-lookup"><span data-stu-id="f3e21-228">0x0000060C</span></span>  <br/> |
|<span data-ttu-id="f3e21-229">日记 Microsoft Office Word</span><span class="sxs-lookup"><span data-stu-id="f3e21-229">Journal Microsoft Office Word</span></span>  <br/> |<span data-ttu-id="f3e21-230">0x0000060D</span><span class="sxs-lookup"><span data-stu-id="f3e21-230">0x0000060D</span></span>  <br/> |
|<span data-ttu-id="f3e21-231">日记 Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="f3e21-231">Journal Microsoft Office Excel</span></span>  <br/> |<span data-ttu-id="f3e21-232">0x0000060E</span><span class="sxs-lookup"><span data-stu-id="f3e21-232">0x0000060E</span></span>  <br/> |
|<span data-ttu-id="f3e21-233">日记本 Microsoft Office PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f3e21-233">Journal Microsoft Office PowerPoint</span></span>  <br/> |<span data-ttu-id="f3e21-234">0x0000060F</span><span class="sxs-lookup"><span data-stu-id="f3e21-234">0x0000060F</span></span>  <br/> |
|<span data-ttu-id="f3e21-235">日记 Microsoft Office Access</span><span class="sxs-lookup"><span data-stu-id="f3e21-235">Journal Microsoft Office Access</span></span>  <br/> |<span data-ttu-id="f3e21-236">0x00000610</span><span class="sxs-lookup"><span data-stu-id="f3e21-236">0x00000610</span></span>  <br/> |
|<span data-ttu-id="f3e21-237">日记文档</span><span class="sxs-lookup"><span data-stu-id="f3e21-237">Journal document</span></span>  <br/> |<span data-ttu-id="f3e21-238">0x00000612</span><span class="sxs-lookup"><span data-stu-id="f3e21-238">0x00000612</span></span>  <br/> |
|<span data-ttu-id="f3e21-239">日记会议</span><span class="sxs-lookup"><span data-stu-id="f3e21-239">Journal meeting</span></span>  <br/> |<span data-ttu-id="f3e21-240">0x00000613</span><span class="sxs-lookup"><span data-stu-id="f3e21-240">0x00000613</span></span>  <br/> |
|<span data-ttu-id="f3e21-241">日记会议取消</span><span class="sxs-lookup"><span data-stu-id="f3e21-241">Journal meeting cancellation</span></span>  <br/> |<span data-ttu-id="f3e21-242">0x00000614</span><span class="sxs-lookup"><span data-stu-id="f3e21-242">0x00000614</span></span>  <br/> |
|<span data-ttu-id="f3e21-243">日记远程会话</span><span class="sxs-lookup"><span data-stu-id="f3e21-243">Journal remote session</span></span>  <br/> |<span data-ttu-id="f3e21-244">0x00000615</span><span class="sxs-lookup"><span data-stu-id="f3e21-244">0x00000615</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="f3e21-245">相关资源</span><span class="sxs-lookup"><span data-stu-id="f3e21-245">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f3e21-246">协议规范</span><span class="sxs-lookup"><span data-stu-id="f3e21-246">Protocol specifications</span></span>

<span data-ttu-id="f3e21-247">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3e21-247">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f3e21-248">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f3e21-248">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f3e21-249">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3e21-249">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f3e21-250">指定在电子邮件对象上允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="f3e21-250">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
<span data-ttu-id="f3e21-251">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3e21-251">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f3e21-252">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="f3e21-252">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="f3e21-253">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3e21-253">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f3e21-254">指定在 "联系人" 和 "个人通讯组" 列表中允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="f3e21-254">Specifies the properties and operations that are permissible on contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f3e21-255">头文件</span><span class="sxs-lookup"><span data-stu-id="f3e21-255">Header files</span></span>

<span data-ttu-id="f3e21-256">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f3e21-256">Mapidefs.h</span></span>
  
> <span data-ttu-id="f3e21-257">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f3e21-257">Provides data type definitions.</span></span>
    
<span data-ttu-id="f3e21-258">Mapitags</span><span class="sxs-lookup"><span data-stu-id="f3e21-258">Mapitags.h</span></span>
  
> <span data-ttu-id="f3e21-259">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f3e21-259">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f3e21-260">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3e21-260">See also</span></span>



[<span data-ttu-id="f3e21-261">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f3e21-261">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f3e21-262">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f3e21-262">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f3e21-263">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f3e21-263">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f3e21-264">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f3e21-264">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

