---
title: PidTagDisplayTypeEx 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayTypeEx
api_type:
- HeaderDef
ms.assetid: 23074402-6ac1-47f1-8a49-b8909f98a26e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 30482f7d6acef7377a1b63bc3de4e43be48d8608
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583356"
---
# <a name="pidtagdisplaytypeex-canonical-property"></a><span data-ttu-id="e6ab8-103">PidTagDisplayTypeEx 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6ab8-103">PidTagDisplayTypeEx Canonical Property</span></span>

  
  
<span data-ttu-id="e6ab8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6ab8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6ab8-105">包含一个条目，相对于如何条目应显示在表中的行的全局地址列表的类型。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-105">Contains the type of an entry, with respect to how the entry should be displayed in a row in a table for the Global Address List.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6ab8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e6ab8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e6ab8-107">PR_DISPLAY_TYPE_EX</span><span class="sxs-lookup"><span data-stu-id="e6ab8-107">PR_DISPLAY_TYPE_EX</span></span>  <br/> |
|<span data-ttu-id="e6ab8-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e6ab8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e6ab8-109">0x3905</span><span class="sxs-lookup"><span data-stu-id="e6ab8-109">0x3905</span></span>  <br/> |
|<span data-ttu-id="e6ab8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e6ab8-110">Data type:</span></span>  <br/> |<span data-ttu-id="e6ab8-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e6ab8-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e6ab8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e6ab8-112">Area:</span></span>  <br/> |<span data-ttu-id="e6ab8-113">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="e6ab8-113">MAPI address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6ab8-114">注解</span><span class="sxs-lookup"><span data-stu-id="e6ab8-114">Remarks</span></span>

<span data-ttu-id="e6ab8-115">此属性指定的一个条目，相对于它的全局地址列表中显示的方式的类型。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-115">This property specifies the type of an entry, with respect to how it should be displayed in the Global Address List.</span></span> <span data-ttu-id="e6ab8-116">它提供不能用**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 表示的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-116">It provides additional information that cannot be represented in **PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6ab8-117">**PR_DISPLAY_TYPE**和此属性的值以"DT_"开头，并且在 Mapitags.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-117">The values of both **PR_DISPLAY_TYPE** and this property begin with "DT_" and are defined in Mapitags.h.</span></span> <span data-ttu-id="e6ab8-118">MAPI 的保留未进行归档的所有值。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-118">All values not documented are reserved for MAPI.</span></span> <span data-ttu-id="e6ab8-119">客户端应用程序无需定义的任何新值，必须在准备好处理一个未记录的值。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-119">Client applications must not define any new values and must be prepared to deal with an undocumented value.</span></span> 
  
<span data-ttu-id="e6ab8-120">有一些可帮助确定如它是本地、 远程或安全控制对象的属性的宏。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-120">There are some macros that can help determine attributes of an object such as whether it is local, remote, or security-controlled.</span></span> <span data-ttu-id="e6ab8-121">这些宏包括：</span><span class="sxs-lookup"><span data-stu-id="e6ab8-121">These macros include:</span></span> 
  
