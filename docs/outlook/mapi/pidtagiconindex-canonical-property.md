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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398106"
---
# <a name="pidtagiconindex-canonical-property"></a><span data-ttu-id="39ed3-103">PidTagIconIndex 规范属性</span><span class="sxs-lookup"><span data-stu-id="39ed3-103">PidTagIconIndex Canonical Property</span></span>

  
  
<span data-ttu-id="39ed3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="39ed3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="39ed3-105">包含一个数字，指示显示一组电子邮件对象时要使用的图标。</span><span class="sxs-lookup"><span data-stu-id="39ed3-105">Contains a number that indicates which icon to use when you display a group of email objects.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="39ed3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="39ed3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="39ed3-107">PR_ICON_INDEX</span><span class="sxs-lookup"><span data-stu-id="39ed3-107">PR_ICON_INDEX</span></span>  <br/> |
|<span data-ttu-id="39ed3-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="39ed3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="39ed3-109">0x1080</span><span class="sxs-lookup"><span data-stu-id="39ed3-109">0x1080</span></span>  <br/> |
|<span data-ttu-id="39ed3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="39ed3-110">Data type:</span></span>  <br/> |<span data-ttu-id="39ed3-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="39ed3-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="39ed3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="39ed3-112">Area:</span></span>  <br/> |<span data-ttu-id="39ed3-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="39ed3-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="39ed3-114">说明</span><span class="sxs-lookup"><span data-stu-id="39ed3-114">Remarks</span></span>

<span data-ttu-id="39ed3-115">此属性，如果存在，为对客户端的提示。</span><span class="sxs-lookup"><span data-stu-id="39ed3-115">This property, if it exists, is a hint to the client.</span></span> <span data-ttu-id="39ed3-116">客户端可能会忽略此属性的值。</span><span class="sxs-lookup"><span data-stu-id="39ed3-116">The client may ignore the value of this property.</span></span> 
  
