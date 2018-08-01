---
title: 查找 POP3 帐户的邮件下载历史记录
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 90a51150-5c2c-4d5b-8717-5dacc8532744
description: 本主题介绍如何邮件客户端可以访问 PidTagAttachDataBinary 属性获取 POP3 帐户的消息下载历史记录。
ms.openlocfilehash: 00cf5b02e29a22b5165a4aa339230b604722ab6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774363"
---
# <a name="locating-the-message-download-history-for-a-pop3-account"></a><span data-ttu-id="eb254-103">查找 POP3 帐户的邮件下载历史记录</span><span class="sxs-lookup"><span data-stu-id="eb254-103">Locating the message download history for a POP3 account</span></span>

<span data-ttu-id="eb254-104">本主题介绍如何邮件客户端可以访问[PidTagAttachDataBinary](http://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx)属性获取 POP3 帐户的消息下载历史记录。</span><span class="sxs-lookup"><span data-stu-id="eb254-104">This topic describes how a mail client can access the [PidTagAttachDataBinary](http://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx) property to get the message download history for a POP3 account.</span></span> 

<span data-ttu-id="eb254-105"><a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_WhyGetUIDLHistory"> </a></span><span class="sxs-lookup"><span data-stu-id="eb254-105"></span></span>

## <a name="why-get-the-message-download-history"></a><span data-ttu-id="eb254-106">为什么收到的消息下载历史记录？</span><span class="sxs-lookup"><span data-stu-id="eb254-106">Why get the message download history?</span></span>

<span data-ttu-id="eb254-107">Outlook 邮局协议 (POP) 提供程序允许用户检索并在其本地设备上的新电子邮件下载并随后保留或删除这些邮件服务器上的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="eb254-107">The Post Office Protocol (POP) provider for Outlook allows users to retrieve and download new email messages on their local device, and subsequently to leave or delete these email messages on the mail server.</span></span> <span data-ttu-id="eb254-108">当邮件客户端检查新邮件，若要下载时，它具有能够识别和仅下载新邮件的收件箱。</span><span class="sxs-lookup"><span data-stu-id="eb254-108">When the mail client checks for new messages to download, it has to be able to identify and download only the new messages for that Inbox.</span></span> <span data-ttu-id="eb254-109">邮件客户端首先使用 UIDL （唯一 ID 列出） 命令，获取以往任何时候都已传递给为唯一标识符 (UID) 的收件箱每封邮件的地图来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="eb254-109">The mail client does this by first using the UIDL (Unique ID Listing) command, which obtains a map of each message that has ever been delivered to that Inbox to a unique identifier (UID).</span></span> <span data-ttu-id="eb254-110">客户端还获取的已下载或删除该客户端上的收件箱邮件的消息下载历史记录。</span><span class="sxs-lookup"><span data-stu-id="eb254-110">The client also gets the message download history for messages that have been downloaded or deleted for the Inbox on that client.</span></span> <span data-ttu-id="eb254-111">使用邮件 UID 地图和下载历史记录，客户端可以然后确定不存在这些消息在历史记录，通过新建，因此，应下载。</span><span class="sxs-lookup"><span data-stu-id="eb254-111">Using the message UID map and download history, the client can then identify those messages that are absent in the history as new and, hence, should be downloaded.</span></span>
  
<span data-ttu-id="eb254-112">若要获取的收件箱的消息下载历史记录：</span><span class="sxs-lookup"><span data-stu-id="eb254-112">To get the message download history for an Inbox:</span></span>
  
- <span data-ttu-id="eb254-113">按照本主题查找**PidTagAttachDataBinary**属性，其中包含中二进制大型对象 (BLOB) 的特定格式的历史记录中的步骤。</span><span class="sxs-lookup"><span data-stu-id="eb254-113">Follow the steps in this topic to find the **PidTagAttachDataBinary** property, which contains the history in a binary large object (BLOB) that follows a specific format.</span></span> 
    
- <span data-ttu-id="eb254-114">继续[分析 POP3 帐户的消息下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md)，其中介绍了如何分析此 BLOB 标识的已下载或删除的收件箱邮件。</span><span class="sxs-lookup"><span data-stu-id="eb254-114">Continue with [Parsing the message download history for a POP3 account](parsing-the-message-download-history-for-a-pop3-account.md), which describes how to parse this BLOB to identify messages that have been downloaded or deleted for that Inbox.</span></span>
    
## <a name="core-concepts-to-know-for-locating-the-message-download-history"></a><span data-ttu-id="eb254-115">要了解的查找邮件的核心概念下载历史记录</span><span class="sxs-lookup"><span data-stu-id="eb254-115">Core concepts to know for locating the message download history</span></span>

<span data-ttu-id="eb254-116">收件箱的消息下载历史记录存储在二进制 MAPI 属性，可**PidTagAttachDataBinary**，在收件箱中的隐藏邮件的附件。</span><span class="sxs-lookup"><span data-stu-id="eb254-116">The message download history for an Inbox is stored in a binary MAPI property, **PidTagAttachDataBinary**, on an attachment of a hidden message in the Inbox.</span></span> <span data-ttu-id="eb254-117">表 1 显示了为帮助您了解如何找到的消息下载历史记录的概念的资源。</span><span class="sxs-lookup"><span data-stu-id="eb254-117">Table 1 shows resources for concepts that help you understand how to locate the message download history.</span></span>
  
<span data-ttu-id="eb254-118">**表 1. 核心概念**</span><span class="sxs-lookup"><span data-stu-id="eb254-118">**Table 1. Core concepts**</span></span>

|<span data-ttu-id="eb254-119">**文章标题**</span><span class="sxs-lookup"><span data-stu-id="eb254-119">**Article title**</span></span>|<span data-ttu-id="eb254-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="eb254-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="eb254-121">MAPI 隐藏文件夹</span><span class="sxs-lookup"><span data-stu-id="eb254-121">MAPI Hidden Folders</span></span>](http://msdn.microsoft.com/library/8b3b9c80-f7f4-4f37-bd6b-323469d020f1%28Office.15%29.aspx) <br/> |<span data-ttu-id="eb254-122">MAPI 允许邮件客户端中隐藏的文件夹和隐藏的邮件存储信息。</span><span class="sxs-lookup"><span data-stu-id="eb254-122">MAPI allows mail clients to store information in hidden folders and hidden messages.</span></span> <span data-ttu-id="eb254-123">隐藏的文件夹中的关联部分的 MAPI 文件夹，通常包含对不可见的信息而不用户操作。</span><span class="sxs-lookup"><span data-stu-id="eb254-123">Hidden folders are in the associated part of MAPI folders and typically contain information that is not visible to and not to be manipulated by users.</span></span> <span data-ttu-id="eb254-124">客户端决定的格式和内容存储在隐藏的文件夹中的隐藏邮件。</span><span class="sxs-lookup"><span data-stu-id="eb254-124">Clients decide the format and contents to store in hidden messages in hidden folders.</span></span>  <br/> |
|[<span data-ttu-id="eb254-125">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="eb254-125">MAPI Messages</span></span>](http://msdn.microsoft.com/library/417c113f-bd98-4515-85d1-09db7fc3a227%28Office.15%29.aspx) <br/> |<span data-ttu-id="eb254-126">MAPI 中对用户的客户端，或外部子树和用户看不到可见的标准 IPM 子树的文件夹中存储的邮件。</span><span class="sxs-lookup"><span data-stu-id="eb254-126">MAPI stores messages in folders, either in the standard IPM subtree that is visible to users of a client, or outside of the subtree and invisible to users.</span></span> <span data-ttu-id="eb254-127">消息可以具有存储在附件，可以是一个文件，另一条消息或 OLE 对象的窗体中的其他数据。</span><span class="sxs-lookup"><span data-stu-id="eb254-127">Messages can have additional data stored in an attachment, which can be in the form of a file, another message, or an OLE object.</span></span> <span data-ttu-id="eb254-128">对于消息下载历史记录，历史记录存储在一条消息，附加到另一个隐藏邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="eb254-128">In the case of the message download history, the history is stored in a property of a message that is attached to another hidden message.</span></span>  <br/> |
|[<span data-ttu-id="eb254-129">邮件属性概述</span><span class="sxs-lookup"><span data-stu-id="eb254-129">Message Properties Overview</span></span>](http://msdn.microsoft.com/library/447f54de-9f0d-4f73-89b6-bed9cfea9c15%28Office.15%29.aspx) <br/> |<span data-ttu-id="eb254-130">当客户端将信息存储在一条消息时，它将实际属性中的邮件存储的信息。</span><span class="sxs-lookup"><span data-stu-id="eb254-130">When a client stores information in a message, it actually stores the information in a property of the message.</span></span> <span data-ttu-id="eb254-131">MAPI 支持许多属性 — 某些始终存在，可以通过客户端设置、 都是可选的其他人 — 和客户端无法所期望可用或设置为有效的值。</span><span class="sxs-lookup"><span data-stu-id="eb254-131">MAPI supports many properties—some always exist and can be set by clients, others are optional—and clients cannot expect them to be available or set to valid values.</span></span> <span data-ttu-id="eb254-132">隐藏邮件的附件的**PidTagAttachDataBinary**属性中存储的消息下载历史记录。</span><span class="sxs-lookup"><span data-stu-id="eb254-132">The message download history is stored in the **PidTagAttachDataBinary** property of an attachment to a hidden message.</span></span>  <br/> |
|[<span data-ttu-id="eb254-133">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="eb254-133">MAPI Profiles</span></span>](http://msdn.microsoft.com/library/493c87a4-317d-47ec-850b-342cac59594b%28Office.15%29.aspx) <br/> |<span data-ttu-id="eb254-134">在会话中的登录时，邮件客户端选择介绍要使用的提供程序和服务的配置文件。</span><span class="sxs-lookup"><span data-stu-id="eb254-134">At logon time in a session, the mail client selects a profile that describes the providers and services to be used.</span></span> <span data-ttu-id="eb254-135">一个配置文件分为包含属性的部分。</span><span class="sxs-lookup"><span data-stu-id="eb254-135">A profile is divided into sections that contain properties.</span></span> <span data-ttu-id="eb254-136">具体而言， [PidTagSearchKey](http://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) (**PR_SEARCH_KEY**) 和[PidTagProfileName](http://msdn.microsoft.com/library/13ca726d-ae7a-4da9-9c8e-3db3c479f839%28Office.15%29.aspx) (**PR_PROFILE_NAME**) 属性始终存在。</span><span class="sxs-lookup"><span data-stu-id="eb254-136">In particular, the [PidTagSearchKey](http://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) (**PR_SEARCH_KEY**) and [PidTagProfileName](http://msdn.microsoft.com/library/13ca726d-ae7a-4da9-9c8e-3db3c479f839%28Office.15%29.aspx) (**PR_PROFILE_NAME**) properties always exist.</span></span> <span data-ttu-id="eb254-137">配置文件的搜索关键字唯一所有配置文件，并存储在配置文件部分的由**MUID_PROFILE_INSTANCE** （其中 MAPIGUID 中定义。H)。</span><span class="sxs-lookup"><span data-stu-id="eb254-137">A profile's search key is unique among all profiles, and is stored in the profile section that is identified by **MUID_PROFILE_INSTANCE** (which is defined in MAPIGUID.H).</span></span> <span data-ttu-id="eb254-138">使用[IMAPISession::OpenProfileSection](http://msdn.microsoft.com/library/e2757028-27e7-4fc0-9674-e8e30737ef1d%28Office.15%29.aspx)以打开部分，并使用[IMAPIProp::GetProps](http://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx)获取属性值。</span><span class="sxs-lookup"><span data-stu-id="eb254-138">Use [IMAPISession::OpenProfileSection](http://msdn.microsoft.com/library/e2757028-27e7-4fc0-9674-e8e30737ef1d%28Office.15%29.aspx) to open the section, and use [IMAPIProp::GetProps](http://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx) to get the property values.</span></span>  <br/> |
|[<span data-ttu-id="eb254-139">内容表</span><span class="sxs-lookup"><span data-stu-id="eb254-139">Contents Tables</span></span>](http://msdn.microsoft.com/library/7b8efb4e-b5be-41b8-81bb-9aa1da421433%28Office.15%29.aspx) <br/> |<span data-ttu-id="eb254-140">消息存储提供程序实现其文件夹的内容表。</span><span class="sxs-lookup"><span data-stu-id="eb254-140">Message store providers implement contents tables for their folders.</span></span> <span data-ttu-id="eb254-141">对相关部件的文件夹中的隐藏邮件，消息存储提供程序支持的关联的内容表和客户端可以使用[IMAPIContainer::GetContentsTable](http://msdn.microsoft.com/library/88c7a666-875d-473a-b126-dbbb7009f7d9%28Office.15%29.aspx)方法以返回到关联的内容表的指针。</span><span class="sxs-lookup"><span data-stu-id="eb254-141">For hidden messages in the associated part of a folder, message store providers support associated contents tables, and clients can use the [IMAPIContainer::GetContentsTable](http://msdn.microsoft.com/library/88c7a666-875d-473a-b126-dbbb7009f7d9%28Office.15%29.aspx) method to return a pointer to the associated contents table.</span></span>  <br/> |
|[<span data-ttu-id="eb254-142">关于限制</span><span class="sxs-lookup"><span data-stu-id="eb254-142">About Restrictions</span></span>](http://msdn.microsoft.com/library/e119fa20-08b8-4c8d-93fc-56037220890d%28Office.15%29.aspx) <br/> [<span data-ttu-id="eb254-143">限制的类型</span><span class="sxs-lookup"><span data-stu-id="eb254-143">Types of Restrictions</span></span>](http://msdn.microsoft.com/library/0d3bd58b-7100-4117-91ac-27139715c85b%28Office.15%29.aspx) <br/> [<span data-ttu-id="eb254-144">生成限制</span><span class="sxs-lookup"><span data-stu-id="eb254-144">Building a Restriction</span></span>](http://msdn.microsoft.com/library/12abbd8c-f825-493e-af42-344371d9658e%28Office.15%29.aspx) <br/> [<span data-ttu-id="eb254-145">示例限制代码</span><span class="sxs-lookup"><span data-stu-id="eb254-145">Sample Restriction Code</span></span>](http://msdn.microsoft.com/library/9b82097c-dbd6-4ba0-a6cb-292301f9402b%28Office.15%29.aspx) <br/> |<span data-ttu-id="eb254-146">MAPI，在客户端可以使用限制筛选内容表格，搜索行表示的某些属性设置为特定值的邮件。</span><span class="sxs-lookup"><span data-stu-id="eb254-146">In MAPI, clients can use restrictions to filter contents tables, to search for rows that represent messages that have a certain property set to a specific value.</span></span> <span data-ttu-id="eb254-147">通过使用[SRestriction](http://msdn.microsoft.com/library/c12b4409-da6f-480b-87af-1e5baea2e8bd%28Office.15%29.aspx)数据结构，它可以包含的更多专用限制结构联合定义限制。</span><span class="sxs-lookup"><span data-stu-id="eb254-147">Restrictions are defined by using the [SRestriction](http://msdn.microsoft.com/library/c12b4409-da6f-480b-87af-1e5baea2e8bd%28Office.15%29.aspx) data structure, which can contain a union of more specialized restriction structures.</span></span> <span data-ttu-id="eb254-148">[IMAPITable::FindRow](http://msdn.microsoft.com/library/6511368c-9777-497e-9eea-cf390c04b92e%28Office.15%29.aspx)方法应用限制，并检索与限制条件匹配的表中的第一行。</span><span class="sxs-lookup"><span data-stu-id="eb254-148">The [IMAPITable::FindRow](http://msdn.microsoft.com/library/6511368c-9777-497e-9eea-cf390c04b92e%28Office.15%29.aspx) method applies a restriction and retrieves the first row in a table that matches the restriction criteria.</span></span>  <br/> |
|[<span data-ttu-id="eb254-149">关于注册用于建立索引的存储区</span><span class="sxs-lookup"><span data-stu-id="eb254-149">About Registering Stores for Indexing</span></span>](http://msdn.microsoft.com/library/dd2aa06a-96e8-1291-18b5-fc3c40b74e4d%28Office.15%29.aspx) <br/> |<span data-ttu-id="eb254-150">[PidTagStoreProvider](http://msdn.microsoft.com/library/6f6cc66f-a08e-4f8e-b33a-d3674319248e%28Office.15%29.aspx) (**PR_MDB_PROVIDER**) 属性用于验证存储提供程序的类型。</span><span class="sxs-lookup"><span data-stu-id="eb254-150">Use the [PidTagStoreProvider](http://msdn.microsoft.com/library/6f6cc66f-a08e-4f8e-b33a-d3674319248e%28Office.15%29.aspx) (**PR_MDB_PROVIDER**) property to verify the type of store provider.</span></span> <span data-ttu-id="eb254-151">例如，若要验证是否在 Exchange 存储存储区， **PidTagStoreProvider**属性应返回常量**pbExchangeProviderPrimaryUserGuid**，在公共头文件 edkmdb.h 中定义所表示的值。</span><span class="sxs-lookup"><span data-stu-id="eb254-151">For example, to verify whether a store is an Exchange store, the **PidTagStoreProvider** property should return a value represented by the constant **pbExchangeProviderPrimaryUserGuid**, which is defined in the public header file edkmdb.h.</span></span>  <br/> |
   
## <a name="locating-the-appropriate-hidden-message-and-attachment"></a><span data-ttu-id="eb254-152">查找相应的隐藏的邮件和附件</span><span class="sxs-lookup"><span data-stu-id="eb254-152">Locating the appropriate hidden message and attachment</span></span>

<span data-ttu-id="eb254-153">现在，我们了解收件箱的消息下载历史记录处于隐藏邮件的附件的**PidTagAttachDataBinary**属性，以找到相应的适当的隐藏邮件的附件的过程涉及以下过程：</span><span class="sxs-lookup"><span data-stu-id="eb254-153">Now that we know the message download history for an Inbox is in the **PidTagAttachDataBinary** property of an attachment to a hidden message, the procedure to locate the appropriate attachment of the appropriate hidden message involves the following procedures:</span></span> 
  
1. [<span data-ttu-id="eb254-154">查找相应的隐藏的邮件</span><span class="sxs-lookup"><span data-stu-id="eb254-154">Find the appropriate hidden message</span></span>](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindHiddenMsg)
    
2. [<span data-ttu-id="eb254-155">查找相应的隐藏邮件的附件</span><span class="sxs-lookup"><span data-stu-id="eb254-155">Find the appropriate attachment of the hidden message</span></span>](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindAttachment)
    
3. [<span data-ttu-id="eb254-156">访问邮件附件的 PidTagAttachDataBinary 属性</span><span class="sxs-lookup"><span data-stu-id="eb254-156">Access the PidTagAttachDataBinary property of the message attachment</span></span>](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_AccessProp)

<span data-ttu-id="eb254-157"><a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindHiddenMsg"> </a></span><span class="sxs-lookup"><span data-stu-id="eb254-157"></span></span>

### <a name="find-the-appropriate-hidden-message"></a><span data-ttu-id="eb254-158">查找相应的隐藏的邮件</span><span class="sxs-lookup"><span data-stu-id="eb254-158">Find the appropriate hidden message</span></span>

1. <span data-ttu-id="eb254-159">在配置文件部分指定**MUID_PROFILE_INSTANCE**从配置文件，获取[PidTagSearchKey](http://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) (**PR_SEARCH_KEY**) 属性。</span><span class="sxs-lookup"><span data-stu-id="eb254-159">Get the [PidTagSearchKey](http://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) (**PR_SEARCH_KEY**) property from the profile, in the profile section specified by **MUID_PROFILE_INSTANCE**.</span></span>
    
2. <span data-ttu-id="eb254-160">通过调用**IMAPIContainer::GetContentsTable**打开相关联的收件箱文件夹内容。</span><span class="sxs-lookup"><span data-stu-id="eb254-160">Open the Associated Contents for the Inbox folder by calling **IMAPIContainer::GetContentsTable**.</span></span>
    
3. <span data-ttu-id="eb254-161">创建基于[PidTagConversationKey](http://msdn.microsoft.com/library/52c97d6c-7f4b-4522-aeac-0c1ed8475952%28Office.15%29.aspx) (**PR_CONVERSATION_KEY**)、 **PidTagSearchKey** (**PR_SEARCH_KEY**) 和[PidTagMessageClass](http://msdn.microsoft.com/library/1e704023-1992-4b43-857e-0a7da7bc8e87%28Office.15%29.aspx) (**PR_MESSAGE_CLASS**) 属性限制的获取 table包含的收件箱关联内容中的所有隐藏的消息。</span><span class="sxs-lookup"><span data-stu-id="eb254-161">Create a restriction based on the [PidTagConversationKey](http://msdn.microsoft.com/library/52c97d6c-7f4b-4522-aeac-0c1ed8475952%28Office.15%29.aspx) (**PR_CONVERSATION_KEY**), **PidTagSearchKey** (**PR_SEARCH_KEY**), and [PidTagMessageClass](http://msdn.microsoft.com/library/1e704023-1992-4b43-857e-0a7da7bc8e87%28Office.15%29.aspx) (**PR_MESSAGE_CLASS**) properties to get a table that contains all the hidden messages in the Associated Contents of the Inbox.</span></span> <span data-ttu-id="eb254-162">下面是限制的从[查找 POP3 UIDL 历史记录](http://blogs.msdn.com/b/stephen_griffin/archive/2012/12/03/locating-the-pop3-uidl-history.aspx)中提取的示例。</span><span class="sxs-lookup"><span data-stu-id="eb254-162">The following is an example of a restriction extracted from [Locating the POP3 UIDL History](http://blogs.msdn.com/b/stephen_griffin/archive/2012/12/03/locating-the-pop3-uidl-history.aspx).</span></span>
    
   ```cpp
      SRestriction rgRes[3]; 
      SPropValue rgProps[3]; 
      rgRes[0].rt = RES_AND; 
      rgRes[0].res.resAnd.cRes = 2; 
      rgRes[0].res.resAnd.lpRes = &amp;rgRes[1]; 
      rgRes[1].rt = RES_PROPERTY; 
      rgRes[1].res.resProperty.relop = RELOP_EQ; 
      rgRes[1].res.resProperty.ulPropTag = PR_CONVERSATION_KEY; 
      rgRes[1].res.resProperty.lpProp = &amp;rgProps[0]; 
      rgRes[2].rt = RES_PROPERTY; 
      rgRes[2].res.resProperty.relop = RELOP_EQ; 
      rgRes[2].res.resProperty.ulPropTag = PR_MESSAGE_CLASS; 
      rgRes[2].res.resProperty.lpProp = &amp;rgProps[1]; 
      rgProps[0].ulPropTag = PR_CONVERSATION_KEY; 
      rgProps[0].Value.bin = pVals[iSearchKey].Value.bin; // PR_SEARCH_KEY from the profile 
      rgProps[1].ulPropTag = PR_MESSAGE_CLASS; 
      rgProps[1].Value.LPSZ = (LPTSTR)"IPM.MessageManager";
   ```

4. <span data-ttu-id="eb254-163">从表格中，使用**IMAPITable::FindRow**查找隐藏的邮件。</span><span class="sxs-lookup"><span data-stu-id="eb254-163">From the table, find the hidden message by using **IMAPITable::FindRow**.</span></span>
    
5. <span data-ttu-id="eb254-164">如果未能找到的隐藏的邮件步骤 4，更改要使用**PidTagSearchKey** (**PR_SEARCH_KEY**) 而不是**PidTagConversationKey**，，，如下所示的限制：</span><span class="sxs-lookup"><span data-stu-id="eb254-164">If step 4 fails to find a hidden message, change the restriction to use **PidTagSearchKey** (**PR_SEARCH_KEY**) instead of **PidTagConversationKey**, as shown below:</span></span>
    
   ```cpp
    rgRes[1].res.resProperty.ulPropTag = rgProps[0].ulPropTag = PR_SEARCH_KEY;
   ```

6. <span data-ttu-id="eb254-165">查找使用**IMAPITable::FindRow**隐藏的邮件。</span><span class="sxs-lookup"><span data-stu-id="eb254-165">Find the hidden message using **IMAPITable::FindRow**.</span></span> 
    
7. <span data-ttu-id="eb254-166">如果第 6 步失败，更改要使用[PidTagSubject](http://msdn.microsoft.com/library/aa7ba4d9-c5e0-4ce7-a34e-65f675223bc9%28Office.15%29.aspx) (**PR_SUBJECT**) 等于以下值的限制 (使用如下所示`printf`样式替换为简便起见)。</span><span class="sxs-lookup"><span data-stu-id="eb254-166">If Step 6 fails, change the restriction to use [PidTagSubject](http://msdn.microsoft.com/library/aa7ba4d9-c5e0-4ce7-a34e-65f675223bc9%28Office.15%29.aspx) (**PR_SUBJECT**) being equal to the following value (shown below using  `printf` style substitution for brevity).</span></span> 
    
   ```cpp
    "Outlook Message Manager (%s) (KEY: %s)", PR_PROFILE_NAME, HexFromBin(PR_SEARCH_KEY)
   ```

8. <span data-ttu-id="eb254-167">使用**IMAPITable::FindRow**查找隐藏的邮件。</span><span class="sxs-lookup"><span data-stu-id="eb254-167">Find the hidden message by using **IMAPITable::FindRow**.</span></span>
    
9. <span data-ttu-id="eb254-168">如果您运行的 Outlook 2010 或更高版本，使用以下值**PidTagProfileName** (**PR_PROFILE_NAME**) 和**PidTagSearchKey** (**PR_SEARCH_KEY**)，分别。</span><span class="sxs-lookup"><span data-stu-id="eb254-168">If you are running Outlook 2010 or a later version, use the following values for **PidTagProfileName** (**PR_PROFILE_NAME**) and **PidTagSearchKey** (**PR_SEARCH_KEY**), respectively.</span></span>
    
   ```cpp
    CHAR g_szGeneralKey[] = "General Key"; 
    const SBinary g_binGeneralKey = {sizeof(g_szGeneralKey), (LPBYTE)g_szGeneralKey};
   ```

   <span data-ttu-id="eb254-169">运行通过步骤 3 至 8。</span><span class="sxs-lookup"><span data-stu-id="eb254-169">Run through Steps 3 through 8.</span></span> <span data-ttu-id="eb254-170">如果这无法查找一条消息，回退到原始步骤 3 至 8。</span><span class="sxs-lookup"><span data-stu-id="eb254-170">If this fails to find a message, fall back to the original steps 3 through 8.</span></span>
    
10. <span data-ttu-id="eb254-171">打开在步骤 4、 6 或 8 中发现的隐藏的邮件。</span><span class="sxs-lookup"><span data-stu-id="eb254-171">Open the hidden message found in Step 4, 6, or 8.</span></span>

<span data-ttu-id="eb254-172"><a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindAttachment"> </a></span><span class="sxs-lookup"><span data-stu-id="eb254-172"></span></span>

### <a name="find-the-appropriate-attachment-of-the-hidden-message"></a><span data-ttu-id="eb254-173">查找相应的隐藏邮件的附件</span><span class="sxs-lookup"><span data-stu-id="eb254-173">Find the appropriate attachment of the hidden message</span></span>

<span data-ttu-id="eb254-174">因为隐藏的邮件可能有多个附件，查找以下顺序中的相应附件。</span><span class="sxs-lookup"><span data-stu-id="eb254-174">Because the hidden message may have more than one attachment, look for the appropriate attachment in the following order.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eb254-175">此过程将再次使用`printf`样式为简便起见替换。</span><span class="sxs-lookup"><span data-stu-id="eb254-175">This procedure again uses the  `printf` style substitution for brevity.</span></span> 

1. <span data-ttu-id="eb254-176">查找的附件其[PidTagAttachLongFilename](http://msdn.microsoft.com/library/83b69e8f-0b5a-4992-b5b8-160d3bdfa22a%28Office.15%29.aspx) (**PR_ATTACH_LONG_FILENAME**) 匹配以下字符串，其中`szEmailAddress`在用户的配置文件中指定的用户的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb254-176">Look for an attachment whose [PidTagAttachLongFilename](http://msdn.microsoft.com/library/83b69e8f-0b5a-4992-b5b8-160d3bdfa22a%28Office.15%29.aspx) (**PR_ATTACH_LONG_FILENAME**) matches the following string, where  `szEmailAddress` is the user's SMTP address, as specified in the user's profile.</span></span> <span data-ttu-id="eb254-177">.</span><span class="sxs-lookup"><span data-stu-id="eb254-177"></span></span> 
    
   ```cpp
    "BlobPOP%s", szEmailAddress
   ```

2. <span data-ttu-id="eb254-178">查找的附件其[PidTagAttachFilename](http://msdn.microsoft.com/library/cbf34dd6-7733-47f6-9c41-9d82656ca9dc%28Office.15%29.aspx) (**PR_ATTACH_FILENAME**) 匹配"BlobPOP %s" `szEmailAddress`。</span><span class="sxs-lookup"><span data-stu-id="eb254-178">Look for an attachment whose [PidTagAttachFilename](http://msdn.microsoft.com/library/cbf34dd6-7733-47f6-9c41-9d82656ca9dc%28Office.15%29.aspx) (**PR_ATTACH_FILENAME**) matches "BlobPOP%s",  `szEmailAddress`.</span></span>
    
3. <span data-ttu-id="eb254-179">查找的附件其[PidTagDisplayName](http://msdn.microsoft.com/library/bd094e00-5c60-4bb3-9a45-b943fab52876%28Office.15%29.aspx) (**PR_DISPLAY_NAME**) 匹配"BlobPOP %s" `szEmailAddress`。</span><span class="sxs-lookup"><span data-stu-id="eb254-179">Look for an attachment whose [PidTagDisplayName](http://msdn.microsoft.com/library/bd094e00-5c60-4bb3-9a45-b943fab52876%28Office.15%29.aspx) (**PR_DISPLAY_NAME**) matches "BlobPOP%s",  `szEmailAddress`.</span></span>
    
4. <span data-ttu-id="eb254-180">查找的附件其**PidTagAttachFilename** (**PR_ATTACH_FILENAME**) 匹配"Blob%.8x" `dwAcctUID`，其中`dwAcctUID`来自[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md)。</span><span class="sxs-lookup"><span data-stu-id="eb254-180">Look for an attachment whose **PidTagAttachFilename** (**PR_ATTACH_FILENAME**) matches "Blob%.8x",  `dwAcctUID`, where  `dwAcctUID` comes from [PROP_ACCT_MINI_UID](prop_acct_mini_uid.md).</span></span> <span data-ttu-id="eb254-181">您可以使用[IOlkAccount::GetProp](iolkaccount-getprop.md)方法访问**PROP_ACCT_MINI_UID**属性。</span><span class="sxs-lookup"><span data-stu-id="eb254-181">You can use the [IOlkAccount::GetProp](iolkaccount-getprop.md) method to access the **PROP_ACCT_MINI_UID** property.</span></span> 

<span data-ttu-id="eb254-182"><a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_AccessProp"> </a></span><span class="sxs-lookup"><span data-stu-id="eb254-182"></span></span>

### <a name="access-the-pidtagattachdatabinary-property-of-the-message-attachment"></a><span data-ttu-id="eb254-183">访问邮件附件的 PidTagAttachDataBinary 属性</span><span class="sxs-lookup"><span data-stu-id="eb254-183">Access the PidTagAttachDataBinary property of the message attachment</span></span>

<span data-ttu-id="eb254-184">找到相应的消息的隐藏邮件的附件后, 使用**IMAPIProp::GetProps**读取的附件的**PidTagAttachDataBinary**属性。</span><span class="sxs-lookup"><span data-stu-id="eb254-184">After locating the appropriate message attachment of the hidden message, use **IMAPIProp::GetProps** to read the **PidTagAttachDataBinary** property of the attachment.</span></span> 

<span data-ttu-id="eb254-185"><a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_NextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="eb254-185"></span></span>

## <a name="next-steps"></a><span data-ttu-id="eb254-186">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eb254-186">Next steps</span></span>

<span data-ttu-id="eb254-187">您已从本主题了解如何为 POP3 邮件客户端的收件箱中找到的消息下载历史记录。</span><span class="sxs-lookup"><span data-stu-id="eb254-187">You have learned from this topic how to locate the message download history for the Inbox of a POP3 mail client.</span></span> <span data-ttu-id="eb254-188">请参阅[分析 POP3 帐户的消息下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md)以了解如何解析此历史记录，以确定已下载或删除的收件箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="eb254-188">See [Parsing the message download history for a POP3 account](parsing-the-message-download-history-for-a-pop3-account.md) to learn how to parse this history to identify messages that have been downloaded or deleted for the Inbox.</span></span> 

<span data-ttu-id="eb254-189"><a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_AdditionalRsc"> </a></span><span class="sxs-lookup"><span data-stu-id="eb254-189"></span></span>

## <a name="see-also"></a><span data-ttu-id="eb254-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb254-190">See also</span></span>

- [<span data-ttu-id="eb254-191">管理 POP3 帐户的邮件下载</span><span class="sxs-lookup"><span data-stu-id="eb254-191">Managing message downloads for POP3 accounts</span></span>](managing-message-downloads-for-pop3-accounts.md)   
- [<span data-ttu-id="eb254-192">分析 POP3 帐户的邮件下载历史记录</span><span class="sxs-lookup"><span data-stu-id="eb254-192">Parsing the message download history for a POP3 account</span></span>](parsing-the-message-download-history-for-a-pop3-account.md)
- [<span data-ttu-id="eb254-193">查找 POP3 UIDL 历史记录</span><span class="sxs-lookup"><span data-stu-id="eb254-193">Locating the POP3 UIDL History</span></span>](http://blogs.msdn.com/b/stephen_griffin/archive/2012/12/03/locating-the-pop3-uidl-history.aspx)
    