|<span data-ttu-id="e6ab8-122">**宏**</span><span class="sxs-lookup"><span data-stu-id="e6ab8-122">**Macro**</span></span>|<span data-ttu-id="e6ab8-123">**值**</span><span class="sxs-lookup"><span data-stu-id="e6ab8-123">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6ab8-124">DTE_FLAG_REMOTE_VALID</span><span class="sxs-lookup"><span data-stu-id="e6ab8-124">DTE_FLAG_REMOTE_VALID</span></span>  <br/> |<span data-ttu-id="e6ab8-125">0x80000000)</span><span class="sxs-lookup"><span data-stu-id="e6ab8-125">0x80000000)</span></span>  <br/> |
|<span data-ttu-id="e6ab8-126">DTE_FLAG_ACL_CAPABLE</span><span class="sxs-lookup"><span data-stu-id="e6ab8-126">DTE_FLAG_ACL_CAPABLE</span></span>  <br/> |<span data-ttu-id="e6ab8-127">0x40000000</span><span class="sxs-lookup"><span data-stu-id="e6ab8-127">0x40000000</span></span>  <br/> |
|<span data-ttu-id="e6ab8-128">DTE_MASK_REMOTE</span><span class="sxs-lookup"><span data-stu-id="e6ab8-128">DTE_MASK_REMOTE</span></span>  <br/> |<span data-ttu-id="e6ab8-129">0x0000ff00</span><span class="sxs-lookup"><span data-stu-id="e6ab8-129">0x0000ff00</span></span>  <br/> |
|<span data-ttu-id="e6ab8-130">DTE_MASK_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e6ab8-130">DTE_MASK_LOCAL</span></span>  <br/> |<span data-ttu-id="e6ab8-131">0x000000ff</span><span class="sxs-lookup"><span data-stu-id="e6ab8-131">0x000000ff</span></span>  <br/> |
|<span data-ttu-id="e6ab8-132">DTE_IS_REMOTE_VALID(v)</span><span class="sxs-lookup"><span data-stu-id="e6ab8-132">DTE_IS_REMOTE_VALID(v)</span></span>  <br/> |<span data-ttu-id="e6ab8-133">(!!(（v) &amp; DTE_FLAG_REMOTE_VALID)</span><span class="sxs-lookup"><span data-stu-id="e6ab8-133">(!!((v) &amp; DTE_FLAG_REMOTE_VALID)</span></span>  <br/> |
|<span data-ttu-id="e6ab8-134">DTE_IS_ACL_CAPABLE(v)</span><span class="sxs-lookup"><span data-stu-id="e6ab8-134">DTE_IS_ACL_CAPABLE(v)</span></span>  <br/> |<span data-ttu-id="e6ab8-135">(!!(（v) &amp; DTE_FLAG_ACL_CAPABLE))</span><span class="sxs-lookup"><span data-stu-id="e6ab8-135">(!!((v) &amp; DTE_FLAG_ACL_CAPABLE))</span></span>  <br/> |
|<span data-ttu-id="e6ab8-136">DTE_REMOTE(v)</span><span class="sxs-lookup"><span data-stu-id="e6ab8-136">DTE_REMOTE(v)</span></span>  <br/> |<span data-ttu-id="e6ab8-137">((（v) &amp; DTE_MASK_REMOTE) \> \> 8)</span><span class="sxs-lookup"><span data-stu-id="e6ab8-137">(((v) &amp; DTE_MASK_REMOTE) \>\> 8)</span></span>  <br/> |
|<span data-ttu-id="e6ab8-138">DTE_LOCAL(v)</span><span class="sxs-lookup"><span data-stu-id="e6ab8-138">DTE_LOCAL(v)</span></span>  <br/> |<span data-ttu-id="e6ab8-139">(（v) &amp; DTE_MASK_LOCAL)</span><span class="sxs-lookup"><span data-stu-id="e6ab8-139">((v) &amp; DTE_MASK_LOCAL)</span></span>  <br/> |
|<span data-ttu-id="e6ab8-140">DT_ROOM</span><span class="sxs-lookup"><span data-stu-id="e6ab8-140">DT_ROOM</span></span>  <br/> |<span data-ttu-id="e6ab8-141">（满足） 0X00000007）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-141">((ULONG) 0x00000007)</span></span>  <br/> |
|<span data-ttu-id="e6ab8-142">DT_EQUIPMENT</span><span class="sxs-lookup"><span data-stu-id="e6ab8-142">DT_EQUIPMENT</span></span>  <br/> |<span data-ttu-id="e6ab8-143">（满足） 0X00000008）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-143">((ULONG) 0x00000008)</span></span>  <br/> |
|<span data-ttu-id="e6ab8-144">DT_SEC_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="e6ab8-144">DT_SEC_DISTLIST</span></span>  <br/> |<span data-ttu-id="e6ab8-145">（满足） 0X00000009）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-145">((ULONG) 0x00000009)</span></span>  <br/> |
   
<span data-ttu-id="e6ab8-146">以下是几个说明有关如何使用这些宏。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-146">The following are a few notes about how to use these macros.</span></span> 
  
- <span data-ttu-id="e6ab8-147">若要检查是否条目是另一个林中远程条目，应用于此属性以检查是否在条目中设置 DTE_FLAG_REMOTE_VALID 标志的值 DTE_IS_REMOTE_VALID 宏。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-147">To check whether an entry is a remote entry in another forest, apply the DTE_IS_REMOTE_VALID macro to the value of this property to check whether the DTE_FLAG_REMOTE_VALID flag is set in the entry.</span></span> <span data-ttu-id="e6ab8-148">如果是远程的条目，然后，您可以找到出远程条目的类型使用 DTE_REMOTE 宏。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-148">If it is a remote entry, you can then find out the type of the remote entry by using the DTE_REMOTE macro.</span></span> 
    
