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
ms.openlocfilehash: 6eea30188543cb06545a9efad705f5593d4227a7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360772"
---
# <a name="pidtagdisplaytypeex-canonical-property"></a><span data-ttu-id="fd8c1-103">PidTagDisplayTypeEx 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd8c1-103">PidTagDisplayTypeEx Canonical Property</span></span>

  
  
<span data-ttu-id="fd8c1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd8c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fd8c1-105">包含条目的类型，与条目在全局地址列表的表中行中的显示方式有关。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-105">Contains the type of an entry, with respect to how the entry should be displayed in a row in a table for the Global Address List.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fd8c1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fd8c1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fd8c1-107">PR_DISPLAY_TYPE_EX</span><span class="sxs-lookup"><span data-stu-id="fd8c1-107">PR_DISPLAY_TYPE_EX</span></span>  <br/> |
|<span data-ttu-id="fd8c1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="fd8c1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fd8c1-109">0x3905</span><span class="sxs-lookup"><span data-stu-id="fd8c1-109">0x3905</span></span>  <br/> |
|<span data-ttu-id="fd8c1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fd8c1-110">Data type:</span></span>  <br/> |<span data-ttu-id="fd8c1-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="fd8c1-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="fd8c1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fd8c1-112">Area:</span></span>  <br/> |<span data-ttu-id="fd8c1-113">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="fd8c1-113">MAPI address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fd8c1-114">备注</span><span class="sxs-lookup"><span data-stu-id="fd8c1-114">Remarks</span></span>

<span data-ttu-id="fd8c1-115">此属性指定条目的类型，以它应在全局地址列表中显示。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-115">This property specifies the type of an entry, with respect to how it should be displayed in the Global Address List.</span></span> <span data-ttu-id="fd8c1-116">它提供了无法在[PidTagDisplayType](pidtagdisplaytype-canonical-property.md)  PR_DISPLAY_TYPE (表示的其他) 。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-116">It provides additional information that cannot be represented in **PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd8c1-117">此属性和此属性 **PR_DISPLAY_TYPE** 以"DT_"开头，在 Mapitags.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-117">The values of both **PR_DISPLAY_TYPE** and this property begin with "DT_" and are defined in Mapitags.h.</span></span> <span data-ttu-id="fd8c1-118">未记录的所有值都保留用于 MAPI。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-118">All values not documented are reserved for MAPI.</span></span> <span data-ttu-id="fd8c1-119">客户端应用程序不得定义任何新值，并且必须准备处理未记录的值。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-119">Client applications must not define any new values and must be prepared to deal with an undocumented value.</span></span> 
  
<span data-ttu-id="fd8c1-120">有一些宏可帮助确定对象的属性，例如它是本地对象、远程对象还是受安全控制的对象。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-120">There are some macros that can help determine attributes of an object such as whether it is local, remote, or security-controlled.</span></span> <span data-ttu-id="fd8c1-121">这些宏包括：</span><span class="sxs-lookup"><span data-stu-id="fd8c1-121">These macros include:</span></span> 
  