|<span data-ttu-id="39ed3-117">**邮件项目状态**</span><span class="sxs-lookup"><span data-stu-id="39ed3-117">**Mail item state**</span></span>|<span data-ttu-id="39ed3-118">**图标索引**</span><span class="sxs-lookup"><span data-stu-id="39ed3-118">**Icon Index**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39ed3-119">新邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-119">New mail</span></span>  <br/> |<span data-ttu-id="39ed3-120">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="39ed3-120">0xFFFFFFFF</span></span>  <br/> |
|<span data-ttu-id="39ed3-121">帖子</span><span class="sxs-lookup"><span data-stu-id="39ed3-121">Post</span></span>  <br/> |<span data-ttu-id="39ed3-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="39ed3-122">0x00000001</span></span>  <br/> |
|<span data-ttu-id="39ed3-123">其他</span><span class="sxs-lookup"><span data-stu-id="39ed3-123">Other</span></span>  <br/> |<span data-ttu-id="39ed3-124">0x00000003</span><span class="sxs-lookup"><span data-stu-id="39ed3-124">0x00000003</span></span>  <br/> |
|<span data-ttu-id="39ed3-125">阅读邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-125">Read mail</span></span>  <br/> |<span data-ttu-id="39ed3-126">0x00000100</span><span class="sxs-lookup"><span data-stu-id="39ed3-126">0x00000100</span></span>  <br/> |
|<span data-ttu-id="39ed3-127">未读的邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-127">Unread mail</span></span>  <br/> |<span data-ttu-id="39ed3-128">0x00000101</span><span class="sxs-lookup"><span data-stu-id="39ed3-128">0x00000101</span></span>  <br/> |
|<span data-ttu-id="39ed3-129">提交的邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-129">Submitted mail</span></span>  <br/> |<span data-ttu-id="39ed3-130">0x00000102</span><span class="sxs-lookup"><span data-stu-id="39ed3-130">0x00000102</span></span>  <br/> |
|<span data-ttu-id="39ed3-131">未发送的邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-131">Unsent mail</span></span>  <br/> |<span data-ttu-id="39ed3-132">0x00000103</span><span class="sxs-lookup"><span data-stu-id="39ed3-132">0x00000103</span></span>  <br/> |
|<span data-ttu-id="39ed3-133">接收邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-133">Receipt mail</span></span>  <br/> |<span data-ttu-id="39ed3-134">0x00000104</span><span class="sxs-lookup"><span data-stu-id="39ed3-134">0x00000104</span></span>  <br/> |
|<span data-ttu-id="39ed3-135">答复的邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-135">Replied mail</span></span>  <br/> |<span data-ttu-id="39ed3-136">0x00000105</span><span class="sxs-lookup"><span data-stu-id="39ed3-136">0x00000105</span></span>  <br/> |
|<span data-ttu-id="39ed3-137">转发的邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-137">Forwarded mail</span></span>  <br/> |<span data-ttu-id="39ed3-138">0x00000106</span><span class="sxs-lookup"><span data-stu-id="39ed3-138">0x00000106</span></span>  <br/> |
|<span data-ttu-id="39ed3-139">远程邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-139">Remote mail</span></span>  <br/> |<span data-ttu-id="39ed3-140">0x00000107</span><span class="sxs-lookup"><span data-stu-id="39ed3-140">0x00000107</span></span>  <br/> |
|<span data-ttu-id="39ed3-141">传递邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-141">Delivery mail</span></span>  <br/> |<span data-ttu-id="39ed3-142">0x00000108</span><span class="sxs-lookup"><span data-stu-id="39ed3-142">0x00000108</span></span>  <br/> |
|<span data-ttu-id="39ed3-143">阅读邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-143">Read mail</span></span>  <br/> |<span data-ttu-id="39ed3-144">0x00000109</span><span class="sxs-lookup"><span data-stu-id="39ed3-144">0x00000109</span></span>  <br/> |
|<span data-ttu-id="39ed3-145">原件邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-145">Nondelivery mail</span></span>  <br/> |<span data-ttu-id="39ed3-146">0x0000010A</span><span class="sxs-lookup"><span data-stu-id="39ed3-146">0x0000010A</span></span>  <br/> |
|<span data-ttu-id="39ed3-147">Nonread 的邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-147">Nonread mail</span></span>  <br/> |<span data-ttu-id="39ed3-148">0x0000010B</span><span class="sxs-lookup"><span data-stu-id="39ed3-148">0x0000010B</span></span>  <br/> |
|<span data-ttu-id="39ed3-149">Recall_S 邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-149">Recall_S mail</span></span>  <br/> |<span data-ttu-id="39ed3-150">0x0000010C</span><span class="sxs-lookup"><span data-stu-id="39ed3-150">0x0000010C</span></span>  <br/> |
|<span data-ttu-id="39ed3-151">Recall_F 邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-151">Recall_F mail</span></span>  <br/> |<span data-ttu-id="39ed3-152">0x0000010D</span><span class="sxs-lookup"><span data-stu-id="39ed3-152">0x0000010D</span></span>  <br/> |
|<span data-ttu-id="39ed3-153">跟踪邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-153">Tracking mail</span></span>  <br/> |<span data-ttu-id="39ed3-154">0x0000010E</span><span class="sxs-lookup"><span data-stu-id="39ed3-154">0x0000010E</span></span>  <br/> |
|<span data-ttu-id="39ed3-155">利用 office 邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-155">Out of office mail</span></span>  <br/> |<span data-ttu-id="39ed3-156">0x0000011B</span><span class="sxs-lookup"><span data-stu-id="39ed3-156">0x0000011B</span></span>  <br/> |
|<span data-ttu-id="39ed3-157">邮件撤回</span><span class="sxs-lookup"><span data-stu-id="39ed3-157">Recall mail</span></span>  <br/> |<span data-ttu-id="39ed3-158">0x0000011C</span><span class="sxs-lookup"><span data-stu-id="39ed3-158">0x0000011C</span></span>  <br/> |
|<span data-ttu-id="39ed3-159">跟踪的邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-159">Tracked mail</span></span>  <br/> |<span data-ttu-id="39ed3-160">0x00000130</span><span class="sxs-lookup"><span data-stu-id="39ed3-160">0x00000130</span></span>  <br/> |
|<span data-ttu-id="39ed3-161">联系人</span><span class="sxs-lookup"><span data-stu-id="39ed3-161">Contact</span></span>  <br/> |<span data-ttu-id="39ed3-162">0x00000200</span><span class="sxs-lookup"><span data-stu-id="39ed3-162">0x00000200</span></span>  <br/> |
|<span data-ttu-id="39ed3-163">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="39ed3-163">Distribution list</span></span>  <br/> |<span data-ttu-id="39ed3-164">0x00000202</span><span class="sxs-lookup"><span data-stu-id="39ed3-164">0x00000202</span></span>  <br/> |
|<span data-ttu-id="39ed3-165">粘滞便笺蓝色</span><span class="sxs-lookup"><span data-stu-id="39ed3-165">Sticky note blue</span></span>  <br/> |<span data-ttu-id="39ed3-166">0x00000300</span><span class="sxs-lookup"><span data-stu-id="39ed3-166">0x00000300</span></span>  <br/> |
|<span data-ttu-id="39ed3-167">粘滞便笺绿色</span><span class="sxs-lookup"><span data-stu-id="39ed3-167">Sticky note green</span></span>  <br/> |<span data-ttu-id="39ed3-168">0x00000301</span><span class="sxs-lookup"><span data-stu-id="39ed3-168">0x00000301</span></span>  <br/> |
|<span data-ttu-id="39ed3-169">粘滞便笺粉色</span><span class="sxs-lookup"><span data-stu-id="39ed3-169">Sticky note pink</span></span>  <br/> |<span data-ttu-id="39ed3-170">0x00000302</span><span class="sxs-lookup"><span data-stu-id="39ed3-170">0x00000302</span></span>  <br/> |
|<span data-ttu-id="39ed3-171">粘滞便笺黄色</span><span class="sxs-lookup"><span data-stu-id="39ed3-171">Sticky note yellow</span></span>  <br/> |<span data-ttu-id="39ed3-172">0x00000303</span><span class="sxs-lookup"><span data-stu-id="39ed3-172">0x00000303</span></span>  <br/> |
|<span data-ttu-id="39ed3-173">粘滞便笺白皮书</span><span class="sxs-lookup"><span data-stu-id="39ed3-173">Sticky note white</span></span>  <br/> |<span data-ttu-id="39ed3-174">0x00000304</span><span class="sxs-lookup"><span data-stu-id="39ed3-174">0x00000304</span></span>  <br/> |
|<span data-ttu-id="39ed3-175">单实例约会</span><span class="sxs-lookup"><span data-stu-id="39ed3-175">Single instance appointment</span></span>  <br/> |<span data-ttu-id="39ed3-176">0x00000400</span><span class="sxs-lookup"><span data-stu-id="39ed3-176">0x00000400</span></span>  <br/> |
|<span data-ttu-id="39ed3-177">定期约会</span><span class="sxs-lookup"><span data-stu-id="39ed3-177">Recurring appointment</span></span>  <br/> |<span data-ttu-id="39ed3-178">0x00000401</span><span class="sxs-lookup"><span data-stu-id="39ed3-178">0x00000401</span></span>  <br/> |
|<span data-ttu-id="39ed3-179">单实例会议</span><span class="sxs-lookup"><span data-stu-id="39ed3-179">Single instance meeting</span></span>  <br/> |<span data-ttu-id="39ed3-180">0x00000402</span><span class="sxs-lookup"><span data-stu-id="39ed3-180">0x00000402</span></span>  <br/> |
|<span data-ttu-id="39ed3-181">定期会议</span><span class="sxs-lookup"><span data-stu-id="39ed3-181">Recurring meeting</span></span>  <br/> |<span data-ttu-id="39ed3-182">0x00000403</span><span class="sxs-lookup"><span data-stu-id="39ed3-182">0x00000403</span></span>  <br/> |
|<span data-ttu-id="39ed3-183">会议请求</span><span class="sxs-lookup"><span data-stu-id="39ed3-183">Meeting request</span></span>  <br/> |<span data-ttu-id="39ed3-184">0x00000404</span><span class="sxs-lookup"><span data-stu-id="39ed3-184">0x00000404</span></span>  <br/> |
|<span data-ttu-id="39ed3-185">Accept</span><span class="sxs-lookup"><span data-stu-id="39ed3-185">Accept</span></span>  <br/> |<span data-ttu-id="39ed3-186">0x00000405</span><span class="sxs-lookup"><span data-stu-id="39ed3-186">0x00000405</span></span>  <br/> |
|<span data-ttu-id="39ed3-187">拒绝</span><span class="sxs-lookup"><span data-stu-id="39ed3-187">Decline</span></span>  <br/> |<span data-ttu-id="39ed3-188">0x00000406</span><span class="sxs-lookup"><span data-stu-id="39ed3-188">0x00000406</span></span>  <br/> |
|<span data-ttu-id="39ed3-189">Tentativly</span><span class="sxs-lookup"><span data-stu-id="39ed3-189">Tentativly</span></span>  <br/> |<span data-ttu-id="39ed3-190">0x00000407</span><span class="sxs-lookup"><span data-stu-id="39ed3-190">0x00000407</span></span>  <br/> |
|<span data-ttu-id="39ed3-191">取消</span><span class="sxs-lookup"><span data-stu-id="39ed3-191">Cancellation</span></span>  <br/> |<span data-ttu-id="39ed3-192">0x00000408</span><span class="sxs-lookup"><span data-stu-id="39ed3-192">0x00000408</span></span>  <br/> |
|<span data-ttu-id="39ed3-193">信息性更新</span><span class="sxs-lookup"><span data-stu-id="39ed3-193">Informational update</span></span>  <br/> |<span data-ttu-id="39ed3-194">0x00000409</span><span class="sxs-lookup"><span data-stu-id="39ed3-194">0x00000409</span></span>  <br/> |
|<span data-ttu-id="39ed3-195">任务/任务</span><span class="sxs-lookup"><span data-stu-id="39ed3-195">Task/task</span></span>  <br/> |<span data-ttu-id="39ed3-196">0x00000500</span><span class="sxs-lookup"><span data-stu-id="39ed3-196">0x00000500</span></span>  <br/> |
|<span data-ttu-id="39ed3-197">未分配的定期任务</span><span class="sxs-lookup"><span data-stu-id="39ed3-197">Unassigned recurring task</span></span>  <br/> |<span data-ttu-id="39ed3-198">0x00000501</span><span class="sxs-lookup"><span data-stu-id="39ed3-198">0x00000501</span></span>  <br/> |
|<span data-ttu-id="39ed3-199">代理人的任务</span><span class="sxs-lookup"><span data-stu-id="39ed3-199">Assignee's task</span></span>  <br/> |<span data-ttu-id="39ed3-200">0x00000502</span><span class="sxs-lookup"><span data-stu-id="39ed3-200">0x00000502</span></span>  <br/> |
|<span data-ttu-id="39ed3-201">分配人的任务</span><span class="sxs-lookup"><span data-stu-id="39ed3-201">Assigner's task</span></span>  <br/> |<span data-ttu-id="39ed3-202">0x00000503</span><span class="sxs-lookup"><span data-stu-id="39ed3-202">0x00000503</span></span>  <br/> |
|<span data-ttu-id="39ed3-203">任务要求</span><span class="sxs-lookup"><span data-stu-id="39ed3-203">Task request</span></span>  <br/> |<span data-ttu-id="39ed3-204">0x00000504</span><span class="sxs-lookup"><span data-stu-id="39ed3-204">0x00000504</span></span>  <br/> |
|<span data-ttu-id="39ed3-205">接受任务</span><span class="sxs-lookup"><span data-stu-id="39ed3-205">Task acceptance</span></span>  <br/> |<span data-ttu-id="39ed3-206">0x00000505</span><span class="sxs-lookup"><span data-stu-id="39ed3-206">0x00000505</span></span>  <br/> |
|<span data-ttu-id="39ed3-207">任务拒绝</span><span class="sxs-lookup"><span data-stu-id="39ed3-207">Task rejection</span></span>  <br/> |<span data-ttu-id="39ed3-208">0x00000506</span><span class="sxs-lookup"><span data-stu-id="39ed3-208">0x00000506</span></span>  <br/> |
|<span data-ttu-id="39ed3-209">日记对话</span><span class="sxs-lookup"><span data-stu-id="39ed3-209">Journal conversation</span></span>  <br/> |<span data-ttu-id="39ed3-210">0x00000601</span><span class="sxs-lookup"><span data-stu-id="39ed3-210">0x00000601</span></span>  <br/> |
|<span data-ttu-id="39ed3-211">日记电子邮件</span><span class="sxs-lookup"><span data-stu-id="39ed3-211">Journal email message</span></span>  <br/> |<span data-ttu-id="39ed3-212">0x00000602</span><span class="sxs-lookup"><span data-stu-id="39ed3-212">0x00000602</span></span>  <br/> |
|<span data-ttu-id="39ed3-213">日记会议请求</span><span class="sxs-lookup"><span data-stu-id="39ed3-213">Journal meeting request</span></span>  <br/> |<span data-ttu-id="39ed3-214">0x00000603</span><span class="sxs-lookup"><span data-stu-id="39ed3-214">0x00000603</span></span>  <br/> |
|<span data-ttu-id="39ed3-215">日记会议响应</span><span class="sxs-lookup"><span data-stu-id="39ed3-215">Journal meeting response</span></span>  <br/> |<span data-ttu-id="39ed3-216">0x00000604</span><span class="sxs-lookup"><span data-stu-id="39ed3-216">0x00000604</span></span>  <br/> |
|<span data-ttu-id="39ed3-217">日志任务要求</span><span class="sxs-lookup"><span data-stu-id="39ed3-217">Journal task request</span></span>  <br/> |<span data-ttu-id="39ed3-218">0x00000606</span><span class="sxs-lookup"><span data-stu-id="39ed3-218">0x00000606</span></span>  <br/> |
|<span data-ttu-id="39ed3-219">日志任务响应</span><span class="sxs-lookup"><span data-stu-id="39ed3-219">Journal task response</span></span>  <br/> |<span data-ttu-id="39ed3-220">0x00000607</span><span class="sxs-lookup"><span data-stu-id="39ed3-220">0x00000607</span></span>  <br/> |
|<span data-ttu-id="39ed3-221">日记注释</span><span class="sxs-lookup"><span data-stu-id="39ed3-221">Journal note</span></span>  <br/> |<span data-ttu-id="39ed3-222">0x00000608</span><span class="sxs-lookup"><span data-stu-id="39ed3-222">0x00000608</span></span>  <br/> |
|<span data-ttu-id="39ed3-223">日记传真</span><span class="sxs-lookup"><span data-stu-id="39ed3-223">Journal fax</span></span>  <br/> |<span data-ttu-id="39ed3-224">0x00000609</span><span class="sxs-lookup"><span data-stu-id="39ed3-224">0x00000609</span></span>  <br/> |
|<span data-ttu-id="39ed3-225">日记电话呼叫</span><span class="sxs-lookup"><span data-stu-id="39ed3-225">Journal phone call</span></span>  <br/> |<span data-ttu-id="39ed3-226">0x0000060A</span><span class="sxs-lookup"><span data-stu-id="39ed3-226">0x0000060A</span></span>  <br/> |
|<span data-ttu-id="39ed3-227">日记字母</span><span class="sxs-lookup"><span data-stu-id="39ed3-227">Journal letter</span></span>  <br/> |<span data-ttu-id="39ed3-228">0x0000060C</span><span class="sxs-lookup"><span data-stu-id="39ed3-228">0x0000060C</span></span>  <br/> |
|<span data-ttu-id="39ed3-229">日记 Microsoft Office Word</span><span class="sxs-lookup"><span data-stu-id="39ed3-229">Journal Microsoft Office Word</span></span>  <br/> |<span data-ttu-id="39ed3-230">0x0000060D</span><span class="sxs-lookup"><span data-stu-id="39ed3-230">0x0000060D</span></span>  <br/> |
|<span data-ttu-id="39ed3-231">日记 Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="39ed3-231">Journal Microsoft Office Excel</span></span>  <br/> |<span data-ttu-id="39ed3-232">0x0000060E</span><span class="sxs-lookup"><span data-stu-id="39ed3-232">0x0000060E</span></span>  <br/> |
|<span data-ttu-id="39ed3-233">日记 Microsoft Office PowerPoint</span><span class="sxs-lookup"><span data-stu-id="39ed3-233">Journal Microsoft Office PowerPoint</span></span>  <br/> |<span data-ttu-id="39ed3-234">0x0000060F</span><span class="sxs-lookup"><span data-stu-id="39ed3-234">0x0000060F</span></span>  <br/> |
|<span data-ttu-id="39ed3-235">日记 Microsoft Office Access</span><span class="sxs-lookup"><span data-stu-id="39ed3-235">Journal Microsoft Office Access</span></span>  <br/> |<span data-ttu-id="39ed3-236">0x00000610</span><span class="sxs-lookup"><span data-stu-id="39ed3-236">0x00000610</span></span>  <br/> |
|<span data-ttu-id="39ed3-237">日记文档</span><span class="sxs-lookup"><span data-stu-id="39ed3-237">Journal document</span></span>  <br/> |<span data-ttu-id="39ed3-238">0x00000612</span><span class="sxs-lookup"><span data-stu-id="39ed3-238">0x00000612</span></span>  <br/> |
|<span data-ttu-id="39ed3-239">日记会议</span><span class="sxs-lookup"><span data-stu-id="39ed3-239">Journal meeting</span></span>  <br/> |<span data-ttu-id="39ed3-240">0x00000613</span><span class="sxs-lookup"><span data-stu-id="39ed3-240">0x00000613</span></span>  <br/> |
|<span data-ttu-id="39ed3-241">日记会议取消</span><span class="sxs-lookup"><span data-stu-id="39ed3-241">Journal meeting cancellation</span></span>  <br/> |<span data-ttu-id="39ed3-242">0x00000614</span><span class="sxs-lookup"><span data-stu-id="39ed3-242">0x00000614</span></span>  <br/> |
|<span data-ttu-id="39ed3-243">日记远程会话</span><span class="sxs-lookup"><span data-stu-id="39ed3-243">Journal remote session</span></span>  <br/> |<span data-ttu-id="39ed3-244">0x00000615</span><span class="sxs-lookup"><span data-stu-id="39ed3-244">0x00000615</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="39ed3-245">相关资源</span><span class="sxs-lookup"><span data-stu-id="39ed3-245">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="39ed3-246">协议规范</span><span class="sxs-lookup"><span data-stu-id="39ed3-246">Protocol specifications</span></span>

<span data-ttu-id="39ed3-247">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="39ed3-247">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="39ed3-248">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="39ed3-248">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="39ed3-249">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="39ed3-249">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="39ed3-250">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="39ed3-250">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
<span data-ttu-id="39ed3-251">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="39ed3-251">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="39ed3-252">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="39ed3-252">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="39ed3-253">[[MS OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="39ed3-253">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="39ed3-254">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="39ed3-254">Specifies the properties and operations that are permissible on contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="39ed3-255">头文件</span><span class="sxs-lookup"><span data-stu-id="39ed3-255">Header files</span></span>

<span data-ttu-id="39ed3-256">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="39ed3-256">Mapidefs.h</span></span>
  
> <span data-ttu-id="39ed3-257">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="39ed3-257">Provides data type definitions.</span></span>
    
<span data-ttu-id="39ed3-258">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="39ed3-258">Mapitags.h</span></span>
  
> <span data-ttu-id="39ed3-259">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="39ed3-259">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="39ed3-260">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39ed3-260">See also</span></span>



[<span data-ttu-id="39ed3-261">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="39ed3-261">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="39ed3-262">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="39ed3-262">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="39ed3-263">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="39ed3-263">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="39ed3-264">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="39ed3-264">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