- <span data-ttu-id="e6ab8-149">在单林和跨林配置中，当**PR_DISPLAY_TYPE**具有 DT_DISTLIST 和 DTE_IS_REMOTE_VALID 的值为 false，将宏 DTE_LOCAL 应用于此属性的值可以让您进一步标识为对象的类型DT_DISTLIST （通讯组列表） 或 DT_SEC_DISTLIST （安全通讯组列表）。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-149">In both single-forest and cross-forest configurations, when **PR_DISPLAY_TYPE** has the value of DT_DISTLIST, and DTE_IS_REMOTE_VALID is false, applying the macro DTE_LOCAL to the value of this property can let you further identify the type of the object as either DT_DISTLIST (a distribution list) or DT_SEC_DISTLIST (a security distribution list).</span></span> 
    
- <span data-ttu-id="e6ab8-150">如果宏 DTE_LOCAL 于**PR_DISPLAY_TYPE_EX**的值，它返回类型 DT_REMOTE_MAILUSER 项将是远程项。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-150">If you apply the macro DTE_LOCAL to the value of **PR_DISPLAY_TYPE_EX** and it returns the type DT_REMOTE_MAILUSER, then the entry is a remote entry.</span></span> 
    
- <span data-ttu-id="e6ab8-151">在单个林或跨林配置的复制控制的访问控制列表 (ACL) 中，您可以使用 DTE_IS_ACL_CAPABLE 宏来确定一个条目的安全主体。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-151">In a single forest or in a cross-forest configuration where replication is controlled by an Access Control List (ACL), you can use the DTE_IS_ACL_CAPABLE macro to determine whether an entry is a security principal.</span></span>
    
<span data-ttu-id="e6ab8-152">在跨林配置中， **PR_DISPLAY_TYPE**有 DT_REMOTE_MAILUSER 值。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-152">In a cross-forest configuration, **PR_DISPLAY_TYPE** has the value of DT_REMOTE_MAILUSER.</span></span> <span data-ttu-id="e6ab8-153">将宏 DTE_REMOTE 应用于此属性的值可以让您获取的远程条目类型。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-153">Applying the macro DTE_REMOTE to the value of this property can let you obtain the type of the remote entry.</span></span> <span data-ttu-id="e6ab8-154">可能的远程条目类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="e6ab8-154">The possible types of remote entry are the following:</span></span> 
  
|<span data-ttu-id="e6ab8-155">**远程条目的类型**</span><span class="sxs-lookup"><span data-stu-id="e6ab8-155">**Type of Remote Entry**</span></span>|<span data-ttu-id="e6ab8-156">**值**</span><span class="sxs-lookup"><span data-stu-id="e6ab8-156">**Value**</span></span>|<span data-ttu-id="e6ab8-157">**说明**</span><span class="sxs-lookup"><span data-stu-id="e6ab8-157">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6ab8-158">DT_AGENT</span><span class="sxs-lookup"><span data-stu-id="e6ab8-158">DT_AGENT</span></span>  <br/> |<span data-ttu-id="e6ab8-159">（满足） 0X00000003）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-159">((ULONG) 0x00000003)</span></span>  <br/> |<span data-ttu-id="e6ab8-160">动态通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-160">Dynamic distribution list.</span></span>  <br/> |
|<span data-ttu-id="e6ab8-161">DT_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="e6ab8-161">DT_DISTLIST</span></span>  <br/> |<span data-ttu-id="e6ab8-162">（满足） 0X00000001）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-162">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="e6ab8-163">通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-163">Distribution list.</span></span>  <br/> |
|<span data-ttu-id="e6ab8-164">DT_EQUIPMENT</span><span class="sxs-lookup"><span data-stu-id="e6ab8-164">DT_EQUIPMENT</span></span>  <br/> |<span data-ttu-id="e6ab8-165">（满足） 0X00000008）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-165">((ULONG) 0x00000008)</span></span>  <br/> |<span data-ttu-id="e6ab8-166">设备，例如，打印机或投影仪。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-166">Equipment, for example, a printer or a projector.</span></span>  <br/> |
|<span data-ttu-id="e6ab8-167">DT_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="e6ab8-167">DT_MAILUSER</span></span>  <br/> |<span data-ttu-id="e6ab8-168">（满足） 0X00000000）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-168">((ULONG) 0x00000000)</span></span>  <br/> |<span data-ttu-id="e6ab8-169">具有邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-169">User with a mailbox.</span></span>  <br/> |
|<span data-ttu-id="e6ab8-170">DT_REMOTE_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="e6ab8-170">DT_REMOTE_MAILUSER</span></span>  <br/> |<span data-ttu-id="e6ab8-171">（满足） 0X00000000）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-171">((ULONG) 0x00000000)</span></span>  <br/> |<span data-ttu-id="e6ab8-172">全局地址列表中的地址列表条目。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-172">An address list entry in the Global Address List.</span></span>  <br/> |
|<span data-ttu-id="e6ab8-173">DT_ROOM</span><span class="sxs-lookup"><span data-stu-id="e6ab8-173">DT_ROOM</span></span>  <br/> |<span data-ttu-id="e6ab8-174">（满足） 0X00000007）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-174">((ULONG) 0x00000007)</span></span>  <br/> |<span data-ttu-id="e6ab8-175">会议室。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-175">Conference room.</span></span>  <br/> |
|<span data-ttu-id="e6ab8-176">DT_SEC_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="e6ab8-176">DT_SEC_DISTLIST</span></span>  <br/> |<span data-ttu-id="e6ab8-177">（满足） 0X00000009）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-177">((ULONG) 0x00000009)</span></span>  <br/> |<span data-ttu-id="e6ab8-178">安全通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-178">Security distribution list.</span></span>  <br/> |
   