|<span data-ttu-id="fd8c1-122">**宏**</span><span class="sxs-lookup"><span data-stu-id="fd8c1-122">**Macro**</span></span>|<span data-ttu-id="fd8c1-123">**值**</span><span class="sxs-lookup"><span data-stu-id="fd8c1-123">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fd8c1-124">DTE_FLAG_REMOTE_VALID</span><span class="sxs-lookup"><span data-stu-id="fd8c1-124">DTE_FLAG_REMOTE_VALID</span></span>  <br/> |<span data-ttu-id="fd8c1-125">0x80000000) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-125">0x80000000)</span></span>  <br/> |
|<span data-ttu-id="fd8c1-126">DTE_FLAG_ACL_CAPABLE</span><span class="sxs-lookup"><span data-stu-id="fd8c1-126">DTE_FLAG_ACL_CAPABLE</span></span>  <br/> |<span data-ttu-id="fd8c1-127">0x40000000</span><span class="sxs-lookup"><span data-stu-id="fd8c1-127">0x40000000</span></span>  <br/> |
|<span data-ttu-id="fd8c1-128">DTE_MASK_REMOTE</span><span class="sxs-lookup"><span data-stu-id="fd8c1-128">DTE_MASK_REMOTE</span></span>  <br/> |<span data-ttu-id="fd8c1-129">0x0000ff00</span><span class="sxs-lookup"><span data-stu-id="fd8c1-129">0x0000ff00</span></span>  <br/> |
|<span data-ttu-id="fd8c1-130">DTE_MASK_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fd8c1-130">DTE_MASK_LOCAL</span></span>  <br/> |<span data-ttu-id="fd8c1-131">0x000000ff</span><span class="sxs-lookup"><span data-stu-id="fd8c1-131">0x000000ff</span></span>  <br/> |
|<span data-ttu-id="fd8c1-132">DTE_IS_REMOTE_VALID (v) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-132">DTE_IS_REMOTE_VALID(v)</span></span>  <br/> |<span data-ttu-id="fd8c1-133"> (？ ( (v) &amp; DTE_FLAG_REMOTE_VALID) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-133">(!!((v) &amp; DTE_FLAG_REMOTE_VALID)</span></span>  <br/> |
|<span data-ttu-id="fd8c1-134">DTE_IS_ACL_CAPABLE (v) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-134">DTE_IS_ACL_CAPABLE(v)</span></span>  <br/> |<span data-ttu-id="fd8c1-135"> (？ ( (v) &amp; DTE_FLAG_ACL_CAPABLE) ) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-135">(!!((v) &amp; DTE_FLAG_ACL_CAPABLE))</span></span>  <br/> |
|<span data-ttu-id="fd8c1-136">DTE_REMOTE (v) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-136">DTE_REMOTE(v)</span></span>  <br/> |<span data-ttu-id="fd8c1-137"> ( ( (v) DTE_MASK_REMOTE) &amp; \> \> 8) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-137">(((v) &amp; DTE_MASK_REMOTE) \>\> 8)</span></span>  <br/> |
|<span data-ttu-id="fd8c1-138">DTE_LOCAL (v) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-138">DTE_LOCAL(v)</span></span>  <br/> |<span data-ttu-id="fd8c1-139"> ( (v) &amp; DTE_MASK_LOCAL) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-139">((v) &amp; DTE_MASK_LOCAL)</span></span>  <br/> |
|<span data-ttu-id="fd8c1-140">DT_ROOM</span><span class="sxs-lookup"><span data-stu-id="fd8c1-140">DT_ROOM</span></span>  <br/> |<span data-ttu-id="fd8c1-141"> ( (ULONG) 0x00000007) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-141">((ULONG) 0x00000007)</span></span>  <br/> |
|<span data-ttu-id="fd8c1-142">DT_EQUIPMENT</span><span class="sxs-lookup"><span data-stu-id="fd8c1-142">DT_EQUIPMENT</span></span>  <br/> |<span data-ttu-id="fd8c1-143"> ( (ULONG) 0x00000008) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-143">((ULONG) 0x00000008)</span></span>  <br/> |
|<span data-ttu-id="fd8c1-144">DT_SEC_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="fd8c1-144">DT_SEC_DISTLIST</span></span>  <br/> |<span data-ttu-id="fd8c1-145"> ( (ULONG) 0x00000009) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-145">((ULONG) 0x00000009)</span></span>  <br/> |
   
<span data-ttu-id="fd8c1-146">以下是有关如何使用这些宏的一些说明。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-146">The following are a few notes about how to use these macros.</span></span> 
  
- <span data-ttu-id="fd8c1-147">若要检查条目是否是另一个林中的远程条目，请对此属性的值应用 DTE_IS_REMOTE_VALID 宏，以检查该条目中是否设置了 DTE_FLAG_REMOTE_VALID 标志。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-147">To check whether an entry is a remote entry in another forest, apply the DTE_IS_REMOTE_VALID macro to the value of this property to check whether the DTE_FLAG_REMOTE_VALID flag is set in the entry.</span></span> <span data-ttu-id="fd8c1-148">如果它是远程条目，则可以通过使用远程条目的宏DTE_REMOTE类型。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-148">If it is a remote entry, you can then find out the type of the remote entry by using the DTE_REMOTE macro.</span></span> 
    
- <span data-ttu-id="fd8c1-149">在单林和跨林配置中，当 **PR_DISPLAY_TYPE** 的值为 DT_DISTLIST 且 DTE_IS_REMOTE_VALID 为 false 时，对此属性的值应用宏 DTE_LOCAL 可以进一步将对象类型标识为通讯组列表) DT_DISTLIST (或 DT_SEC_DISTLIST (安全通讯组列表) 。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-149">In both single-forest and cross-forest configurations, when **PR_DISPLAY_TYPE** has the value of DT_DISTLIST, and DTE_IS_REMOTE_VALID is false, applying the macro DTE_LOCAL to the value of this property can let you further identify the type of the object as either DT_DISTLIST (a distribution list) or DT_SEC_DISTLIST (a security distribution list).</span></span> 
    
- <span data-ttu-id="fd8c1-150">如果对 DTE_LOCAL 值应用宏PR_DISPLAY_TYPE_EX则返回DT_REMOTE_MAILUSER，则条目为远程条目。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-150">If you apply the macro DTE_LOCAL to the value of **PR_DISPLAY_TYPE_EX** and it returns the type DT_REMOTE_MAILUSER, then the entry is a remote entry.</span></span> 
    
- <span data-ttu-id="fd8c1-151">在单林或跨林配置（其中复制由访问控制列表 (ACL) 控制）中，可以使用 DTE_IS_ACL_CAPABLE 宏来确定条目是否是安全主体。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-151">In a single forest or in a cross-forest configuration where replication is controlled by an Access Control List (ACL), you can use the DTE_IS_ACL_CAPABLE macro to determine whether an entry is a security principal.</span></span>
    
<span data-ttu-id="fd8c1-152">在跨林 **配置中** ，PR_DISPLAY_TYPE的值为 DT_REMOTE_MAILUSER。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-152">In a cross-forest configuration, **PR_DISPLAY_TYPE** has the value of DT_REMOTE_MAILUSER.</span></span> <span data-ttu-id="fd8c1-153">将宏DTE_REMOTE此属性的值可让你获取远程条目的类型。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-153">Applying the macro DTE_REMOTE to the value of this property can let you obtain the type of the remote entry.</span></span> <span data-ttu-id="fd8c1-154">可能的远程条目类型如下：</span><span class="sxs-lookup"><span data-stu-id="fd8c1-154">The possible types of remote entry are the following:</span></span> 
  
|<span data-ttu-id="fd8c1-155">**远程输入的类型**</span><span class="sxs-lookup"><span data-stu-id="fd8c1-155">**Type of Remote Entry**</span></span>|<span data-ttu-id="fd8c1-156">**值**</span><span class="sxs-lookup"><span data-stu-id="fd8c1-156">**Value**</span></span>|<span data-ttu-id="fd8c1-157">**说明**</span><span class="sxs-lookup"><span data-stu-id="fd8c1-157">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd8c1-158">DT_AGENT</span><span class="sxs-lookup"><span data-stu-id="fd8c1-158">DT_AGENT</span></span>  <br/> |<span data-ttu-id="fd8c1-159">((ULONG) 0x00000003)</span><span class="sxs-lookup"><span data-stu-id="fd8c1-159">((ULONG) 0x00000003)</span></span>  <br/> |<span data-ttu-id="fd8c1-160">动态通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-160">Dynamic distribution list.</span></span>  <br/> |
|<span data-ttu-id="fd8c1-161">DT_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="fd8c1-161">DT_DISTLIST</span></span>  <br/> |<span data-ttu-id="fd8c1-162">((ULONG) 0x00000001)</span><span class="sxs-lookup"><span data-stu-id="fd8c1-162">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="fd8c1-163">通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-163">Distribution list.</span></span>  <br/> |
|<span data-ttu-id="fd8c1-164">DT_EQUIPMENT</span><span class="sxs-lookup"><span data-stu-id="fd8c1-164">DT_EQUIPMENT</span></span>  <br/> |<span data-ttu-id="fd8c1-165"> ( (ULONG) 0x00000008) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-165">((ULONG) 0x00000008)</span></span>  <br/> |<span data-ttu-id="fd8c1-166">设备，例如打印机或投影仪。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-166">Equipment, for example, a printer or a projector.</span></span>  <br/> |
|<span data-ttu-id="fd8c1-167">DT_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="fd8c1-167">DT_MAILUSER</span></span>  <br/> |<span data-ttu-id="fd8c1-168"> ( (ULONG) 0x00000000) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-168">((ULONG) 0x00000000)</span></span>  <br/> |<span data-ttu-id="fd8c1-169">具有邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-169">User with a mailbox.</span></span>  <br/> |
|<span data-ttu-id="fd8c1-170">DT_REMOTE_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="fd8c1-170">DT_REMOTE_MAILUSER</span></span>  <br/> |<span data-ttu-id="fd8c1-171"> ( (ULONG) 0x00000000) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-171">((ULONG) 0x00000000)</span></span>  <br/> |<span data-ttu-id="fd8c1-172">全局地址列表中的地址列表条目。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-172">An address list entry in the Global Address List.</span></span>  <br/> |
|<span data-ttu-id="fd8c1-173">DT_ROOM</span><span class="sxs-lookup"><span data-stu-id="fd8c1-173">DT_ROOM</span></span>  <br/> |<span data-ttu-id="fd8c1-174"> ( (ULONG) 0x00000007) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-174">((ULONG) 0x00000007)</span></span>  <br/> |<span data-ttu-id="fd8c1-175">会议室。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-175">Conference room.</span></span>  <br/> |
|<span data-ttu-id="fd8c1-176">DT_SEC_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="fd8c1-176">DT_SEC_DISTLIST</span></span>  <br/> |<span data-ttu-id="fd8c1-177"> ( (ULONG) 0x00000009) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-177">((ULONG) 0x00000009)</span></span>  <br/> |<span data-ttu-id="fd8c1-178">安全通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-178">Security distribution list.</span></span>  <br/> |
   
<span data-ttu-id="fd8c1-179">在单林和跨林配置中，当 **PR_DISPLAY_TYPE** 的值为 DT_DISTLIST 且 DTE_IS_REMOTE_VALID 为 false 时，将 DTE_LOCAL 宏应用于此属性的值可让你获取通讯组列表的类型。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-179">In both a single forest and in a cross-forest configuration, when **PR_DISPLAY_TYPE** has the value of DT_DISTLIST and DTE_IS_REMOTE_VALID is false, applying the DTE_LOCAL macro to the value of this property can let you obtain the type of the distribution list.</span></span> <span data-ttu-id="fd8c1-180">可能的通讯组列表类型如下：</span><span class="sxs-lookup"><span data-stu-id="fd8c1-180">The possible types of distribution list are the following:</span></span> 
  
|<span data-ttu-id="fd8c1-181">**通讯组列表的类型**</span><span class="sxs-lookup"><span data-stu-id="fd8c1-181">**Type of Distribution List**</span></span>|<span data-ttu-id="fd8c1-182">**值**</span><span class="sxs-lookup"><span data-stu-id="fd8c1-182">**Value**</span></span>|<span data-ttu-id="fd8c1-183">**说明**</span><span class="sxs-lookup"><span data-stu-id="fd8c1-183">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd8c1-184">DT_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="fd8c1-184">DT_DISTLIST</span></span>  <br/> |<span data-ttu-id="fd8c1-185">((ULONG) 0x00000001)</span><span class="sxs-lookup"><span data-stu-id="fd8c1-185">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="fd8c1-186">通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-186">Distribution list.</span></span>  <br/> |
|<span data-ttu-id="fd8c1-187">DT_SEC_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="fd8c1-187">DT_SEC_DISTLIST</span></span>  <br/> |<span data-ttu-id="fd8c1-188"> ( (ULONG) 0x00000009) </span><span class="sxs-lookup"><span data-stu-id="fd8c1-188">((ULONG) 0x00000009)</span></span>  <br/> |<span data-ttu-id="fd8c1-189">安全通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-189">Security distribution list.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="fd8c1-190">相关资源</span><span class="sxs-lookup"><span data-stu-id="fd8c1-190">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fd8c1-191">协议规范</span><span class="sxs-lookup"><span data-stu-id="fd8c1-191">Protocol specifications</span></span>

<span data-ttu-id="fd8c1-192">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fd8c1-192">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fd8c1-193">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-193">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fd8c1-194">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fd8c1-194">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fd8c1-195">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-195">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fd8c1-196">头文件</span><span class="sxs-lookup"><span data-stu-id="fd8c1-196">Header files</span></span>

<span data-ttu-id="fd8c1-197">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fd8c1-197">Mapidefs.h</span></span>
  
> <span data-ttu-id="fd8c1-198">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-198">Provides data type definitions.</span></span>
    
<span data-ttu-id="fd8c1-199">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fd8c1-199">Mapitags.h</span></span>
  
> <span data-ttu-id="fd8c1-200">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fd8c1-200">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fd8c1-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd8c1-201">See also</span></span>



[<span data-ttu-id="fd8c1-202">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fd8c1-202">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fd8c1-203">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd8c1-203">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fd8c1-204">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fd8c1-204">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fd8c1-205">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fd8c1-205">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