<span data-ttu-id="e6ab8-179">在这两个单林和跨林配置，当**PR_DISPLAY_TYPE**具有 DT_DISTLIST 和 DTE_IS_REMOTE_VALID 的值为 false，将 DTE_LOCAL 宏应用于此属性的值可以让您获取的通讯组列表类型.</span><span class="sxs-lookup"><span data-stu-id="e6ab8-179">In both a single forest and in a cross-forest configuration, when **PR_DISPLAY_TYPE** has the value of DT_DISTLIST and DTE_IS_REMOTE_VALID is false, applying the DTE_LOCAL macro to the value of this property can let you obtain the type of the distribution list.</span></span> <span data-ttu-id="e6ab8-180">可能的通讯组列表类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="e6ab8-180">The possible types of distribution list are the following:</span></span> 
  
|<span data-ttu-id="e6ab8-181">**通讯组列表的类型**</span><span class="sxs-lookup"><span data-stu-id="e6ab8-181">**Type of Distribution List**</span></span>|<span data-ttu-id="e6ab8-182">**值**</span><span class="sxs-lookup"><span data-stu-id="e6ab8-182">**Value**</span></span>|<span data-ttu-id="e6ab8-183">**说明**</span><span class="sxs-lookup"><span data-stu-id="e6ab8-183">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6ab8-184">DT_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="e6ab8-184">DT_DISTLIST</span></span>  <br/> |<span data-ttu-id="e6ab8-185">（满足） 0X00000001）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-185">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="e6ab8-186">通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-186">Distribution list.</span></span>  <br/> |
|<span data-ttu-id="e6ab8-187">DT_SEC_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="e6ab8-187">DT_SEC_DISTLIST</span></span>  <br/> |<span data-ttu-id="e6ab8-188">（满足） 0X00000009）</span><span class="sxs-lookup"><span data-stu-id="e6ab8-188">((ULONG) 0x00000009)</span></span>  <br/> |<span data-ttu-id="e6ab8-189">安全通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-189">Security distribution list.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="e6ab8-190">相关资源</span><span class="sxs-lookup"><span data-stu-id="e6ab8-190">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e6ab8-191">协议规范</span><span class="sxs-lookup"><span data-stu-id="e6ab8-191">Protocol specifications</span></span>

<span data-ttu-id="e6ab8-192">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6ab8-192">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6ab8-193">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-193">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e6ab8-194">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6ab8-194">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6ab8-195">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-195">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e6ab8-196">头文件</span><span class="sxs-lookup"><span data-stu-id="e6ab8-196">Header files</span></span>

<span data-ttu-id="e6ab8-197">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e6ab8-197">Mapidefs.h</span></span>
  
> <span data-ttu-id="e6ab8-198">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-198">Provides data type definitions.</span></span>
    
<span data-ttu-id="e6ab8-199">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e6ab8-199">Mapitags.h</span></span>
  
> <span data-ttu-id="e6ab8-200">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e6ab8-200">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e6ab8-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6ab8-201">See also</span></span>



[<span data-ttu-id="e6ab8-202">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e6ab8-202">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e6ab8-203">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6ab8-203">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e6ab8-204">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e6ab8-204">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e6ab8-205">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e6ab8-205">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

